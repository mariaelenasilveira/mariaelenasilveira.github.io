---
layout: post
title:  "POV rotativo"
date:   2018-08-20 18:54:00 -0300
categories: jekyll update
---

Olá caro leitor, seja bem vindo. Nesta postagem será feita uma breve introdução ao primeiro projeto exposto aqui no blog e então seguirá com outras 4 postagens mais detalhadas sobre cada etapa do projeto.

O projeto foi desenvolvido em grupo (composto por três discentes) como proposta de atividade avaliativa do componente curricular Sistemas Digitais, da grade do curso de Engenharia Mecatrônica da UFRN. Trata-se de um display de leds rotativo, conhecido como POV rotativo. É assim chamado, devido o fenômeno ***Persistence Of Vision*** (persistência da visão ou persistência da retina). 

Tal fenômeno torna possível ver a imagem estática mesmo que esteja sendo projetada em movimento.

(ADICIONAR IMAGEM)


O projeto consiste em um display formado por uma fileira de leds, que ao ser rotacionada a uma velocidade específica e com os leds programados para acender no tempo certo, imprimem uma imagem já pré definida. É possível ver na Figura 1 a estrutura física parada e na figura 2 o display em movimento.
 ![POV rotativo em funcionamento](/mariaelenasilveira.github.io/img/em_funcionamento.jpg)

 ![POV rotativo estático](/mariaelenasilveira.github.io/img/photo4954356484196640733.jpg "POV rotativo estático")

Os materiais usados para desenvolvimento do projeto, foram em sua maioria reaproveitados.
Para superfície giratória e também base do protótipo, usou-se um cooler de computador (especificar);
Para montagem do circuito  com os leds foi usada uma placa de fenolite (x) leds e (x) resistores de (y) Homs;
O arduíno nano (atmega 328) foi usado como microprocessador para hospedar o programa e controlar o processo.
Para que a imagem seja formada é necessário estabelecer o ponto de inicio da volta durante a rotação, para isso foi usado um red swith - um sensor de campo magnético - e um imã de neodímio na estrutura do cooler assim era estabelecido no codigo o inicio da rotação; a fonte de energia para o pequeno circuito foi uma bateria de 9V e para o cooler uma fonte.

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
