# gitProject
test project

## 0

Клонируем проект из репозитория
`git clone https://github.com/NikIvan/gitProject.git`

Для добавления файлов в коммит используем комаанду `add`
`git add index.html`

Коммитим изменения с сообщением

`git commit -m "Initial commit"`

Отправляем изменения

`git push`

Для создания новой ветки и перехода на неё используем

`git checkout -b develop`

Эта команда является сокращением от 

`git branch develop`
`git checkout develop`

После изменения файлов добавляем их в коммит и выполняем

`git commit -m "34: Site header (Added tags)"`

Текст в кавычках после флага `-m` будет добавлен как описание коммита

* 1

Сливаем develop-feature1 в develop, а develop в master
`git checkout develop`
`git merge develop-feature1`
`git checkout master`
`git merge develop`

* 2
Для добавления тега к коммиту (ветке) - переходим на него:

`git checkout master`

Добавляем тег `release1` с описанием:

`git tag -a release1 -m "First release"`

* 3
Удаляем ветку локально и из репозитория:

`git push origin --delete develop-feature2`

Если после нашего коммита кто-то успел слить к себе изменения - ему
необходимо будет выполнить команду:

`git fetch --all --prune`

Если же коммит ещё не отправлен, то можно удалить ветку только из локального хранилища командой (предварительно перейдя на другую ветку):

`git branch -d develop-feature2`

##1

* 1

`git log --format="%s by %an" --since="3 hours ago" --no-merges develop-feature1..`

`--format` - Форматирование
`%s` - Сообщение коммита
`%an` - Имя автора
`--since` - выборка по дате

* 2

`git log --format="%s by %an% at %ai%" --grep="231:"`

Команда `--grep` проверяет описание коммита на соответствие регулярному выражению в кавычках

##2

Для добавления коммита в текущую ветку из другой выполняем

`git cherry-pick 239ab83`

Где "239ab83" - идентификатор коммита.
Можно перечислить комиты через пробел
(последний коммит будет верхним)

##3

Для выполнения поставленой задачи предлагаю перейти к комиту С1, сделать новую ветку от него и последовательно коммандами `cherry-pick` добавлять изменения. В команду также необходимо добавить флаг `--no-commit` для того чтобы можно было заново задать описание к коммиту. Это будет выглядеть примерно так:

`git checkout -b develop-feature3_1 C1`
`git cherry-pick C2 --no-commit`
`git add *.*`
`git commit -m "25: Some task (description)"`
`git cherry-pick C3 --no-commit`
`git add *.*`
...

Затем слить ветку в develop (если необходимо) и удалить ветку с ошибочными описаниями

