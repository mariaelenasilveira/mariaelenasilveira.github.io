---
layout: post
title:  "POV rotativo - Circuito"
date:   2018-12-05 22:35:00 -0300
categories: jekyll update
---

<h4>Nas postagens anteriores, foi apresentado um pouco sobre o projeto e a implementação do código usado no POV. Neste será mostrado um pouco de como foi pensado o circuito</h4>

A parte do circuito (pelo menos a parte de se pensar) é bem simples, é necessária apenas uma entrada que receberá o sinal do sensor e as saídas vão de acordo com a quantidade de leds que será usada. No nosso caso foram 9 leds, lembrando que para cada led é necessário um resistor.

O microcontrolador que usamos foi o Atmega 328 (o do arduíno);

Então segue a listinha dos materiais:
* Leds (a quantidade que for usar);
* Resistores 260ohms (a mesma quantidade de leds);
* 1 Reed switch (Sensor de campo magnético);
* Jumpers (podem ser fios mesmo);
* Arduíno 

Uma montagem simples do circuito está repesentada na figura abaixo. 

![Circuito simulado](/mariaelenasilveira.github.io/images/circuito-pov.png)

Porém essa imagem é apenas para uma compreensão rápida do circuito! 
Devemos lembrar que no POV existe a rotação portanto cada componente deve estar muito firme em seu lugar. 
optamos por fazer o circuito em uma placa de fenolite bem estreita, e para diminuir o peso usamos o arduíno Nano.

![Circuito Real](/mariaelenasilveira.github.io/images/circuito-real.png)

Relembrando que era um projeto de fim de curso de um componente, tivemos um prazo bem curto para executar todo projeto e devido isto, foi preciso fazer algumas soldagens com generosas gambiarras. O ideal seriam trilhas feitas na placa, mas o "ajuste técnico" nos salvou.
Na imagem, no lado esquerdo estavam os leds e no direito o arduíno nano.

Boa parte do projeto já está feita, agora é preciso juntar tudo montando o "esqueleto" do projeto. Na próxima postagem mostraremos como se deu essa etapa. Até logo...  




[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
