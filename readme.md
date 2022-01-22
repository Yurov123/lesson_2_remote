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