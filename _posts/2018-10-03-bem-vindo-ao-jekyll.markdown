---
layout: post
title:  "POV rotativo - Programação"
date:   2018-08-20 18:54:00 -0300
categories: jekyll update
---

<h4>Nessa postagem, iremos falar um pouco sobre a programação do POV Rotativo.</h4>

Como já apresentado na primeira postagem, o projeto foi um trabalho avaliativo do componente Sistemas Digitais, presente na grade do curso de Engenharia Mecatrônica. Existiam assim alguns critérios para a implementação do código. O processador definido foi o ATMEGA328 que já vinha sendo trabalhado na disciplina, uma das especificações era que não era permitido o uso de bibliotecas prontas, a implementação deveria ser feita a nível de registradores.

Optamos por imprimir uma frase programada, a frase escolhida foi COISA BOA (jargão usado por nosso professor).
O código basicamente contém uma função para cada letra, e na função main elas são chamadas na ordem desejada e com a interrupção setada a partir da resposta do sensor, que informava o inicio de uma rotação.

Para a implementação de cada função foi utilizado um simulador com uma matriz de leds onde era possivel desenhar a letra desejada e assim setar quais saídas seriam altas "1" ou baixas "0".

[Simulador online da matriz de leds](https://toxic-dev.github.io/LED-Matrix-Simulator/)


[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
