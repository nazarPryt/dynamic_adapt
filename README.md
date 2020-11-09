# Динамический адаптив (Dynamic Adapt)
JS функция для комфортной адаптивной верстки. Позволяет "перебрасывать" объекты DOM в зависимости от потребностей.

## Применение.
Для перещаемого объекта пишем HTML атрибут - `data-da` и указываем параметры.  
В javaScript создаем объект класса DynamicAdapt с параметором "min" или "max".  
Тип срабатывания брейкпоинта. max - Desktop First, min - Mobile First.  
Вызываем метод .init()  

const da = new DynamicAdapt("max");  
da.init();

## Параметры

`data-da="куда,когда,какой"`

Название | Значение по-умолчанию | Описание
------------- | ------------- | ------------- 
`куда (имя класса)` | _\[обязательный\]_ | Класс блока, в который нужно будет "перебросить" текущий объект. Если класс не уникален, объек перебросится в первый элемент с этим классом.
`когда` | 767 | Брейкпоинт при котором перемещать объект.
`какой` | last | Позиция на которую нужно переместить объект внутри родителя `куда`. Кроме цифр можно указать слова `first` (в начало блока) или `last` (в конец блока)

## Примеры

```html
<div data-da=".content__column-garden" class="content__block">Я Коля</div>
<div data-da=".content__column-garden,992" class="content__block">Я Коля</div>
<div data-da=".content__column-garden,992,2" class="content__block">Я Коля</div>
<div data-da=".content__column-garden,992,2" class="content__block">Я Коля</div>
```

## Подробнее
https://www.youtube.com/watch?v=QKuMr575vlQ

## Спасибо за идеи и предложения
last и first - идея Mark.
Параметры по умолчанию - идея mubat (https://github.com/mubat)
