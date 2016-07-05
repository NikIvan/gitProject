# gitProject
test project


Клонируем проект из репозитория
git clone https://github.com/NikIvan/gitProject.git

Для добавления файлов в коммит используем add
git add index.html

Коммитим изменения с сообщением
git commit -m "Initial commit"

Отправляем изменения
git push

Создание ветки и переход на неё
git checkout -b develop

git commit -m "34: Site header (Added tags)"

0.1)

Сливаем develop-feature1 в develop, а develop в master
git checkout develop
git merge develop-feature1
git checkout master
git merge develop

0.2)
Добавляем тег release1 с описанием
git tag -a release1 -m "First release"

0.3)
Удаляем ветку локально и из репозитория
git push origin --delete develop-feature2



1.1
git log --format="%s by %an" --since="3 hours ago" --no-merges develop-feature1..

--format - Форматирование
%s - Сообщение коммита
%an - Имя автора
--since - выборка по дате

1.2
git log --format="%s by %an% at %ai%"

2.
git cherry-pick develop