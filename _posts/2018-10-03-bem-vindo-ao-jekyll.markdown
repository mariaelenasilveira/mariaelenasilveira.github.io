---
layout: post
title:  "POV rotativo - Programação"
date:   2018-08-20 18:54:00 -0300
categories: jekyll update
---

<h4>Nessa postagem, iremos falar um pouco sobre a programação do POV Rotativo.</h4>

Como já apresentado na primeira postagem, o projeto foi um trabalho avaliativo do componente Sistemas Digitais, presente na grade do curso de Engenharia Mecatrônica. Existiam assim alguns critérios para a implementação do código. O processador definido foi o ATMEGA328 que já vinha sendo trabalhado na disciplina, uma das especificações era o não uso de bibliotecas prontas. A implementação deveria ser feita a nível de registradores.

Optamos por imprimir uma frase programada, a frase escolhida foi COISA BOA (jargão usado por nosso professor).
O código basicamente contém uma função para cada letra, e na função main elas são chamadas na ordem desejada e com interrupção setada a partir da resposta do sensor, que informava o inicio de uma rotação.

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


[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
