+++
title = 'Использование hugo'
date = 2023-10-16T12:16:30+03:00
draft = false
tag = ["tag1", "tag2"]
+++
{{< youtube 2xkNJL4gJ9E >}}
## Создание сайта

```sh
$ hugo new site acewiki
```

В этой команде _acewiki_ -- это название сайта. В результате в текущем каталоге будет создан подкат `acewiki`, содержащий пустую структуру сайта.

```
hugotest/
└── acewiki
    ├── archetypes
    │   └── default.md
    ├── assets
    ├── content
    ├── data
    ├── hugo.toml
    ├── i18n
    ├── layouts
    ├── static
    └── themes
```

### Запуск сайта

Выполняется командой `hugo serve`.

- `-D, --buildDrafts` -- include content marked as draft
- `-d, --destination publishDir` -- по умолчанию сайт размещается в памяти. Чтобы положить его на диск, например для индексации, используется данный флаг.
- `--cleanDestinationDir` -- remove files from destination not found in static directories

```sh
$ hugo serve --destination pub
```

В результате сгенерированный сайт разместится в каталоге `acewiki/pub/`.

## Создание страницы

```sh
$ hugo new wiki/installation.md
```

Затем в метaданных страницы, что между +++ и +++, необходимо в поле draft поменять значение на false.

### Вставить картинку

![](/hugo/tree.png)

Чтобы на страничку в папке `~/hugo/test/content/hugo/custom/` вставить картинку, находящуюся в той же папке, надо написать так:

```md
![](/hugo/custom/chromium.png)
```

### [Вставить ссылку на страничку]()

Чтобы прейти на страничку `/posts/link-test.md` пишем следующее:
	
```md
[A link to some post page](/posts/link-test/)
```

That is [a link to some post page](/posts/link-test/).

Теперь чтобы перейти с той страницы обратно на эту, но уже к определенному заголовку, потребуется сделать на нем якорь.

```md
### [Вставить страничку]()
```
Ссылка же будет такого вида:

```md
Where will I end up after following [this link](/hugo/usage/#вставить-страничку), I wonder?
```

Where will I end up after following [this link](/hugo/usage/#вставить-страничку), I wonder?

В меню странички справа этот заголовок будет отображаться, но переход при на жатии на ссылку работать не будет.

---
Каталог `layouts` имеет высший приоритет по сравненеию с подобным каталогом в темах, `themes`. В каталогах тем имеются каты с таким же названием.

#### nav bar color

`#007bff` - было
`#062c56` - стало

#### search box

background-color: #f7f7f7

#### body

body {
 margin:0;
 font-family:-apple-system,BlinkMacSystemFont,segoe ui,Roboto,helvetica neue,Arial,noto sans,sans-serif,apple color emoji,segoe ui emoji,segoe ui symbol,noto color emoji;
 font-size:1rem;
 font-weight:400;
 line-height:1.5;
 color:#212529;
 text-align:left;
 background-color:#f5efe0
}
