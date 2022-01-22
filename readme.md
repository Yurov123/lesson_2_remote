# Что такое git

**Cистема контроля версий (VCS)** — программное обеспечение для облегчения работы с изменяющейся информацией.

# Подготовка репозитория

## git init

Команда `git init` создает в директории пустой репозиторий в виде директории .git, где и будет в дальнейшем храниться вся информация об истории коммитов, тегах — о ходе разработки проекта:

    mkdir project-dir
    cd project-dir
    git init

## git add

Следующее, что нужно знать — команда git add. Она позволяет внести в индекс — временное хранилище — изменения, которые затем войдут в коммит.
Индексирует измененный файл, либо оповещение о создании нового:
git add EDITEDFILE
Вносит в индекс все изменения, включая новые файлы:
git add .

## git commit

`git commit`
Коммит проиндексированного состояния кода. Эта команда откроет текстовый редактор с предложением ввести комментарий к коммиту. После ввода комментария сохраните файл и закройте текстовый редактор, чтобы выполнить коммит.

`git commit -a`
Выполнение коммита состояния со всеми изменениями в рабочем каталоге. Эта команда включает только изменения отслеживаемых файлов (тех, которые были в какой-то момент добавлены в историю с помощью команды git add).

`git commit -m "commit message"`
Быстрая команда, которая создает коммит с указанным комментарием. По умолчанию команда git commit открывает локально настроенный текстовый редактор с предложением ввести комментарий к коммиту. При передаче параметра -m текстовый редактор не открывается, а используется подставленный комментарий.

`git commit -am "commit message"`
Команда для опытных пользователей с параметрами -a и -m. Эта комбинация параметров создает коммит всех проиндексированных изменений и добавляет к коммиту подставленный комментарий.

`git commit --amend`
Этот параметр добавляет команде commit новый уровень функциональности. При передаче этого параметра будет изменен последний коммит. Вместо создания нового коммита проиндексированные изменения будут добавлены в предыдущий коммит. Кроме того, эта команда откроет настроенный текстовый редактор системы с предложением изменить указанный ранее комментарий к коммиту.

## git rm и reset 

Из индекса и дерева проекта одновременно файл можно удалить командой git rm.
Удаляет из индекса и дерева проекта отдельные файлы:
git rm FILE1 FILE2
Хороший пример удаления из документации к git, удаляются сразу все файлы txt из папки:
git rm Documentation/\*.txt
Вносит в индекс все удаленные файлы:
git rm -r --cached .
Сбросить весь индекс или удалить из него изменения определенного файла можно командой git reset:
git reset
Удаляет из индекса конкретный файл:
git reset — EDITEDFILE
Команда git reset используется не только для сбрасывания индекса, поэтому дальше ей будет уделено гораздо больше внимания.

## git status — состояние проекта, измененные и не добавленные файлы, индексированные файлы

Команду git status, пожалуй, можно считать самой часто используемой наряду с командами коммита и индексации. Она выводит информацию обо всех изменениях, внесенных в дерево директорий проекта по сравнению с последним коммитом рабочей ветки; отдельно выводятся внесенные в индекс и неиндексированные файлы. Использовать ее крайне просто:
git status
Кроме того, git status указывает на файлы с неразрешенными конфликтами слияния и файлы, игнорируемые git.

## git log

Команда `git log` отображает отправленные снимки состояния и позволяет просматривать и фильтровать историю проекта, а также искать в ней конкретные изменения. С помощью `git status` можно просматривать рабочий каталог и раздел проиндексированных файлов, в то время как `git log` показывает только историю коммитов.