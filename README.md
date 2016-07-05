# gitProject
test project

git clone https://github.com/NikIvan/gitProject.git

git add index.html

git commit -m "Initial commit"

git push

Создание ветки и переход на неё
git checkout -b develop

git commit -m "34: Site header (Added tags)"

0.1)
git checkout develop
git merge develop-feature1
git checkout develop
git merge develop

0.2) 
git tag -a release1 -m "First release"

0.3)
git branch -d develop-feature2
git push origin --delete develop-feature2



1.1 
git log --format="%s by %an%" --since="3 hours ago" --no-merges develop-feature1..

1.2
git log --format="%s by %an% at %ai%"

2.
git cherry-pick develop