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
