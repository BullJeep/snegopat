# Руководство контрибьютора

Краткие инструкции для тех, кто хочет поучаствовать в проекте: исправить ошибку, добавить новый функционал в какой-либо из существующих скриптов или добавить свой оригинальный скрипт.

- [Руководство контрибьютора](#руководство-контрибьютора)
  - [Как развернуть проект](#как-развернуть-проект)
  - [Процесс](#процесс)
    - [Синхронизация личного форка с основным репозиторием Снегопата](#синхронизация-личного-форка-с-основным-репозиторием-снегопата)
  - [Документация и инструменты](#документация-и-инструменты)

## Как развернуть проект

Краткая последовательность:

- создайте каталог с произвольным именем. Например, `snegopat`
- положите snegopat.dll (свой личный или от триальной версии) в этот каталог
- выполните команду `git clone https://github.com/infostart-hub/snegopat.git core`
  - теперь репозиторий находится в подкаталоге `core`
- запустите стартер Снегопата - `core/starter.exe`
- если при запуске режима Конфигуратора вы видите окно Снегопата, значит, все сделано верно.

## Процесс

Разработка ведется по [GitHub Flow](https://guides.github.com/introduction/flow/).

Если кратко, то последовательность действий такая:

1. Выбрать из существующих задач (issues) в основном репо [infostart-hub/snegopat](https://github.com/infostart-hub/snegopat/issues/) или создать новую задачу, в которой описать функционал.
2. В комментарии к выбранной задачи написать, что собираетесь ее делать (чтобы вдруг никто другой не взялся).
3. Сделать форк основного репо
4. Клонировать форк себе, сделать отдельную ветку.
5. Сделать доработку, запушить ветку с доработкой на GitHub
6. В интерфейсе GitHub'а зайти в свой форк, там появится ссылка на создание pull-request'а, создать PR

### Синхронизация личного форка с основным репозиторием Снегопата

Ваш личный форк автоматически не синхронизируется с основным репозиторием, это нужно делать вручную.
Синхронизироваться нужно перед началом любых новых доработок.

Чтобы синхронизировать свой форк с основным репо, нужно в своей рабочей копии выполнить следующие действия:

```
# 1. подключаем основной репозиторий как upstream
git remote add upstream https://github.com/infostart-hub/snegopat.git

# 2. загружаем данные апстрима себе локально
git fetch upstream

# 3. переключаемся на основную ветку и обновляем ее из ветки master основного репозитория
git checkout master
git merge upstream/master

# 4. помещаем результат обновления из своей локальной копии в свой форк на гитхабе
git push
```

После этого для разработки

## Документация и инструменты

* [Как разрабатывать скрипты на TypeScript](/docs/10%20develop-start.md)
* [Описание объектной модели Снегопата](/docs/99%20snegapi.md)
* [Как разрабатывать скрипты на JavaScript](https://infostart.ru/1c/articles/116665/) - некоторые детали, описанные в статье, устарели, но может помочь в понимании общих принципов разработки скриптов для Снегопата
* [Как формы скриптов в формате ssf сконвертировать в epf](https://snegopat.ru/forum/viewtopic.php?f=3&t=850)
