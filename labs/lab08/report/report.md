---
## Front matter
title: "Отчёт по лабораторной работе 8"
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
  - parentracker=trueЗырянов Артём Алексеевич	НБИбд-01-22

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

Целью работы является приобретение навыков написания программ с использованием циклов и обработкой аргументов командной строки..

# Выполнение лабораторной работы

## Реализация циклов в NASM

ыл создан каталог для проведения лабораторной работы N8, а также был создан файл с именем lab8-1.asm.

При использовании инструкции loop в NASM для организации циклов, нужно помнить следующее:
эта инструкция применяет регистр ecx в качестве счётчика и на каждой итерации уменьшает его значение на единицу.
Для лучшего понимания этого процесса давайте рассмотрим пример программы, которая выводит значение регистра ecx. 

Я написал в файл lab8-1.asm текст программы из листинга 8.1. 
Затем создал исполняемый файл и проверил его работу.

![Код программы lab8-1.asm](image/01.png){ #fig:001 width=70%, height=70% }

![Компиляция и запуск программы lab8-1.asm](image/02.png){ #fig:002 width=70%, height=70% }

В этом примере показано, что применение регистра ecx в инструкции loop может вызвать 
неправильную работу программы. В текст программы я внёс изменения, заключающиеся 
в модификации значения регистра ecx внутри цикла.

Теперь эта программа запускает бесконечный цикл при нечётном значении N и выводит 
только нечётные числа при чётном значении N.

![Код программы lab8-1.asm](image/03.png){ #fig:003 width=70%, height=70% }

![Компиляция и запуск программы lab8-1.asm](image/04.png){ #fig:004 width=70%, height=70% }

Для того, чтобы применить регистр ecx в цикле и обеспечить правильность работы программы, 
можно использовать стек. Я внёс изменения в текст программы, добавив команды push и pop 
для сохранения значения счётчика цикла loop в стеке.

Был создан исполняемый файл и проверена его работа. Программа выводит числа от N-1 до 0, 
где количество проходов цикла соответствует значению N.

![Код программы lab8-1.asm](image/05.png){ #fig:005 width=70%, height=70% }

![Компиляция и запуск программы lab8-1.asm](image/06.png){ #fig:006 width=70%, height=70% }

Создал файл lab8-2.asm в каталоге ~/work/arch-pc/lab08 и ввел в него 
текст программы из листинга 8.2.

Затем создал исполняемый файл и запустил его, указав аргументы. Программа обработала 5 аргументов. Аргументами считаются слова/числа, разделённые пробелом.

![Код программы lab8-2.asm](image/07.png){ #fig:007 width=70%, height=70% }

![Компиляция и запуск программы lab8-2.asm](image/08.png){ #fig:008 width=70%, height=70% }

Рассмотрим еще один пример программы которая выводит сумму чисел,
которые передаются в программу как аргументы.

![Код программы lab8-3.asm](image/09.png){ #fig:009 width=70%, height=70% }

![Компиляция и запуск программы lab8-3.asm](image/10.png){ #fig:010 width=70%, height=70% }

Изменл текст программы из листинга 8.3 для вычисления произведения
аргументов командной строки.

![Код программы lab8-3.asm](image/11.png){ #fig:011 width=70%, height=70% }

![Компиляция и запуск программы lab8-3.asm](image/12.png){ #fig:012 width=70%, height=70% }

## Задание для самостоятельной работы

Напишите программу, которая находит сумму значений функции 
$f(x)$ для $x = x_1, x_2, ..., x_n$, т.е. программа должна выводить значение 
$f(x_1) + f(x_2)+ ... +f(x_n)$. 
Значения $x$ передаются как аргументы. 
Вид функции $f(x)$ выбрать из таблицы 8.1 вариантов заданий в соответствии с вариантом, 
полученным при выполнении лабораторной работы № 7. 
Создайте исполняемый файл и проверьте его работу на нескольких наборах $x$.

Мой вариант 1: $f(x) = 2x + 15$ 

![Код программы program-1.asm](image/13.png){ #fig:013 width=70%, height=70% }

Для проверки я запустил сначала с одним аргументом. Так, при подстановке $f(0)=15, f(10)=35$

Затем подал несколько аргументов и получил сумму значений функции.

![Компиляция и запуск программы program-1.asm](image/14.png){ #fig:014 width=70%, height=70% }

# Выводы

Освоили работы со стеком, циклом и аргументами на ассемблере nasm.