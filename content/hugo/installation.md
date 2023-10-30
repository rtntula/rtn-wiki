+++
title = 'Установка hugo'
date = 2023-10-16T12:16:28+03:00
draft = false
tag = ["tag2"]
+++
## Установка

### Ссылка на архив программы
https://github.com/gohugoio/hugo/releases/tag/v0.119.0 -- ссылка на страницу с бинарниками.
- hugo.exe >> D:\cygwin64\bin
- hugo_extended_0.119.0_linux-amd64.deb

```sh
dpkg -i hugo_extended_0.119.0_linux-amd64.deb
dpkg --get-selected |grep hugo
```


## Подключение темы

```sh
$ cd acewiki
$ git init
$ git submodule add https://github.com/vantagedesign/ace-documentation.git themes/ace-documentation
$ echo "theme = 'ace-documentation'" >> hugo.toml
```

### Обновление темы

```sh
$ cd themes/ace-documentation
$ git pull
```

