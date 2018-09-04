---
layout: post
title:  "POV rotativo"
date:   2018-08-20 18:54:00 -0300
categories: jekyll update
---


O primeiro projeto exposto aqui no blog trata-se de um display de leds rotativo.
Conhecido como POV rotativo, devido o fenômeno Persistence Of Vision pelo qual torna-se possível ver a imagem estática mesmo estando em rotação.
O projeto foi desenvolvido em grupo (composto por três discentes) como proposta de atividade avaliativa do componente curricular Sistemas Digitais, da grade do curso de Engenharia Mecatrônica da UFRN.
Nesta primeira postagem será feita uma breve introdução
e então será seguida de outras 4 postagens mais detalhadas sobre cada etapa do projeto.  
O projeto consiste em um display formado por uma fileira de leds, que ao ser rotacionada a uma velocidade específica e programados para acender no tempo certo, imprimem uma imagem já pré definida. É possível ver na Figura 1 a estrutura física parada e na figura 2 o display em movimento.

Os materiais usados para desenvolvimento do projeto, foram em sua maioria reaproveitados.
Para superfície giratória e também base do protótipo, usou-se um cooler de computador (especificar);
Para montagem do circuito  com os leds foi usada uma placa de fenolite (x) leds e (x) resistores de (y) Homs;
O arduíno nano (atmega 328) foi usado como microprocessador para hospedar o programa e controlar o processo.
Para que a imagem seja formada é necessário estabelecer o ponto de inicio da volta durante a rotação e para isso foi usado um red swith um sensor de campo magnético e um imã de neodímio na estrutura do cooler assim era estabelecido no codigo o inicio da rotação;
a fonte de energia para o pequeno circuito foi uma bateria de 9V.
e para o cooler uma fonte.,

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
