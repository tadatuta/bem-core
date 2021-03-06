# bem-core Library [![Build Status](https://travis-ci.org/bem/bem-core.png)](https://travis-ci.org/bem/bem-core)

This README is also available [in English](http://bem.info/libs/bem-core/).

## Что это?

Базовая библиотека блоков для разработки веб-интерфейсов.
Содержит только необходимый минимум для разработки клиентского JS и HTML-шаблонов.

## Использование

Наиболее простым способом начать проект с использованием `bem-core` является
[project-stub](https://github.com/bem/project-stub).

Вы также можете добавить библиотеку к себе в проект любым известным вам способом.

## Состав

### Уровни
  - `common.blocks` — предназначен для любых устройств и браузеров
  - `desktop.blocks` — следует использовать для всех десктопных браузеров
  - `touch.blocks` — реализует некоторую специфику для тач-платформ

### Блоки
  - `i-bem` — базовый блок с хелперами для JS и HTML
  - `ecma` — некоторые ES5-полифилы
  - `strings` — хелперы для JS-строк
  - `objects` — хелперы для JS-объектов
  - `functions` — хелперы для JS-функций
  - `events` — JS-события
  - `querystring` — работа со строкой запроса
  - `tick` — глобальный таймер
  - `idle` — IDLE-событие
  - `next-tick` — полифил для `nextTick`/`setTimeout(0, ...)`
  - `inherit` — ООП-хелперы
  - `jquery` — jQuery
  - `clearfix` — CSS-трюк clearfix
  - `identify` — идентификация JS-объектов
  - `cookie` — хелперы для работы с браузерными куками
  - `vow` — реализация Promises/A+
  - `dom` — хелперы для работы с DOM
  - `loader` — загрузчик для JS-файлов
  - `ua` — определение возможностей браузера
  - `page` — скелет для html/head/body

### Технологии
  - vanilla.js + browser.js
  - bemhtml
  - bemtree

## История изменений

История изменений доступна на [отдельной странице](http://ru.bem.info/libs/bem-core/changelog/).

## Миграция

Миграция описана на [отдельной странице](http://ru.bem.info/libs/bem-core/migration/).

## Разработка

### Рабочая копия

1. Получаем исходники нужной версии (например, `v1`):
```
$ git clone -b v1 git://github.com/bem/bem-core.git
$ cd bem-core
```

2. Устанавливаем зависимости:
```
$ npm install
```
Для последующего запуска локально установленных [bem-tools](https://github.com/bem/bem-tools) нам потребуется
`export PATH=./node_modules/.bin:$PATH` или любой альтернативный способ.

3. Устанавливаем зависимые библиотеки:
```
$ bower-npm-install
```

4. Собираем примеры и тесты:
```
$ bem make sets
```

5. Запускаем разработческий сервер:
```
$ bem server
```

### Внесение изменений

1. [Создать issue](https://github.com/bem/bem-core/issues/new) с описанием сути изменений.
2. Определить в какую версию необходимо внести изменения.
3. Сделать feature-branch с указанием номера issue и версии (`issues/<номер issue>@v<номер версии>`) на основе ветки версии.
Например для issue с номером 42 и версией 1: `git checkout -b issues/42@v1 v1`. Если изменения нужно внести в несколько версий, то для каждой из версий создаётся отдельная ветка.
4. Сделать изменения, закоммитить и сделать push. Если это необходимо, то нужно сделать rebase от базовой ветки версии.
5. Создать pull-request на основе созданной ветки (или несколько pull-request-ов для случая изменений в нескольких версиях).
6. Любым способом связать pull-request и issue (например, c помощью комментария).
7. Ждать закрытия pull-request и issue ;-)

### Модульное тестирование

Сборка дефолтного тестового бандла для `ecma__array`: `bem make desktop.specs/ecma__array`
После сборки тестового бандла вы увидите результаты выполнения тестов в консоли.
Их также можно посмотреть в браузере, открыв `desktop.specs/ecma__array/spec-js+browser-js+bemhtml/spec-js+browser-js+bemhtml.html`.

По аналогии можно запустить тесты для других БЭМ-сущностей, имеющих реализацию в технологии `spec.js`.

Для сборки и запуска тестов используется библиотека [bem-pr](https://github.com/narqo/bem-pr).
См. [подробную информацию](https://github.com/narqo/bem-pr/blob/master/docs/tests.ru.md) про инфраструктуру
тестирования в bem-pr.

## Поддерживаемые браузеры
Мы поддерживаем браузеры на основе статистики, получаемой на сервисах [Яндекса](http://company.yandex.ru).

Браузеры с долей более 2% пользователей попадают в полную совместимость, с более 0.5% — в частичную,
что означает, что данные будут доступны, но возможна деградация. В браузерах с долей менее 0.5% мы прекращаем
тестирование.

### Десктопы
#### Полная совместимость
  - Google Chrome 29+
  - Firefox 24+
  - Yandex 1.7+
  - Opera 12.16
  - MSIE 10.0
  - MSIE 9.0
  - MSIE 8.0
  - Opera 12.15

#### Частичная совместимость
  - Opera 17.0
  - Opera 16.0
  - Opera 12.14
  - Opera 12.2
  - Firefox 23

### Тач-браузеры
#### Полная совместимость
  - iOS 6+
  - Android 2.3+
  - Opera Mobile 12+
  - Windows Phone 7+

#### Частичная совместимость
  - iOS 5
  - Android 2.2
