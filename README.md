# Отчет по лабе 2

## Часть 1
1) Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com). - Создал репозиторий на сайте
2) Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге. 

>- 803  mkdir projects/lab02_DZ && cd projects/lab02_DZ
>- 804  git init
>- 805  git remote add origin https://github.com/supsun-sockol/lab02_DZ.git
>- 806  vim README.md
>- 807  git add README.md 
>- 808  git commit -m"Start doing DZ"
>- 809  git push origin main
>- 810  git status
>- 811  git pull origin main
>- 812  git add README.md 
>- 813  git status
>- 814  git commit -m"Start doing DZ"
>- 815  git pull origin master
3) Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.
>- 816  git add README.md 
>- 817  git commit -m"Start doing DZ"
>- 818  git push origin master
>- 819  vim hello_world.cpp
>- 820  add hello_world.cpp 
4) Добавьте этот файл в локальную копию репозитория.
>- 821  git add hello_world.cpp 
5) Закоммитьте изменения с осмысленным сообщением.
>- 822  git status
>- 823  git commit -m"added hw"
6) Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
>- 824  vim hello_world.cpp 
7) Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?
>- 825  git commit -m"change hw"
>- 826  git commit -a"change hw"
>- 827  git commit -a
>- 828  git status
>- 829  git commit -m"change hw" -a
8) Запуште изменения в удалёный репозиторий.
>- 830  git push origin master
9) Проверьте, что история коммитов доступна в удалёный репозитории.

## Часть 2

1) В локальной копии репозитория создайте локальную ветку patch1.
>- Эта команда в истории терминала почему-то не сохранилась
2) Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.
>- 848  vim hello_world.cpp 
3) commit, push локальную ветку в удалённый репозиторий.
>- 849  git commit -m"upgrade hw" -a
>- 850  git push origin patch1
4) Проверьте, что ветка patch1 доступна в удалёный репозитории.
>- Проверил
5) Создайте pull-request patch1 -> master.
>- Создал
6) В локальной копии в ветке patch1 добавьте в исходный код комментарии.
>- 851  vim hello_world.cpp 
7) commit, push.
>- 852  git commit -m"comment hw" -a
>- 853  git push origin patch1
8) Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
>- Проверил
9) В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.
>- Сделал на сайте
10) Локально выполните pull.
>- 859  git pull origin master 
11) С помощью команды git log просмотрите историю в локальной версии ветки master.
>- 860  git log
12) Удалите локальную ветку patch1.
>- 862  git checkout master 
>- 864  git branch -D patch1 

