# Русский календарь

Это библиотека JavaScript для расчета даты и времени по русскому календарю

Зависимости:
- JQuery 

## Что делает?

Принимает на вход объект типа Date() и выдает объект со списком параметов русского календаря.

Работает только от даты 1 января 1970 г.

## Инсталяция

Для инсталяции библиотеки используйте composer:

```json
{
    "require": {
        "i-avatar777/kalendar_slavi": "*"
    }
}
```

Или через команду

```
composer require i-avatar777/kalendar_slavi
```

Далее если у вас установлен Yii2 то в коде на странице нужно прописать:

```php
\iAvatar777\widgets\KalendarSlavi1\Asset::register($this);
```

Если у вас не установлен Yii2 то нужно скопировать файл `src/kalendar.js` в открытую папку сервера чтобы это файл был доступен на сайте по http и далее в коде HTML страницы прописать в теге HEAD:

```html
<html>
    <head>
        <link href="https://code.jquery.com/jquery-3.4.1.min.js" rel="stylesheet">
        <link href="/js/kalendar.js" rel="stylesheet">
    </head>
    <body></body>
</html>
```

## Пример использования

```js
var result = KrugoLet(d1);
$('#result').html(result.S_M_Z_H  + ' Лето<br>' + result.KrugFormat + '<br>' + result.Element + ' ' + result.ElementFormat + '<br>' + result.Image + ' ' + result.ImageFormat);
```

Выдаст
```
7528 Лето
Солнечного (Златого) Дракона
4 Солнечного (Златого)
8 Дракон
```

## Возвращаемые параметры

Расшифровка параметров возвращаемого объекта:

Время:
-  Dolja - обязательный / int - Доля 1/1296 Славяно-Арийской Части Часа
-  DoljaFormat - обязательный / string - Доля 1/1296 Славяно-Арийской Части Часа (с ведущими нулями 4 знака всего)
-  Chasti - обязательный / int - количество (с нулями) Частей (каждая 1/144 Часа) Славяно-Арийского часа
-  ChastiFormat - обязательный / int - количество (с нулями) Частей (каждая 1/144 Часа) Славяно-Арийского часа (с ведущими нулями 3 знака всего)
-  Chas - обязательный / int - Час Славяно-Арийский (1/16 суток)
-  ChasFormat - обязательный / string - Час Славяно-Арийский
-  JarFormat - обязательный / string - Время суток

Дата:
-  Dni - обязательный / int - день недели (1-9)
-  DniFormat - обязательный / str - день недели
-  Chislo - обязательный / int - Число Славяно-Арийского Месяца (в чётный месяц - 40 дней, в нечётный - 41)
-  Mes - обязательный / int - Славяно-Арийский Месяц (1-9)
-  MesFormat - обязательный / string - Славяно-Арийский Месяц (РАБГДЭВХТ)
-  Krug_Let - обязательный / int - Лето в Круге Лет - Круг - 16 Лет = 15 Простых Лет + 1 Священное Лето (все 9 Месяцев по 41 дню)
-  KrugFormat - обязательный / string - Название Лета ("первое" - Звёздного Храма)
-  Krug_Zizni - обязательный / int - Лето в Круге Жизни - Цикл 144 Лета = 9 Кругов Лет
-  S_M_Z_H - обязательный / int - Лето от Сотворения Мира в Звёздном Храме (Победы над Аримами)
-  Chertog - обязательный / int - Чертог, где находится Ярило-Солнце
-  ChertogFormat - обязательный / string - Чертог, где находится Ярило-Солнце
-  Element - обязательный / int - Элемент/цвет года (1-9)
-  ElementFormat - обязательный / string - Элемент/цвет года
-  Image - обязательный / int - Образ года (1-16)
-  ImageFormat - обязательный / string - Образ года

Отображение даты в новом формате:
https://docs.google.com/spreadsheets/d/15LIov8VQfAP0_Wu2omtnF7GPyKjhEWlLwuh0-sevnXg/edit?usp=sharing