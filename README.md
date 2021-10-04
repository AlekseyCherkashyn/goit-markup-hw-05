# Домашнее задание

- Создай репозиторий `goit-markup-hw-05`.
- Склонируй созданный репозиторий и скопируй в него файлы предыдущей работы.
- Добавь анимацию декоративных эффектов для страниц макета
  [**домашнего задания #5**](<https://www.figma.com/file/oTYBECAN79dXy19hzWObO4/Web-Studio-(Version-2.1)?node-id=1%3A836>).
- Настрой `GitHub Pages` и добавь ссылку на живую страницу в шапку
  GitHub-репозитория.

## Критерии приёма работы наставником

### Проект

**`«A1»`** Все стили написаны в одном файле `styles.css`, который находится в
папке `css`.

**`«A2»`** Исходный код отформатирован при помощи `Prettier`.

**`«A3»`** Все изображения и текстовый контент взяты из макета.

**`«A4»`** На всех HTML-страницах подключен нормализатор стилей
[`modern-nomalize`](https://github.com/sindresorhus/modern-normalize).

**`«A5»`** Код написан следуя [**руководству**](https://codeguide.co/).

**`«A6»`** Скрипт модального окна подключен в HTML отдельным файлом `modal.js`.

### Разметка

**`«B1»`** Выполнена HTML-разметка всех элементов макета.

**`«B2»`** Теги использованы согласно их семантического смысла.

### Оформление

**`«C1»`** Для всех эффектов ховера и фокуса (цвет, фон, тень) сделаны переходы.
Время - `250ms`, функция распределения времени - `cubic-bezier(0.4, 0, 0.2, 1)`.

**`«C2»`** В переходах и анимациях явно указаны анимируемые свойства. Нигде нет
значения `all`.

**`«C3»`** В секции `Чем мы занимаемся` текст с фоном спозиционирован поверх
изображения.

**`«C4»`** В главной навигации, при помощи псевдоэлемента `::after`, сделано
подчёркивание ссылки текущей страницы (на которой сейчас находится
пользователь).

**`«C5»`** Синий оверлей с текстом на карточках страницы `Портфолио` появляется
при ховере в любом месте карточки.

**`«C6»`** Синий оверлей в карточках страницы `Портфолио` выезжает снизу, как
показано [на видео](./preview.gif).

**`«C7»`** У псевдоэлементов нет текстового контента в свойстве `content`. Они
использованы исключительно для декоративного оформления.

### Модальное окно

**`«D1»`** Выполнена разметка и оформление «бекдропа» (тёмного полупрозрачного
фона) модального окна.

**`«D2»`** «Бекдроп» заполняет 100% высоты и ширины вьюпорта браузера и
фиксирован в нём.

**`«D3»`** Выполнена разметка и оформление модального окна.

**`«D4»`** Модальное окно вертикально и горизонтально спозиционировано
посередине бекдропа.

**`«D5»`** Выполнена разметка и оформление кнопки закрытия модального окна в
верхнем правом углу.

**`«D6»`** Изначально модальное окно и бекдроп скрыты при помощи класса
`is-hidden` на бекдропе, в селекторе которого используются свойства
`visibility`, `opacity` и `pointer-events`.

**`«D7»`** Если убрать с бекдропа класс `is-hidden` - появляется бекдроп и
модальное окно.

**`«D8»`** Появление и скрытие модального окна анимировано при помощи перехода с
произвольным эффектом, например `scale` или `translate`, и `opacity`.

## Открытие/закрытие модального окна

Модальное окно с формой заявки открывается по клику на кнопку
`"Заказать услугу"`. Для того чтобы скрипт сработал необходимо добавить в
разметку специальные атрибуты, по которым скрипт ищет элементы:

- `data-modal-open` - на кнопку открытия модального окна.
- `data-modal-close` - на кнопку закрытия модального окна.
- `data-modal` - на бекдроп модального окна.

После чего, перед закрывающим тегом `body` добавить тег `script` со ссылкой на
файл скрипта для модально окна. Можно посмотреть
[видео-инструкцию](https://drive.google.com/file/d/1yasixN2K-9DdsYtKCJWVay9WbyTZai0t/view?usp=sharing).

```html
<body>
  <!-- Вся твоя разметка, включая разметку модалки -->

  <!-- Ставим перед закрывающим тегом body -->
  <script src="./js/modal.js"></script>
</body>
```

Скрипт который необходимо скопировать и вставить в файл `modal.js`.

```js
(() => {
  const refs = {
    openModalBtn: document.querySelector('[data-modal-open]'),
    closeModalBtn: document.querySelector('[data-modal-close]'),
    modal: document.querySelector('[data-modal]'),
  };

  refs.openModalBtn.addEventListener('click', toggleModal);
  refs.closeModalBtn.addEventListener('click', toggleModal);

  function toggleModal() {
    refs.modal.classList.toggle('is-hidden');
  }
})();
```
