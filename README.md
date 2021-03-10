# Part 1

> Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).

Создал, если вы это читаете, то вы сейчас в нем.

> Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
* vim README.md
* git add README.md
* git commit -m"Start doing DZ"
* git push origin master
> Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.
* vim hellow_world.cpp

    #include <iostream>
    using namespace std;
    int main (){
        cout << "Hello world\n";
    }

> Добавьте этот файл в локальную копию репозитория.
* git add hellow_world.cpp

> Закоммитьте изменения с осмысленным сообщением.
* git commit -m"added hw"

> Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
* vim hello_world.cpp
``` 
    #include <iostream>
    using namespace std;
    int main (){
        string str;
        cin >> str;
        cout << "Hello world from " << str << "\n";
    }
``` 
> Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?
* git commit -m"upgrade hw" -a

Не нужно еще раз добавлять hellow word с помощью git add, потому что мы его уже добавил, и этот файл теперь будет отслеживаться автоматически, однако коммитеть нужно с оператором -а.
> Запуште изменения в удалёный репозиторий.
* git push origin master

> Проверьте, что история коммитов доступна в удалёный репозитории.

    upgrade hw
    @supsun-sockol
    supsun-sockol committed 5 minutes ago

    upgrade hw
    @supsun-sockol
    supsun-sockol committed 7 minutes ago

    added hw
    @supsun-sockol
    supsun-sockol committed 13 minutes ago

    Merge branch 'master' of https://github.com/supsun-sockol/lab02_DZ
    @supsun-sockol
    supsun-sockol committed 21 minutes ago

    added README
    @supsun-sockol

# Part 2

> В локальной копии репозитория создайте локальную ветку patch1.
* git branch patch1
* git checkout patch1

branch - создает новую ветку

checkout  - переключает на нужную ветку

> Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.
* vim hello_world.cpp
```    
    #include <iostream
    int main (){
        std::string str;
        std::cin >> str;
        std::cout << "Hello world from " << str << "\n";
    }
``` 
* git commit -m"upgrage hw and added RM" -a
* git push origin patch1
> Проверьте, что ветка patch1 доступна в удалёный репозитории.
Проверл, доступна, можете сами посмотреть.
> Создайте pull-request patch1 -> master.

supsun-sockol wants to merge 7 commits into master from patch1
> В локальной копии в ветке patch1 добавьте в исходный код комментарии.
* vim hello_world.cpp
```
#include <iostream
int main (){
    std::string str;
    std::cin >> str;
    std::cout << "Hello world from " << str << "\n";
}
// Jast a comment
```
> commit, push.
* git commit -m"added comment" -a
* git push origin patch1
<<<<<<< HEAD
> Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
```
 added comment

    patch1 (#2) 

@supsun-sockol
supsun-sockol committed 2 minutes ago 
```
> В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.
```

Pull request successfully merged and closed

You’re all set—the patch1 branch can be safely deleted.
```
> Локально выполните pull.
* git pull origin master
> С помощью команды git log просмотрите историю в локальной версии ветки master.
* git log
```
commit 15a4e4963c890666963b61ff3d3e524598e46afd (HEAD -> master)
Author: supsun-sockol <supsun-sockol@yandex.ru>
Date:   Mon Mar 8 20:02:57 2021 +0300

    apgrede RM

commit 430c5f438ab86c3e600c09f9d4d7fb1af161bf3c
Author: supsun-sockol <supsun-sockol@yandex.ru>
Date:   Mon Mar 8 19:30:23 2021 +0300

    write RM

commit 5be25052000cc8c98fd3224c1264ebdaea1f4b01
Author: supsun-sockol <supsun-sockol@yandex.ru>
Date:   Mon Mar 8 19:23:34 2021 +0300

    upgrade hw
```
> Удалите локальную ветку patch1.
* git branch -D patch1
```
Deleted branch patch1 (was ff5e00d).
```

# Part 3

> Создайте новую локальную ветку patch2.
* git branch patch2 
* git checkout patch2
> Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.
* clang-format -style=Mozilla hello_world.cpp
> commit, push, создайте pull-request patch2 -> master.
* git commit -m"style=Mozilla" -a
* git push origin patch2
```
supsun-sockol wants to merge 1 commit into master from patch2
```
> В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
Полностью поменял комментарий на
```
This is a comment!
```
Но!
```
This branch has no conflicts with the base branch
```
Мой код и так очень сильно был похож на код мозиллы, поэтому перехожу к искуственному созданию конфликтов.
Ведь изменения затрагивали разные строчки
Поэтому я поменяю метод комментирования в удаленном репозитории в главной ветке.
```
/* This is a Comment!*/
```
Теперь ошибкии есть
```
This branch has conflicts that must be resolved
```
> Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.
Я успользовал такой набор команд:
```
git checkout master
git rebase master
git checkout patch2
git merge patch2
```
> Сделайте force push в ветку patch2
* git push --force origin patch2
> Убедитель, что в pull-request пропали конфликтны.
> Вмержите pull-request patch2 -> master.
```
Pull request successfully merged and closed
```
