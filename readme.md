# BMSTU/GOST DevContainer


## What?

Запускает проект твоей будущей курсовой /диплома внутри докер-контейнера, интегрированного с vscode.

1. Ставит Latex, XeLatex, Bibtex, latex-lang-cur, TimesNewRoman.

2. Скачивает расширение vscode-latex-workshop

3. Устанавливает необходимые настройки и recipies

4. Подключает гост-файл (не гарантирую гост, но вроде он)

Написание латеха будет происходить полностью внутри докера после установки.

Коммитить изменения лучше не внутри докера, т.к. там не настроен git/ssh ключи, а с хоста.

## Что нужно

1. Visual Studio Code
2. Docker
3. Расширение [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) из магазина расширений VSCode (сам попросит поставить)

Внутри лежит пример моего НИР, переписанный ChatGPT так, как будто его писал гопник.