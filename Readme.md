## **Инструкция для работы с Git и удаленными репозиториями**

## Что такое Git?
Git - это одна из реализаций систем контроля версий, имеющая как и локальные, так и удаленные репозитории. Является самой популярной реализацией систем контроля версий в мире.

### Хранение данных в Git
Подход Git к хранению данных больше похож на набор снимков миниатюрной файловой системы. Каждый раз, когда вы делаете коммит, то есть сохраняете состояние своего проекта в Git, система запоминает, как выглядит каждый файл в этот момент, и сохраняет ссылку на этот снимок. Для увеличения эффективности, если файлы не были изменены, Git не запоминает эти файлы вновь, а только создаёт ссылку на предыдущую версию идентичного файла, который уже сохранён. Git представляет свои данные как, скажем, поток снимков.

### Три основные состояния
 У Git есть три основных состояния, в которых могут находиться ваши файлы: 
 * изменён (modified), 
 * индексирован (staged)
 * зафиксирован (committed).

К **изменённым** относятся файлы, которые поменялись, но ещё не были зафиксированы.

**Индексированный** — это изменённый файл в его текущей версии, отмеченный для включения в следующий коммит.

**Зафиксированный** значит, что файл уже сохранён в вашей локальной базе.

![Изображение состояния файлов](areas.png)


## Подготовка репозитория
Для создание репозитория необходимо выполнить команду "git init" в папке с репозиторием и у Вас создается репозиторий (появится скрытая папка -git)

## Сохранение коммитов

### Git add
Для добовления изменений в коммит используется команда "git add". Чтобы использовать команду "git add" напишите "git add <имя файла>"

### Просмотр состояния репозитория
Для того, чтрбы посмотреть состояние репозитория используется команда "git status". Для этого необходимо в папке с репозиторием написать "git status", и Вы увитите были ли изменения в файлах, или их не было.
Таким образом, команда проверки состояния сообщит, что коммитить нечего. Это означает, что в репозитории хранится текущее состояние рабочего каталога, и нет никаких изменений, ожидающих записи.

Мы будем использовать команду git status, чтобы продолжать отслеживать состояние репозитория и рабочего каталога.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с пепозиторием следующим образом: *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием

## Просмотр индексированных и неиндексированных изменений
Если результат работы команды git status недостаточно информативен для вас — вам хочется знать, что конкретно поменялось, а не только какие файлы были изменены — вы можете использовать команду git diff.
Команду git diff вы, скорее всего, будете использовать эту команду для получения ответов на два вопроса: что вы изменили, но ещё не проиндексировали, и что вы проиндексировали и собираетесь включить в коммит. Если git status отвечает на эти вопросы в самом общем виде, перечисляя имена файлов, git diff показывает вам непосредственно добавленные и удалённые строки — патч как он есть.

# **Основные команды Git**

* *git init* – инициализация локального репозитория
* *git status* – получить информацию от git о его текущем состоянии
* *git add* – добавить файл или файлы к следующему коммиту
* *git commit -m “message”* – создание коммита.
* *git log* – вывод на экран истории всех коммитов с их хеш-кодами
* *git checkout* – переход от одного коммита к другому
* *git checkout master* – вернуться к актуальному состоянию и продолжить работу
* *git diff* – увидеть разницу между текущим файлом и закоммиченным файлом


## Ветки в Git

### Создание ветки

Почти каждая система контроля версий (СКВ) в какой-то форме поддерживает ветвление. Используя ветвление, Вы отклоняетесь от основной линии разработки и продолжаете работу независимо от неё, не вмешиваясь в основную линию. Во многих СКВ создание веток — это очень затратный процесс, часто требующий создания новой копии каталога с исходным кодом, что может занять много времени для большого проекта.

Некоторые люди, говоря о модели ветвления Git, называют ее «киллер-фича», что выгодно выделяет Git на фоне остальных СКВ. Что в ней такого особенного? Ветвление Git очень легковесно: операция создания ветки выполняется почти мгновенно, переключение между ветками туда-сюда, обычно, также быстро. В отличие от многих других СКВ, Git поощряет процесс работы, при котором ветвление и слияние выполняется часто, даже по несколько раз в день. Понимание и владение этой функциональностью дает вам уникальный и мощный инструмент, который может полностью изменить привычный процесс разработки.


Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

## Слияние веток
Слияние используется в Git, чтобы собрать воедино разветвленную историю. Команда git merge выполняет слияние отдельных направлений разработки, созданных с помощью команды git branch, в единую ветку.

Обратите внимание: все приведенные ниже команды выполняют слияние в текущую ветку, в то время как целевая ветка остается без изменений. Поэтому команда git merge часто используется в сочетании с командами git checkout (для выбора текущей ветки) и git branch -d (для удаления устаревшей целевой ветки).

## **Конфликты слияния в Git**
Системы контроля версий предназначены для управления дополнениями, вносимыми в проект множеством распределенных авторов (обычно разработчиков). Иногда один и тот же контент могут редактировать сразу несколько разработчиков. Если разработчик A попытается изменить код, который редактирует разработчик B, может произойти конфликт. Для предотвращения конфликтов разработчики работают в отдельных изолированных ветках. Основная задача команды git merge заключается в слиянии отдельных веток и разрешении любых конфликтующих правок.

Общие сведения о конфликтах слияния
Слияние и конфликты являются неотъемлемой частью работы с Git. В других инструментах управления версиями, например SVN, работа с конфликтами может быть дорогой и времязатратной. Git позволяет выполнять слияния очень просто. В большинстве случаев Git самостоятельно решает, как автоматически интегрировать новые изменения.

Обычно конфликты возникают, когда два человека изменяют одни и те же строки в файле или один разработчик удаляет файл, который в это время изменяет другой разработчик. В таких случаях Git не может автоматически определить, какое изменение является правильным. Конфликты затрагивают только того разработчика, который выполняет слияние, остальная часть команды о конфликте не знает. Git помечает файл как конфликтующий и останавливает процесс слияния. В этом случае ответственность за разрешение конфликта несут разработчики.

## Удаление веток

Для удаления ветки используем, следующую команду:
git branch -d  local_branch_name
git branch – команда для удаления локальной ветки.
-d – флаг, опция команды git branch, сокращенный вариант записи --delete. Как и следует из названия, предназначен для удаления ветки.
local_branch_name – имя удаляемой ветки.
