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
