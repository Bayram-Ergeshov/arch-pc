---
## Front matter
title: "Отчёт по лабораторной работе 2"
subtitle: "Архитектура компьютера"
author: "Эргешов Байрам НКАбд-02-23"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью работы является изучить идеологию и применение средств контроля версий. Приобрести практические навыки по работе с системой git.

# Выполнение лабораторной работы

Создаю профиль на гитхабе.

![Регистрация профиля](image/01.jpg){ #fig:001 width=70%, height=70% }

Профиль создан

![Профиль создан](image/02.jpg){ #fig:002 width=70%, height=70% }

Теперь нужно создать репозиторий. 
Для этого захожу в репозиторий преподавателя и выбираю его как шаблон.

![Использование шаблона](image/03.jpg){ #fig:003 width=70%, height=70% }

![Использование шаблона](image/04.jpg){ #fig:004 width=70%, height=70% }

Установил программу гит

![Команды git](image/05.jpg){ #fig:005 width=70%, height=70% }

Нужно задать контакты пользователя, параметры веток и параметры символов.

![Параметры git](image/06.jpg){ #fig:006 width=70%, height=70% }

Для авторизации нужно сгенерировать ssh ключ и добавить его в аккаунт.

![Создание ключа](image/07.jpg){ #fig:007 width=70%, height=70% }

![Сохранение ключа](image/08.jpg){ #fig:008 width=70%, height=70% }

Далее создадим папку и клонируем туда репозиторий

![Создание рабочего каталога](image/09.jpg){ #fig:009 width=70%, height=70% }

Репозиторий содержит Make скрипт для создания папок курса. 
Выполним его, создадутся папки для лабораторных.

![Создание рабочего каталога](image/10.jpg){ #fig:010 width=70%, height=70% }

![Создание рабочего каталога](image/11.jpg){ #fig:011 width=70%, height=70% }

Теперь эти папки можно отправить в сетевой репозиторий.

![push](image/11.jpg){ #fig:011 width=70%, height=70% }

# Выводы

В ходе выполнения работы изучили работу с GitHub.
