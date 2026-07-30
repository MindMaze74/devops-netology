# Отчёт по заданию «Инструменты Git» - Старцев Данила Антонович

## Задание
В клонированном репозитории:

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.
```bash
git show aefea --pretty=format:'%H %s' -q
```
> Ответ:

> Полный хеш: aefead2207ef7e2aa5dc81a34aedf0cad4c32545

> Комментарий: Update CHANGELOG.md

2. Ответьте на вопросы.
* Какому тегу соответствует коммит `85024d3`?
```bash
git show 85024d3
```
>Ответ: 

>Тегу v0.12.23

* Сколько родителей у коммита `b8d720`? Напишите их хеши.
```bash
git log --oneline b8d720^1 
git log --oneline b8d720^2
```
>Ответ:

>Первый родитель: 56cd7859e

>Второй родитель: 9ea88f22f

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами  v0.12.23 и v0.12.24.
```bash
git log --oneline v0.12.23^..v0.12.24
```
<details>
  <summary>Нажмите, чтобы увидеть результаты git log </summary>
Хеш       Комментарий
33ff1c03b	(tag: v0.12.24) v0.12.24
b14b74c49	[Website] vmc provider links
3f235065b	Update CHANGELOG.md
6ae64e247	registry: Fix panic when server is unreachable
5c619ca1b	website: Remove links to the getting started guide's old location
06275647e	Update CHANGELOG.md
d5f9411f5	command: Fix bug when using terraform login on Windows
4b6d06cc5	Update CHANGELOG.md
dd01a3507	Update CHANGELOG.md
225466bc3	Cleanup after v0.12.23 release
85024d310	(tag: v0.12.23) v0.12.23
</details>


* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).
```bash
git log --oneline -SproviderSource
```
>Ответ:

>Хеш: 5e06e39fc

>Комментарий: Use registry alias to fetch providers

* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.
```bash
git log -L :globalPluginDirs:plugins.go --oneline
```
>Ответ(сокращённые хеши):

>1625584ed

>7a6615c90

* Кто автор функции `synchronizedWriters`? 
```bash
git log -S"func synchronizedWriters(" --pretty="%an" --reverse
```
>Ответ:

>Автором функции является Martin Atkins.

*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*
