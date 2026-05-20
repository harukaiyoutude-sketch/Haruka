# Haruka
Город в спмини лолиленд

<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Лолиленд — Официальный сайт города</title>
    <meta name="description" content="Официальный сайт города Лолиленд — уютное место для игроков, новости и контакты жителей.">
    <meta property="og:title" content="Лолиленд — Официальный сайт города">
    <meta property="og:description" content="Познакомьтесь с городом, его жителями и последними новостями Лолиленда!">
    <link rel="icon" href="https://via.placeholder.com/32x32.png?text=L">
    <style>
        :root {
            --pink: #ff66cc;
            --pink-hover: #ff3399;
            --blue-light: #a6c1ee;
            --background-main: linear-gradient(120deg, #fbc2eb, #a6c1ee);
            --white-transp: rgba(255,255,255,0.8);
            --card-bg: rgba(255,255,255,0.7);
            --shadow: 0 2px 5px rgba(0,0,0,0.1);
            --radius: 15px;
            --max-width: 1000px;
        }
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Arial', sans-serif;
            background: var(--background-main);
            color: #333;
            min-height: 100vh;
            line-height: 1.6;
        }
        header {
            position: sticky;
            top: 0;
            width: 100%;
            background: var(--white-transp);
            box-shadow: var(--shadow);
            z-index: 1000;
            backdrop-filter: blur(10px);
        }
        nav[aria-label] ul {
            display: flex;
            gap: 25px;
            list-style: none;
            font-weight: bold;
            justify-content: center;
            padding: 12px 0;
        }
        nav[aria-label] a {
            color: inherit;
            text-decoration: none;
            padding: 4px 8px;
            border-radius: 5px;
            transition: background 0.2s, color 0.2s;
        }
        nav[aria-label] a:focus, nav[aria-label] a:hover {
            color: var(--pink);
            background: #fff0fa;
            outline: none;
        }

        main {
            max-width: var(--max-width);
            margin: 0 auto;
            padding: 80px 24px 0 24px;
        }
        section {
            margin-bottom: 48px;
        }
        h1 {
            font-size: 3.5em;
            color: var(--pink);
            text-shadow: 1px 1px #fff;
            margin-bottom: 0.5em;
            text-align: center;
        }
        h2 {
            margin: 36px 0 12px 0;
            text-align: center;
        }
        h3 {
            margin: 18px 0 0 0;
            text-align: center;
        }
        p {
            max-width: 600px;
            margin: 0 auto 20px auto;
            text-align: center;
        }

        /* Home hero */
        #home {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 65vh;
        }
        .btn {
            display: inline-block;
            padding: 10px 25px;
            background: var(--pink);
            color: #fff;
            border-radius: 8px;
            margin-top: 24px;
            border: none;
            font-size: 1.15em;
            cursor: pointer;
            transition: background 0.25s;
            text-align: center;
        }
        .btn:hover,
        .btn:focus {
            background: var(--pink-hover);
            outline: none;
        }
        /* Cards for founders and residents */
        .cards {
            display: flex;
            flex-wrap: wrap;
            gap: 18px;
            justify-content: center;
            align-items: stretch;
        }
        .card {
            background: var(--card-bg);
            border-radius: var(--radius);
            padding: 20px;
            width: 230px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.08);
            margin: 12px 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: transform 0.22s, box-shadow 0.22s;
        }
        .card:hover, .card:focus-within {
            transform: scale(1.04);
            box-shadow: 0 16px 28px rgba(0,0,0,0.14);
        }

        /* City map */
        #map img {
            display: block;
            max-width: 90%;
            margin: 0 auto 15px auto;
            border-radius: var(--radius);
            box-shadow: 0 5px 15px rgba(0,0,0,0.19);
        }

        /* Новости */
        .news-list {
            display: flex;
            flex-direction: column;
            gap: 18px;
            align-items: center;
        }
        .news-item {
            background: var(--card-bg);
            max-width: 650px;
            width: 100%;
            margin: 0 auto;
            padding: 18px 28px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.09);
            transition: transform 0.18s;
        }
        .news-item:hover {
            transform: translateY(-3px) scale(1.02);
        }

        /* Контакты */
        #contact form {
            max-width: 400px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 14px;
            background: var(--white-transp);
            border-radius: var(--radius);
            padding: 20px 28px;
            box-shadow: 0 5px 12px rgba(0,0,0,0.08);
        }
        label {
            text-align: left;
            margin-bottom: 2px;
            font-weight: 500;
        }
        input, textarea {
            padding: 10px;
            border-radius: 8px;
            border: 1px solid #bbb;
            font-size: 1em;
            font-family: inherit;
            width: 100%;
        }
        textarea {
            resize: vertical;
            min-height: 90px;
        }
        button[type="submit"] {
            background: var(--pink);
            color: white;
            border: none;
            border-radius: 8px;
            padding: 10px;
            cursor: pointer;
            margin-top: 8px;
            font-size: 1.12em;
            transition: background 0.22s;
        }
        button[type="submit"]:hover,
        button[type="submit"]:focus {
            background: var(--pink-hover);
            outline: none;
        }

        /* Footer */
        footer {
            margin-top: 50px;
            text-align: center;
            padding: 16px 8px;
            font-size: 0.99em;
            background: var(--white-transp);
            backdrop-filter: blur(7px);
        }

        /* Адаптивность */
        @media (max-width: 800px) {
            main {
                padding: 60px 8px 0 8px;
            }
            .cards {
                flex-direction: column;
            }
        }
        @media (max-width: 550px) {
            nav[aria-label] ul {
                flex-wrap: wrap;
                gap: 12px;
                font-size: 1em;
            }
            h1 {font-size: 2.2em;}
            .card {width: 100%;}
        }
    </style>
</head>
<body>
    <!-- Шапка и навигация -->
    <header>
        <nav aria-label="Главная навигация">
            <ul>
                <li><a href="#home">Главная</a></li>
                <li><a href="#about">О городе</a></li>
                <li><a href="#founders">Основатели и жители</a></li>
                <li><a href="#map">Карта</a></li>
                <li><a href="#news">Новости</a></li>
                <li><a href="#contact">Контакты</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Главная -->
        <section id="home">
            <h1>Лолиленд</h1>
            <p>Добро пожаловать в волшебный город Лолиленд — уютный цифровой уголок для добрых игроков с большим сердцем и фантазией!
            </p>
            <a class="btn" href="#about">Узнать больше</a>
        </section>

        <!-- О городе -->
        <section id="about">
            <h2>О городе</h2>
            <p>
                Лолиленд — город для маленьких девочек-путешественниц воображения. Здесь царит забота, приключения и радость. 
                Любой, кто уважительно относится к остальным и любит творчество, найдёт здесь друзей и вдохновение.
            </p>
        </section>

        <!-- Основатели и жители -->
        <section id="founders">
            <h2>Основатели и жители</h2>
            <div class="cards" role="list">
                <div class="card" tabindex="0">
                    <h3>Консультат Детского Мира</h3>
                    <p>Основатель Лолиленда и главный хранитель сказочных традиций.</p>
                </div>
                <div class="card" tabindex="0">
                    <h3>Помощник 1</h3>
                    <p>Главный строитель, отвечающий за уют городских улиц.</p>
                </div>
                <div class="card" tabindex="0">
                    <h3>Житель: Маленькая Девочка 1</h3>
                    <p>Любимая постройка: Парк мечты и карусели.</p>
                </div>
                <div class="card" tabindex="0">
                    <h3>Житель: Маленькая Девочка 2</h3>
                    <p>Любимая постройка: Домик на дереве с секретами.</p>
                </div>
            </div>
        </section>

        <!-- Карта -->
        <section id="map">
            <h2>Схема города</h2>
            <img src="https://via.placeholder.com/800x400.png?text=Карта+Лолиленда" alt="Схематичное изображение города Лолиленд">
            <p>
                Интерактивная карта находится в разработке, но вы уже можете увидеть общий план города.
            </p>
        </section>

        <!-- Новости -->
        <section id="news">
            <h2>Новости</h2>
            <div class="news-list">
                <article class="news-item">
                    <h3>Новая игровая площадка</h3>
                    <p>Сегодня торжественно открыта новая площадка для всех жителей. Ждём вас на весёлые игры!</p>
                </article>
                <article class="news-item">
                    <h3>Конкурс построек</h3>
                    <p>Объявлен конкурс на самую креативную и красивую постройку месяца. Присылайте заявки!</p>
                </article>
                <article class="news-item">
                    <h3>Обновление сайта</h3>
                    <p>Теперь сайт стал ещё ярче и удобнее на мобильных устройствах. Спасибо за ваши отзывы!</p>
                </article>
            </div>
        </section>

        <!-- Контакты -->
        <section id="contact">
            <h2>Связаться с нами</h2>
            <form action="#" method="post" autocomplete="on" aria-label="Форма обратной связи">
                <label for="name">Ваше имя</label>
                <input type="text" id="name" name="name" required placeholder="Ваше имя" autocomplete="name">

                <label for="email">Ваш email</label>
                <input type="email" id="email" name="email" required placeholder="Ваш email" autocomplete="email">

                <label for="message">Сообщение</label>
                <textarea id="message" name="message" required placeholder="Ваше сообщение"></textarea>

                <button type="submit">Отправить</button>
            </form>
        </section>
    </main>

    <footer>
        &copy; 2026 Лолиленд. Все права защищены. | Сайт создан с любовью <!-- Можно указать ваше имя или ссылку -->
    </footer>
    <!-- Для доп. интерактивности — скрипт плавного скролла поддерживается большинством современных браузеров через CSS -->
</body>
</html>
