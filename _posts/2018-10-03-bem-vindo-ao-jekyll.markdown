---
layout: post
title:  "POV rotativo - Programação"
date:   2018-08-20 18:54:00 -0300
categories: jekyll update
---

<h4>Nessa postagem, iremos falar um pouco sobre a programação do POV Rotativo.</h4>

Como já apresentado na primeira postagem, o projeto foi um trabalho avaliativo do componente Sistemas Digitais, presente na grade do curso de Engenharia Mecatrônica. Existiam assim alguns critérios para a implementação do código. O processador definido foi o ATMEGA328 que já vinha sendo trabalhado na disciplina, uma das especificações era o não uso de bibliotecas prontas. A implementação deveria ser feita a nível de registradores.

Optamos por imprimir uma frase programada, a frase escolhida foi COISA BOA (jargão usado por nosso professor).
O código basicamente contém uma função para cada letra, e na interrupção elas são chamadas na ordem desejada.

Para a implementação de cada função foi utilizado um 
[Simulador online](https://toxic-dev.github.io/LED-Matrix-Simulator/) com uma matriz de leds onde era possivel desenhar a letra desejada e assim setar quais saídas seriam altas "1" ou baixas "0".

![Desenho da letra "B"](/mariaelenasilveira.github.io/images/matriz-de-leds.png "Desenho da letra 'B' na matriz")

Uma fila da matriz é equivalente a nossa fileira de led, de maneira que para o desenho ser feito setamos a saída de das portas na primeira fila, logo após um delay e então a saída da segunda fila e assim para quantas filas forem necessárias para formar a letra desejada. o trecho de codigo que mostra a função da letra "B" está a seguir.


	#define del1 1  //delay utilizado no programa
	void B(){
		PORTD = 0xfc;
		PORTB = 0x00;
		_delay_ms(del1);
		PORTD = 0x24;
		PORTB = 0x02;
		_delay_ms(del1);
		PORTD = 0x24;
		PORTB = 0x02;
		_delay_ms(del1);
		PORTD = 0x24;
		PORTB = 0x02;
		_delay_ms(del1);
		PORTD = 0xd8;
		PORTB = 0x00;
		_delay_ms(del1);
		PORTD = 0x00;
		PORTB = 0x00;
	}

A atribuíção de cada saída foi feita analisando as portas do arduíno Nano com o uso do Datasheet.
a PB1 foi usada como porta de entrada para o sensor. e a PB0 usada como saída para o primeiro led. Por isso o valor atribuído ao PORTB sempre era 0 ou 2. 
Já as portas de PD7 a PD2 foram usadas para completar os 7 leds.
O valor setado no PORT é um valor completo para 8 bits em hexadecimal. Assim, se apenas os leds PD7 e PD6 iriam acender no PORTD, então o valor setado seria 11000000 que em hexadecimal correspondia a 0xc0.

![Datasheet arduíno Nano](/mariaelenasilveira.github.io/images/arduino-nano-datasheet.gif)

O procedimento para implementação da função que imprime a letra "B", foi usado para implementar cada letra desejada.
E então cada função foi chamada dentro de uma interrupção.

	//INTERRUPÇÃO
	ISR(TIMER1_CAPT_vect) { //interrupção por captura do sinal
	    cli();
	    //COISA BOA
	    C();
	    O();
	    I();
	    S();
	    A();
	    B();
	    O();
	    A();

	    sei();
	}

Todos os parametros da interrupção foram setados na main. Aqui chamamos atenção, a explicação do funcionamento da interrupção é um pouco confuso, mas no datasheet do ATMEG328 vem explicando direitinho cada registrador. Aqui no nosso projeto era necessário ter apenas o cuidado de usar o pino PB0 como entrada da resposta do sensor já que para essa interrupção ele é um pino especial de leitura, sendo usado para controlar o timer/counter, pois ele é responsável pelo ICP1 (timer/counter1 input capture input).

	int main(){
	    DDRD = 0xFC;
	    DDRB = 0x02;
	    DDRC = 0x00;
	    cli();  //limpa as flags da interrupção
	    
	    // configuração da interrupção
	    TCCR1A ^= (1 << WGM10); // seleciona o modo de operação normal do timer/counter
	    //icnc1 - filtra o sinal capturado (icp1)
	    //ices1 - seleciona a borda do icp1
	    //CS12, CS10 - divisor do clock
	    TCCR1B &= 0b11111000;
	    TCCR1B = 1 << ICNC1 | 1 << ICES1 | 1 << CS12 | 1 << CS10;
	    TCNT1 = 0;  // variavel do contador
	    TIMSK1 = (1 << ICIE1);  // enable da interrupção
	    sei(); //ativa as configurações
	    while(1){
	        
		}
	    
	}

O grupo desenvolveu o codigo, assim a baixo nível por ter sido um aspecto exigidido. Porém fica a critério pessoal, o uso de funções prontas de bibliotecas disponíveis que facilitam a programação em arduíno. Com uma pesquisada rapida na internet é possível encontrar propostas de códigos para essas funções. 


[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
