
# Шаблон русской кандидатской диссертации на Typst

Это обновление на коленке под актуальную версию Typst"а шаблона за авторством [Горчакова Сергея](https://github.com/SergeyGorchakov/russian-phd-thesis-template-typst). Автор, судя по всему, шаблон более не обновляет и в жидхаб не заходит, а между тем, начиная с Typst 0.12 появились ломающие совместимость с шаблоном изменения:
+ Часть вызовов по типу `glossary_entries.final(loc)` более не принимают `loc`, информация о положении сама получается из контекста.
+ Вызовы `locate(x =>...` больше не работают. Вместо них надо пользоваться `context`, а локацию для нужных методов доставать из `here()`.
Изменения небольшие, и, в общем-то, самостоятельно проделать их не сложно. Но мне очень не хотелось знакомиться с синтаксисом и правилами языка Typst дальше набирания формулок и простой разметки, а пришлось. Может кому-нибудь с аналогичным желание не учить ничего нового этот шаблон сэкономит время и нервы.

Из новых фишек - падежи для терминов из глоссария. Теперь можно добавить к элементу в `glossary_entries` поле `forms`, например:
```
(
    key: "cat",
    short: "кошка", 
    forms: (genitive: "кошки", dative: "кошке", accusative: "кошку", plural: "кошки", myform: "кОтОвОе" ),
    desc: "Теневые хозяева рода людского.",
)
```

После чего можно делать такие вещи:

```
Есть такие животные -- @cat-plural. Каждому надо дать по @cat-dative. У кого нет @cat-genitive -- того искренне жаль. Оооо, @cat -- это @cat-myform!
```
Это превращается в
```
Есть такие животные - кошки. Каждому надо дать по кошке. У кого нет кошки - того искренне жаль. Оооо, кошка -- это кОтОвОе!
```
с рабочими ссылками на `cat` в глоссарии.


## Установка
Проще всего делать так - найти путь к вашему пакету с `modern-russian-dissertation`. У меня он -- `$HOME/.cache/typst/packages/preview/modern-russian-dissertation/`. Там создайте папку `0.1.0` и выпложите содержимое репозитория. 
Обращаю внимание, что обновлённый шаблон живёт под новой версией:
```
#import "@preview/modern-russian-dissertation:0.1.0": *
```
 
# Оригинальный README.md
## Шаблон русской кандидатской диссертации 


Шаблон русской кандидатской диссертации на языке разметки [Typst](https://typst.app/) - современной альтернативы LaTeX.

### Использование

В веб-приложении нажмите "Start from template" и на панели найдите `modern-russian-dissertation`.

Вы также можете инициализировать проект командой:

```bash
typst init @preview/modern-russian-dissertation
```

Будет создана новая директория со всеми файлами, необходимыми для начала работы.

### Конфигурация

Список литературы формируется из файлов `common/external.bib` и `common/author.bib`.

Список сокращений и условных обозначений формируется из данных, записанных в файле `common/acronyms.typ` `common/symbols.typ`. Список определений формируется из данных в файле `common/glossary.typ`.

### Компиляция  

Для компиляции проекта из CLI используйте:

```bash
typst compile thesis.typ
```

Или если вы хотите следить за изменениями:

```bash
typst watch thesis.typ
```

### Особенности

- Стандарт ГОСТ Р 7.0.11-2011.

### Благодарности

- Благодарность авторам шаблона диссертации на [LaTeX](https://github.com/AndreyAkinshin/Russian-Phd-LaTeX-Dissertation-Template)

- [Полезные ссылки](https://github.com/AndreyAkinshin/Russian-Phd-LaTeX-Dissertation-Template/wiki/Links#%D0%BF%D1%80%D0%BE%D1%87%D0%B8%D0%B5-%D1%80%D0%B5%D0%BF%D0%BE%D0%B7%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B8-%D1%81-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D1%8B%D0%BC%D0%B8-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D0%B0%D0%BC%D0%B8)