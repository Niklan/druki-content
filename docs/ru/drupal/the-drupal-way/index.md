---
title: Философия Drupal
slug: the-drupal-way
metatags:
  description: 'Философия Drupal — это набор основных ценностей и принципов сообщества.'
---

_Официального документа, отражающего принципы сообщества Drupal нет, поэтому, они собраны из публичных материалов и устоявшихся принципов внутри сообщества._

Философия Drupal, также известна как Drupal Way, это набор основных принципов и ценностей сообщества. Если коротко, то их можно описать фразой: _<abbr title="Прекратите переизобретать колесо, и у вас будет больше времени и сил для проектировки космического корабля.">Stop reinventing the wheel and you'll have more time and energy to design a spaceship.</abbr>_

## Мы следим за качеством кода

Drupal разработчики очень трепетно относятся к качеству кода, который они пишут. В сообществе имеются официальные [стандарты кодирования](../standards/index.md), которые должны соблюдать все, кто пишет код под Drupal. Данные требования выработаны годами, имеют под собой основания и охватывают как PHP, так и CSS, JS, HTML.

Цель данных стандартов и жестких требований очень проста — код, написанный для Drupal, как для ядра, так и сторонних модулей, должен читаться как свой собственный. Это позволяет быстро ориентироваться и понимать что делает тот или иной файл или функция.

## Мы не хакаем ни ядро, ни модули

Drupal предоставляет всевозможные инструменты, для того, чтобы разработчики сторонних модулей, могли внедряться в работу других модулей или ядра, на различных его этапах выполнения, тем самым, срезая на корню необходимость писать свой код напрямую в ядре или стороннем модуле.

## Будьте открытыми и вносите свой вклад

Drupal является OpenSource системой, весь его код свободен и открыт для всех. Это же и касается модулей, которые для него разрабатываются. В замен, сообщество ожидает ответных действий от вас. Это не обязательно должен быть код, даже сообщение об ошибке, или опечатке где-то в интерфейсе модуля, уже очень полезная информация для разработчиков.

Именно поэтому у Drupal огромное количество модулей в открытом доступе, и почти отсутствуют платные решения. Разработчики делятся своими наработками, а затем, совместно с теми, кому данное решение тоже необходимо, дорабатывают и улучшают функционал.

Не нужно работать в одиночку, всегда найдутся другие люди, желающие помочь вам с вашими идеями и довести их до финишной прямой.

## Пишите модули атомически

Всегда кажется, что писать весь функционал в одном модуле это хорошая идея. На самом деле, оно того не стоит, и лучше приложить небольшие усилия для разбиения кастомного кода на мелкие кусочки в виде различных модулей.

Монолитные модули, это хорошо, но их очень сложно поддерживать, они несут с собой очень много лишнего функционала, который может быть не нужен конкретному сайту, но он будет выполняться и делать дополнительную нагрузку на сайт, тем самым, замедляя его работу без необходимости.

Также, модули-комбайны пагубно влияют на Drupal, так как новичкам, присуще ставить подобные модули пачками, так как они решают их задачи, без необходимости кодить, но, возможно, им нужен лишь 1 функционал из 1000 других, которые предоставляет каждый из этих модулей. В конечном итоге они достигают своей цели, но сайт их тормозит, и они винят в этом Drupal.

Не пишите весь код в одном модуле, дробите его на самодостаточные мини-модули, которые расширяют основной. В качестве примера, посмотрите как устроен модуль Drupal Commerce 2, который имеет огромное количество функционала, но его всегда можно либо включить, либо выключить, если так требуется.

## Темплейты — для отображения

Мы не пишем логику и запросы в темплейтах. Это плохой тон в Drupal сообществе и очень не приветствуется.

Темплейты созданы для формирования HTML разметки страницы, больше ни для чего. Если вы выполняете запрос в темплейте на получение данных, пишите CSS стили, или JS код — вы используете их неправильно.

В Drupal 8, ситуацию сильно улучшили, перейдя с PHPTemplate шаблонизатора на Twig. Тем не менее многие все равно умудряются делать серьезную логику в темплейтах, пишут фильтры и плагины для Twig, которые позволяют писать запросы в темплейте и исполнять PHP код напрямую — это плохо.

Drupal предоставляет множество инструментов, когда вы можете подготовить данные для темплейта заранее в своем модуле, а в темплейте только использовать их значения. Не допускайте таких ошибок, лучше прочитайте про то, как работает hook_theme() и его производные хуки, изучите [как правильно подключать библиотеки](../8/libraries/index.md) (CSS и JS) только там, где вам это нужно. Всё это позволит вам избежать перемешивания логики с отображением.

## Никакого PHP в базе данных

**Серьезно, не нужно.**

## Используйте Drupal API

У Drupal очень большой API, спустя несколько лет, вы все равно будете находить что-то новое для себя, и это не преувеличение. Всё изучать не стоит, и не имеет смысла. Учить нужно только основные моменты, а остальное, гуглить по необходимости.

Если вы не понимаете как что-то сделать, или куда-то подлезть, очень вероятно, в Drupal уже есть API в ядре, который позволит вам решить вашу задачу, нужно лишь просто поискать.

Мы не пишем костыли, когда есть официальные решения в ядре.

## Не переизобретайте велосипед

Drupal уже второй десяток лет, он появился не вчера, а это значит, что у сообщества скопилось огроменное количество решений и готового функционала. Если вы нашли модуль, который решает вашу задачу, не нужно писать ещё один такой же. Исключением может быть лишь только то, что вы хотите сделать модуль, решающий аналогичную задачу, но другим способом, или же, если модуль заброшен автором, и он не передает права на проект, даже в таком случае, есть процессы позволяющие получить права над проектом без участия автора.

## Ссылки

 * [The Drupal Way](http://sharonkrossa.com/drupallets/drupal-way), Sharon Krossa, 2011
 * [The Drupal Way™](https://www.jeffgeerling.com/blogs/jeff-geerling/the-drupal-way), Jeff Geernling, 2013
 * [Implementing a Web Design the Drupal Way (not just any old way)](https://www.annertech.com/blog/implement-web-design-drupal-way), Anthony Lindsay, 2015
 * [Programming The Drupal Way](http://www.kwallcompany.com/blog/programming-drupal-way), Sebastian, 2013
 