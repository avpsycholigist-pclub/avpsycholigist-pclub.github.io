<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>P.club | Профессиональный старт</title>
    <style>
        :root {
            --color-deep-blue: #0a1a3a;
            --color-gold: #d4af37;
            --color-light-gold: #f5e8c0;
            --color-dark-red: #8b0000;
            --color-white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, sans-serif;
            color: var(--color-deep-blue);
            background-color: var(--color-deep-blue);
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
            position: relative;
        }

        /* Контейнер */
        .container {
            max-width: 1000px;
            margin: 40px auto;
            background: rgba(255, 255, 255, 0.98);
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(10, 26, 58, 0.3);
            border: 2px solid var(--color-gold);
            padding: 40px;
            position: relative;
            z-index: 2;
            overflow: hidden;
        }

        /* Снежинки только сзади */
        .snowflakes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        .snowflake {
            position: absolute;
            top: -10px;
            color: var(--color-light-gold);
            font-size: 1em;
            opacity: 0.5;
            animation: fall linear infinite;
            z-index: 1;
        }
        @keyframes fall {
            to { 
                transform: translateY(105vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Шапка */
        .header {
            text-align: center;
            margin-bottom: 50px;
            padding-bottom: 25px;
            border-bottom: 2px dashed var(--color-gold);
        }
        
        /* Шрифт P.club */
        .club-title {
            font-family: 'Georgia', 'Times New Roman', serif;
            font-size: 4.5rem;
            font-weight: bold;
            color: var(--color-gold);
            margin-bottom: 10px;
            letter-spacing: 3px;
            text-transform: uppercase;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .club-title .dot {
            color: var(--color-dark-red);
        }
        
        .header .subtitle {
            font-size: 1.3rem;
            color: var(--color-deep-blue);
            font-weight: 300;
            max-width: 700px;
            margin: 0 auto;
        }
        .new-year-badge {
            display: inline-block;
            background: linear-gradient(45deg, var(--color-dark-red), var(--color-gold));
            color: white;
            padding: 8px 25px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 1.1rem;
            margin-top: 15px;
            letter-spacing: 1px;
        }

        /* Карточки форматов */
        .format-card {
            background: var(--color-white);
            border-left: 5px solid var(--color-gold);
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 35px;
            box-shadow: 0 8px 20px rgba(10, 26, 58, 0.08);
        }
        .format-card.premium {
            border-left-color: var(--color-dark-red);
        }
        .format-card h2 {
            font-size: 2.2rem;
            color: var(--color-deep-blue);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .format-card .tag {
            display: inline-block;
            background-color: var(--color-light-gold);
            color: var(--color-deep-blue);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 20px;
        }
        .format-card ul {
            list-style: none;
            padding-left: 0;
        }
        .format-card ul li {
            padding: 10px 0;
            padding-left: 30px;
            position: relative;
            border-bottom: 1px dashed #eee;
        }
        .format-card ul li:last-child { border-bottom: none; }
        .format-card ul li:before {
            content: '❄️';
            position: absolute;
            left: 0; top: 10px;
        }
        .price {
            font-weight: bold;
            color: var(--color-dark-red);
            margin-top: 15px;
            font-size: 1.2rem;
            padding: 15px;
            background: rgba(139, 0, 0, 0.05);
            border-radius: 10px;
            border-left: 3px solid var(--color-dark-red);
        }
        .price .highlight {
            color: var(--color-deep-blue);
            font-size: 1.1em;
        }

        /* КАРТА - ПРОФ.ПЛАН (оптимизировано для телефона) */
        .map-section {
            background: linear-gradient(135deg, #f8f4e9 0%, #fff 100%);
            border-radius: 15px;
            padding: 25px 20px;
            text-align: center;
            margin: 50px 0;
            border: 2px dashed var(--color-gold);
        }
        .map-section h2 {
            color: var(--color-deep-blue);
            font-size: 2rem;
            margin-bottom: 15px;
            word-break: keep-all;
            line-height: 1.3;
        }
        .map-section h2 .short {
            display: block;
            font-size: 1.7rem;
            color: var(--color-dark-red);
            margin-top: 5px;
        }
        .map-icon { 
            font-size: 2.5rem; 
            margin-bottom: 15px;
        }
        .map-section p {
            font-size: 1rem;
            line-height: 1.5;
            margin-bottom: 15px;
            text-align: left;
        }
        .map-section em {
            display: block;
            font-style: italic;
            color: var(--color-dark-red);
            margin-top: 20px;
            padding: 15px;
            background: rgba(212, 175, 55, 0.1);
            border-radius: 10px;
            border-left: 3px solid var(--color-gold);
        }

        /* Призыв к действию */
        .cta-section {
            text-align: center;
            margin-top: 60px;
            padding: 40px;
            background: linear-gradient(135deg, var(--color-deep-blue) 0%, #1a2d5a 100%);
            border-radius: 20px;
            color: white;
        }
        .cta-section h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--color-light-gold);
        }
        .telegram-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            background: linear-gradient(45deg, #0088cc, #24a2e0);
            color: white;
            padding: 18px 45px;
            font-size: 1.3rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            margin-top: 25px;
            transition: transform 0.3s;
        }
        .telegram-button:hover {
            transform: scale(1.05);
        }

        /* Подвал */
        .footer {
            text-align: center;
            margin-top: 60px;
            padding-top: 30px;
            border-top: 1px solid #eee;
        }
        
        .footer-logo {
            font-family: 'Georgia', 'Times New Roman', serif;
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--color-gold);
            letter-spacing: 3px;
            text-transform: uppercase;
        }
        .footer .only {
            font-size: 1.5rem;
            color: var(--color-dark-red);
            font-style: italic;
            letter-spacing: 5px;
            margin-top: -10px;
            font-family: 'Georgia', 'Times New Roman', serif;
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .container { 
                padding: 20px; 
                margin: 20px auto; 
                border-radius: 15px;
            }
            .club-title { 
                font-size: 3rem; 
                letter-spacing: 2px;
            }
            .header .subtitle { 
                font-size: 1.1rem; 
                padding: 0 10px;
            }
            .format-card { 
                padding: 20px; 
                margin-bottom: 25px;
            }
            .format-card h2 { 
                font-size: 1.8rem; 
                flex-wrap: wrap;
            }
            .format-card h2 span {
                margin-right: 10px;
            }
            .price {
                font-size: 1.1rem;
                padding: 12px;
            }
            
            /* Оптимизация карты для телефона */
            .map-section {
                padding: 20px 15px;
                margin: 40px 0;
                border-radius: 12px;
            }
            .map-section h2 {
                font-size: 1.7rem;
                line-height: 1.2;
            }
            .map-section h2 .short {
                font-size: 1.4rem;
            }
            .map-icon { 
                font-size: 2rem; 
                margin-bottom: 10px;
            }
            .map-section p {
                font-size: 0.95rem;
                line-height: 1.4;
                text-align: justify;
                hyphens: auto;
            }
            .map-section em {
                font-size: 0.9rem;
                padding: 12px;
                margin-top: 15px;
            }
            
            .cta-section { 
                padding: 30px 20px; 
                margin-top: 40px;
                border-radius: 15px;
            }
            .cta-section h2 { 
                font-size: 1.8rem; 
                line-height: 1.3;
            }
            .telegram-button { 
                padding: 15px 35px; 
                font-size: 1.1rem; 
                width: 100%;
                max-width: 300px;
            }
            .footer-logo { 
                font-size: 2.8rem; 
            }
            .footer .only {
                font-size: 1.2rem;
                letter-spacing: 3px;
            }
        }
        
        @media (max-width: 480px) {
            body {
                padding: 10px;
            }
            .container {
                padding: 15px;
                margin: 15px auto;
            }
            .club-title { 
                font-size: 2.5rem; 
            }
            .header .subtitle {
                font-size: 1rem;
            }
            .new-year-badge {
                font-size: 1rem;
                padding: 6px 20px;
            }
            
            /* Дальнейшая оптимизация карты */
            .map-section {
                padding: 15px 12px;
                margin: 30px 0;
            }
            .map-section h2 {
                font-size: 1.5rem;
            }
            .map-section h2 .short {
                font-size: 1.2rem;
            }
            .map-section p {
                font-size: 0.9rem;
                line-height: 1.3;
            }
            
            .format-card h2 {
                font-size: 1.5rem;
            }
            .price {
                font-size: 1rem;
            }
            .cta-section h2 {
                font-size: 1.6rem;
            }
            .telegram-button {
                padding: 12px 25px;
                font-size: 1rem;
            }
            .footer-logo { 
                font-size: 2.2rem; 
            }
        }
        
        @media (max-width: 360px) {
            .club-title {
                font-size: 2.2rem;
            }
            .map-section h2 {
                font-size: 1.3rem;
            }
            .map-section h2 .short {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <div class="snowflakes" id="snowflakes"></div>

    <div class="container">
        <header class="header">
            <div class="club-title">P<span class="dot">.</span>club</div>
            <div class="subtitle">
                Твой путь от теории к уверенной практике начинается здесь. Встречай 2026 год с новыми навыками и профессиональным сообществом.
            </div>
            <div class="new-year-badge">С НАСТУПАЮЩИМ 2026!</div>
        </header>

        <!-- Формат 1: Start in Action -->
        <section class="format-card">
            <div class="tag">СТАЖИРОВКА</div>
            <h2><span>🎯</span> Start in Action</h2>
            <p><strong>Формат:</strong> Включение в реальную сессию, практика в реальном времени, глубокий пост-разбор, постоянная онлайн-поддержка.</p>
            <div style="font-weight:600; color:#8b0000; margin-top:20px;">Результаты:</div>
            <ul>
                <li>Прямой опыт наблюдения и анализа сессии.</li>
                <li>Карта техник и понимание их применения.</li>
                <li>Поддержка сообщества — ты не одинок в профессии.</li>
                <li>Сертификат, подтверждающий реальные шаги в профессии.</li>
            </ul>
            <div class="price">
                <span class="highlight">ПАКЕТ ИЗ 7 СЕССИЙ:</span> 20.000₽ (+сертификат)
            </div>
        </section>

        <!-- Формат 2: Session Practicum -->
        <section class="format-card">
            <div class="tag">ПРАКТИКА С СУПЕРВИЗИЕЙ</div>
            <h2><span>🧠</span> Session Practicum</h2>
            <p><strong>Формат:</strong> Работа с реальным клиентом, сопровождение супервизора уровня PRO (10+ лет стажа), глубокий пост-разбор после каждой сессии, онлайн-поддержка.</p>
            <div style="font-weight:600; color:#8b0000; margin-top:20px;">Результаты:</div>
            <ul>
                <li>Уверенность в ведении сессий с клиентами.</li>
                <li>Понимание своих "зон силы" и зон роста.</li>
                <li>Формирование собственного профессионального взгляда.</li>
                <li>Честная обратная связь, которую не даст ни одна запись.</li>
                <li>Сертификат, подтверждающий опыт практики под супервизией.</li>
            </ul>
            <div class="price">
                <span class="highlight">ПАКЕТ ИЗ 5 ПРАКТИК:</span> 25.000₽ (+сертификат)
            </div>
        </section>

        <!-- Формат 3: Pro Launch -->
        <section class="format-card premium">
            <div class="tag">КОМПЛЕКСНЫЙ СТАРТ</div>
            <h2><span>🚀</span> Pro Launch: ПрофСтарт</h2>
            <p><strong>Формат:</strong> Включает стажировку и практику с супервизией, плюс карьерное сопровождение.</p>
            <div style="font-weight:600; color:#8b0000; margin-top:20px;">Что входит:</div>
            <ul>
                <li>Стажировка (реальные сессии, наблюдение, анализ).</li>
                <li>Практика (работа с клиентом под супервизией).</li>
                <li>Помощь в поиске первых клиентов и проведении пробных сессий.</li>
                <li>Стратегическая сессия по формированию клиентской базы.</li>
                <li>Поддержка в течение двух месяцев после завершения программы.</li>
                <li>Итоговый сертификат и портфолио опыта.</li>
            </ul>
            <div class="price">
                <span class="highlight">ПАКЕТ ИЗ 10 ПРАКТИК + стратегическая сессия:</span> 40.000₽ (возможна оплата по частям)
            </div>
        </section>

        <!-- Оптимизированная карта для телефона -->
        <section class="map-section">
            <div class="map-icon">🗺️</div>
            <h2>Профессиональный план <span class="short">(Проф.план)</span></h2>
            <p>Начните год с ясными целями. Это ваш инструмент для планирования пути от теории к практике.</p>
            <p>Заполните карту, чтобы определить свои ключевые точки роста на год вперед и увидеть, как программы P.club помогут вам в каждой из них.</p>
            <p>Проф.план включает этапы развития навыков, цели по клиентам и личные профессиональные метрики успеха.</p>
            <em>Карта станет вашим гидом и будет предоставлена сразу после начала работы.</em>
        </section>

        <!-- Призыв к действию -->
        <section class="cta-section">
            <h2>Начни свой 2026 год с P.club</h2>
            <p>Выбери формат, который соответствует твоим целям. Все детали по стоимости, датам старта и условиям участия обсудим лично.</p>
            <!-- ЗАМЕНЕНА ССЫЛКА НА ЛИЧНЫЙ ЧАТ -->
            <a href="https://t.me/annapsycho" class="telegram-button" target="_blank">
                <span>✈️</span> Написать в Telegram
            </a>
            <p style="margin-top:20px; font-size:1rem;">Кликни на кнопку, чтобы перейти в Telegram и узнать все условия.</p>
        </section>

        <footer class="footer">
            <div class="footer-logo">P.club</div>
            <span class="only">only</span>
        </footer>
    </div>

    <script>
        function createSnowflakes() {
            const container = document.getElementById('snowflakes');
            const count = 60;
            for (let i = 0; i < count; i++) {
                const flake = document.createElement('div');
                flake.classList.add('snowflake');
                flake.innerHTML = '❄';
                flake.style.left = Math.random() * 100 + 'vw';
                flake.style.animationDuration = (Math.random() * 5 + 5) + 's';
                flake.style.animationDelay = Math.random() * 5 + 's';
                flake.style.opacity = Math.random() * 0.5 + 0.3;
                flake.style.fontSize = (Math.random() * 10 + 10) + 'px';
                container.appendChild(flake);
            }
        }
        document.addEventListener('DOMContentLoaded', createSnowflakes);
    </script>
</body>
</html>
