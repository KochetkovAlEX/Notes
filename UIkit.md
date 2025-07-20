# UIkit CSS Framework 

# Установка
> npm install uikit --save

В основном файле `index.html` пишем `uk-$` и получаем скелет приложения

## 1. Кнопки (Buttons)
```html
<!-- Стандартные кнопки -->
<button class="uk-button uk-button-default">Default</button>
<button class="uk-button uk-button-primary">Primary</button>
<button class="uk-button uk-button-secondary">Secondary</button>
<button class="uk-button uk-button-danger">Danger</button>

<!-- Кнопки с разными размерами -->
<button class="uk-button uk-button-small">Small</button>
<button class="uk-button">Default</button>
<button class="uk-button uk-button-large">Large</button>

<!-- Disabled кнопка -->
<button class="uk-button uk-button-primary" disabled>Disabled</button>
```

## 2. Карточки (Card)
```html
<div class="uk-card uk-card-default uk-card-body">
    <h3 class="uk-card-title">Заголовок карточки</h3>
    <p>Содержимое карточки. UIkit делает их стильными по умолчанию.</p>
</div>

<!-- Карточка с изображением -->
<div class="uk-card uk-card-default">
    <div class="uk-card-media-top">
        <img src="image.jpg" alt="">
    </div>
    <div class="uk-card-body">
        <h3 class="uk-card-title">Карточка с изображением</h3>
        <p>Текст под изображением.</p>
    </div>
</div>
```

## 3. Навигация (Navbar)
```html
<nav class="uk-navbar-container" uk-navbar>
    <div class="uk-navbar-left">
        <a class="uk-navbar-item uk-logo" href="#">Логотип</a>
    </div>
    <div class="uk-navbar-right">
        <ul class="uk-navbar-nav">
            <li class="uk-active"><a href="#">Главная</a></li>
            <li><a href="#">О нас</a></li>
            <li>
                <a href="#">Выпадающее меню</a>
                <div class="uk-navbar-dropdown">
                    <ul class="uk-nav uk-navbar-dropdown-nav">
                        <li><a href="#">Пункт 1</a></li>
                        <li><a href="#">Пункт 2</a></li>
                    </ul>
                </div>
            </li>
        </ul>
    </div>
</nav>
```

## 4. Уведомления (Alert)

```html
<div class="uk-alert-primary" uk-alert>
    <a class="uk-alert-close" uk-close></a>
    <p>Это primary уведомление с кнопкой закрытия.</p>
</div>

<div class="uk-alert-success" uk-alert>
    <p>Success! Операция выполнена успешно.</p>
</div>

<div class="uk-alert-danger" uk-alert>
    <p>Ошибка! Что-то пошло не так.</p>
</div>
```

## 5. Сетка (Grid)

```html
<div class="uk-child-width-1-3@s" uk-grid>
    <div>
        <div class="uk-card uk-card-default uk-card-body">Колонка 1</div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-body">Колонка 2</div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-body">Колонка 3</div>
    </div>
</div>
```
## 6. Формы (Form)

```html
<form class="uk-form-stacked">
    <div class="uk-margin">
        <label class="uk-form-label" for="form-name">Имя</label>
        <div class="uk-form-controls">
            <input class="uk-input" id="form-name" type="text" placeholder="Введите имя">
        </div>
    </div>

    <div class="uk-margin">
        <label class="uk-form-label" for="form-email">Email</label>
        <div class="uk-form-controls">
            <input class="uk-input" id="form-email" type="email" placeholder="email@example.com">
        </div>
    </div>

    <div class="uk-margin">
        <label class="uk-form-label" for="form-select">Выпадающий список</label>
        <div class="uk-form-controls">
            <select class="uk-select" id="form-select">
                <option>Вариант 1</option>
                <option>Вариант 2</option>
            </select>
        </div>
    </div>

    <button class="uk-button uk-button-primary">Отправить</button>
</form>
```
## 7. Модальное окно (Modal)
```html
<!-- Кнопка для открытия модального окна -->
<button class="uk-button uk-button-default" uk-toggle="target: #my-modal">Открыть модалку</button>

<!-- Само модальное окно -->
<div id="my-modal" uk-modal>
    <div class="uk-modal-dialog uk-modal-body">
        <button class="uk-modal-close-default" type="button" uk-close></button>
        <h2 class="uk-modal-title">Заголовок модалки</h2>
        <p>Содержимое модального окна...</p>
    </div>
</div>
```