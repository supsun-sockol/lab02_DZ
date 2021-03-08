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
    
    #include <iostream>
    using namespace std;
    int main (){
        string str;
        cin >> str;
        cout << "Hello world from " << str << "\n";
    }
    
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
    
    #include <iostream
    int main (){
        std::string str;
        std::cin >> str;
        std::cout << "Hello world from " << str << "\n";
    }
    
* git commit -m"upgrage hw and added RM" -a
* git push origin master
