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

Para a implementação de cada função foi utilizado um simulador com uma matriz de leds onde era possivel desenhar a letra desejada e assim setar quais saídas seriam altas "1" ou baixas "0".

![Desenho da letra "B"](/mariaelenasilveira.github.io/images/matriz-de-leds.jpg)

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
'

[Simulador disponível aqui](https://toxic-dev.github.io/LED-Matrix-Simulator/)


[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
