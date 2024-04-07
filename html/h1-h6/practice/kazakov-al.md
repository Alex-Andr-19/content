🛠 SEO-специалисты советуют соблюдать определенное максимальное количество заголовков, например, использовать:
- `<h2>` — не больше двух, максимум трёх раз;
- `<h3>` — 4-5 раз и так далее.

К сожалению, такой совет часто разбивается о скалы реальности, например, если у вас лендинг с большим количеством секций или секция со множеством карточек:

```html
<body>
  <header class="header">
    <h1 class="header__heading"></h1>
  </header>
  <main class="content">
    <section class="promo">
      <h2 class="promo__heading"></h2>
      ...
    </section>

    <section class="about-company">
      <h2 class="about-company__heading"></h2>
      ...
    </section>

    <section class="teams">
      <h2 class="teams__heading"></h2>
      ...
    </section>

    <section class="why-us">
      <h2 class="why-us__heading"></h2>

      <article class="card">
        <h3 class="card__title"></h3>
      </article>
      <article class="card">
        <h3 class="card__title"></h3>
      </article>
      <article class="card">
        <h3 class="card__title"></h3>
      </article>
      ...
    </section>

    <section class="faq">
      <h2 class="faq__heading"></h2>
      ...
    </section>

    ...
  </main>
</body>
```

Секций и карточек может быть сколько угодно, в попытке ограничить количество заголовков вы навредите семантике и доступности. Поэтому при написании разметки в первую очередь думайте о пользователях, руководствуйтесь здравым смыслом и берите в расчёт контент сайта 😊

🛠 Иногда, в процессе вёрстки можно заметить, что дизайн заголовков повторяется. Допустим, текст сайта имеет такие стили:

```css
body {
  font-size: 18px;
  font-weight: 400;
}

.header__heading {
  font-size: 45px;
  font-weight: 800;
  color: #4A148C;
}

.promo__heading {
  font-size: 31px;
  font-weight: 700;
  color: #2B2B2B;
}

.about-company__heading {
  font-size: 31px;
  font-weight: 700;
  color: #2B2B2B;
}

.why-us__heading {
  font-size: 31px;
  font-weight: 700;
  color: #2B2B2B;
}

.card__title {
  font-size: 20px;
  font-weight: 500;
  color: #000;
}

.footer__heading {
  font-size: 25px;
  font-weight: 300;
  color: #2B2B2B;
}
```

В чем проблема и что сразу бросается в глаза: большое количество повторяемых стилей. Если вдруг поменяется корпоративный цвет или дизайнер захочет поправить типиграфику всего сайта — придётся править огромное количество строчек кода. Избежать этого поможет выделение стилей в отдельные токены — такой подход называется компонентным. Токены — свойства, которые вынесены в переменные, которые затем можно многократно использовать в любом другом месте в коде. Если какое-то свойство объекта повторяется больше одного раза, стоит задуматься, можно ли его вынести в токен. Выглядеть токены будут примерно так:

```css
.text_size_3xl {
  font-size: 45px;
}

.text_size_2xl {
  font-size: 31px;
}

.text_size_xl {
  font-size: 25px;
}

.text_size_l {
  font-size: 20px;
}

.text_size_m {
  font-size: 18px;
}

.text_weight_2xl {
  font-weight: 800;
}

.text_weight_xl {
  font-weight: 700;
}

.text_weight_l {
  font-weight: 500;
}

.text_weight_m {
  font-weight: 400;
}

.text_weight_s {
  font-weight: 300;
}

.color_accent {
  color: #4A148C;
}

.color_default {
  color: #000;
}

.color_secondary {
  color: #2B2B2B;
}
```

После того как выделили токены, мы можем их переиспользовать:
