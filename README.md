<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
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
            -webkit-text-size-adjust: 100%;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        html {
            overflow-x: hidden;
            width: 100%;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            color: var(--color-deep-blue);
            background-color: var(--color-deep-blue);
            line-height: 1.5;
            padding: 15px;
            min-height: 100vh;
            position: relative;
            width: 100%;
            overflow-x: hidden;
            -webkit-overflow-scrolling: touch;
        }

        /* Контейнер с исправлениями для мобильных */
        .container {
            max-width: 100%;
            margin: 20px auto;
            background: rgba(255, 255, 255, 0.98);
            border-radius: 16px;
            box-shadow: 0 8px 25px rgba(10, 26, 58, 0.2);
            border: 2px solid var(--color-gold);
            padding: 20px;
            position: relative;
            z-index: 2;
            overflow: hidden;
            width: 100%;
            word-wrap: break-word;
            overflow-wrap: break-word;
            hyphens: auto;
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

        /* Шапка - исправлено для мобильных */
        .header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px dashed var(--color-gold);
        }
        
        /* Шрифт P.club с исправлениями */
        .club-title {
            font-family: 'Georgia', 'Times New Roman', serif;
            font-size: 2.8rem;
            font-weight: bold;
            color: var(--color-gold);
            margin-bottom: 10px;
            letter-spacing: 1px;
            text-transform: uppercase;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
            line-height: 1.2;
            word-break: break-word;
            padding: 0 10px;
        }
        
        .club-title .dot {
            color: var(--color-dark-red);
        }
        
        .header .subtitle {
            font-size: 1.1rem;
            color: var(--color-deep-blue);
            font-weight: 300;
            max-width: 100%;
            margin: 0 auto 15px;
            line-height: 1.4;
            padding: 0 10px;
            word-break: break-word;
        }
        .new-year-badge {
            display: inline-block;
            background: linear-gradient(45deg, var(--color-dark-red), var(--color-gold));
            color: white;
            padding: 8px 20px;
            border-radius: 25px;
            font-weight: 600;
            font-size: 1rem;
            margin-top: 10px;
            letter-spacing: 0.5px;
            max-width: 90%;
            word-break: break-word;
            white-space: normal;
            text-align: center;
        }

        /* Карточки форматов - оптимизировано */
        .format-card {
            background: var(--color-white);
            border-left: 4px solid var(--color-gold);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 25px;
            box-shadow: 0 4px 15px rgba(10, 26, 58, 0.08);
            overflow: hidden;
            width: 100%;
        }
        .format-card.premium {
            border-left-color: var(--color-dark-red);
        }
        .format-card .tag {
            display: inline-block;
            background-color: var(--color-light-gold);
            color: var(--color-deep-blue);
            padding: 5px 12px;
            border-radius: 18px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 15px;
            width: 100%;
            text-align: center;
        }
        .format-card h2 {
            font-size: 1.6rem;
            color: var(--color-deep-blue);
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
            flex-wrap: wrap;
            line-height: 1.3;
            word-break: break-word;
        }
        .format-card h2 span {
            font-size: 1.8rem;
            min-width: 40px;
        }
        .format-card p {
            font-size: 0.95rem;
            line-height: 1.4;
            margin-bottom: 15px;
            word-break: break-word;
        }
        .format-card p strong {
            color: var(--color-dark-red);
        }
        .format-card ul {
            list-style: none;
            padding-left: 0;
            margin: 15px 0;
        }
        .format-card ul li {
            padding: 8px 0;
            padding-left: 28px;
            position: relative;
            border-bottom: 1px dashed #eee;
            font-size: 0.9rem;
            line-height: 1.4;
            word-break: break-word;
        }
        .format-card ul li:last-child { 
            border-bottom: none; 
        }
        .format-card ul li:before {
            content: '❄️';
            position: absolute;
            left: 0; 
            top: 8px;
            font-size: 0.9rem;
        }
        .results-title {
            font-weight: 600;
            color: var(--color-dark-red);
            margin-top: 20px;
            font-size: 1rem;
            display: block;
        }

        /* Цены - исправлено */
        .price {
            font-weight: bold;
            color: var(--color-dark-red);
            margin-top: 20px;
            font-size: 1rem;
            padding: 12px;
            background: rgba(139, 0, 0, 0.05);
            border-radius: 8px;
            border-left: 3px solid var(--color-dark-red);
            text-align: center;
            word-break: break-word;
            line-height: 1.4;
        }
        .price .highlight {
            color: var(--color-deep-blue);
            font-size: 1.05em;
            display: block;
            margin-bottom: 5px;
            font-weight: 700;
        }

        /* КАРТА - ПРОФ.ПЛАН */
        .map-section {
            background: linear-gradient(135deg, #f8f4e9 0%, #fff 100%);
            border-radius: 12px;
            padding: 20px 15px;
            text-align: center;
            margin: 30px 0;
            border: 2px dashed var(--color-gold);
            width: 100%;
        }
        .map-section h2 {
            color: var(--color-deep-blue);
            font-size: 1.5rem;
            margin-bottom: 12px;
            line-height: 1.3;
            word-break: break-word;
            padding: 0 5px;
        }
        .map-section h2 .short {
            display: block;
            font-size: 1.3rem;
            color: var(--color-dark-red);
            margin-top: 5px;
        }
        .map-icon { 
            font-size: 2rem; 
            margin-bottom: 12px;
        }
        .map-section p {
            font-size: 0.9rem;
            line-height: 1.4;
            margin-bottom: 12px;
            text-align: left;
            word-break: break-word;
        }
        .map-section em {
            display: block;
            font-style: italic;
            color: var(--color-dark-red);
            margin-top: 15px;
            padding: 12px;
            background: rgba(212, 175, 55, 0.1);
            border-radius: 8px;
            border-left: 3px solid var(--color-gold);
            font-size: 0.85rem;
            line-height: 1.4;
            word-break: break-word;
        }

        /* Призыв к действию */
        .cta-section {
            text-align: center;
            margin-top: 40px;
            padding: 25px 15px;
            background: linear-gradient(135deg, var(--color-deep-blue) 0%, #1a2d5a 100%);
            border-radius: 16px;
            color: white;
            width: 100%;
        }
        .cta-section h2 {
            font-size: 1.6rem;
            margin-bottom: 15px;
            color: var(--color-light-gold);
            line-height: 1.3;
            word-break: break-word;
            padding: 0 5px;
        }
        .cta-section p {
            font-size: 0.95rem;
            line-height: 1.4;
            margin-bottom: 15px;
            word-break: break-word;
        }
        .telegram-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            background: linear-gradient(45deg, #0088cc, #24a2e0);
            color: white;
            padding: 14px 30px;
            font-size: 1.1rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            margin-top: 15px;
            transition: transform 0.3s;
            width: 90%;
            max-width: 300px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .telegram-button:hover {
            transform: scale(1.05);
        }
        .telegram-button span {
            font-size: 1.2rem;
        }

        /* Подвал */
        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 25px;
            border-top: 1px solid #eee;
            width: 100%;
        }
        
        .footer-logo {
            font-family: 'Georgia', 'Times New Roman', serif;
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--color-gold);
            letter-spacing: 2px;
            text-transform: uppercase;
            line-height: 1.2;
            word-break: break-word;
        }
        .footer .only {
            font-size: 1.2rem;
            color: var(--color-dark-red);
            font-style: italic;
            letter-spacing: 3px;
            margin-top: -5px;
            font-family: 'Georgia', 'Times New Roman', serif;
            display: block;
        }

        /* Адаптивность для очень маленьких экранов */
        @media (max-width: 480px) {
            body {
                padding: 10px;
            }
            .container {
                padding: 15px;
                margin: 15px auto;
                border-radius: 14px;
            }
            .club-title { 
                font-size: 2.2rem; 
                letter-spacing: 0.5px;
                padding: 0 5px;
            }
            .header .subtitle {
                font-size: 1rem;
                padding: 0 5px;
            }
            .new-year-badge {
                font-size: 0.9rem;
                padding: 6px 15px;
                max-width: 95%;
            }
            
            .format-card { 
                padding: 15px; 
                margin-bottom: 20px;
            }
            .format-card h2 { 
                font-size: 1.4rem; 
            }
            .format-card h2 span {
                font-size: 1.6rem;
                min-width: 35px;
            }
            .format-card p {
                font-size: 0.9rem;
            }
            .format-card ul li {
                font-size: 0.85rem;
                padding-left: 25px;
            }
            
            .map-section {
                padding: 15px 12px;
                margin: 25px 0;
            }
            .map-section h2 {
                font-size: 1.3rem;
            }
            .map-section h2 .short {
                font-size: 1.1rem;
            }
            .map-section p {
                font-size: 0.85rem;
            }
            
            .cta-section { 
                padding: 20px 12px; 
                margin-top: 30px;
            }
            .cta-section h2 { 
                font-size: 1.4rem; 
            }
            .telegram-button {
                padding: 12px 25px;
                font-size: 1rem;
                width: 95%;
            }
            .footer-logo { 
                font-size: 2rem; 
            }
            .footer .only {
                font-size: 1rem;
                letter-spacing: 2px;
            }
        }

        @media (max-width: 360px) {
            .club-title {
                font-size: 1.8rem;
            }
            .format-card h2 {
                font-size: 1.2rem;
            }
            .map-section h2 {
                font-size: 1.1rem;
            }
            .map-section h2 .short {
                font-size: 1rem;
            }
            .cta-section h2 {
                font-size: 1.2rem;
            }
        }

        /* Для очень высоких экранов */
        @media (min-height: 800px) and (max-width: 480px) {
            .container {
                margin: 30px auto;
                padding: 25px 20px;
            }
        }

        /* Исправление горизонтального скролла */
        @media (max-width: 767px) {
            html, body {
                max-width: 100%;
                overflow-x: hidden;
            }
            .container * {
                max-width: 100%;
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
            <span class="results-title">Результаты:</span>
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
            <span class="results-title">Результаты:</span>
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
            <span class="results-title">Что входит:</span>
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

        <!-- Карта -->
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
            <a href="https://t.me/annapsycho" class="telegram-button" target="_blank" rel="noopener noreferrer">
                <span>✈️</span> Написать в Telegram
            </a>
            <p style="margin-top:15px; font-size:0.9rem; opacity:0.9;">Кликни на кнопку, чтобы перейти в Telegram и узнать все условия.</p>
        </section>

        <footer class="footer">
            <div class="footer-logo">P.club</div>
            <span class="only">only</span>
        </footer>
    </div>

    <script>
        function createSnowflakes() {
            const container = document.getElementById('snowflakes');
            const count = 40; // Уменьшил количество для мобильных
            for (let i = 0; i < count; i++) {
                const flake = document.createElement('div');
                flake.classList.add('snowflake');
                flake.innerHTML = '❄';
                flake.style.left = Math.random() * 100 + 'vw';
                flake.style.animationDuration = (Math.random() * 5 + 5) + 's';
                flake.style.animationDelay = Math.random() * 5 + 's';
                flake.style.opacity = Math.random() * 0.5 + 0.3;
                flake.style.fontSize = (Math.random() * 8 + 8) + 'px';
                container.appendChild(flake);
            }
        }
        
        // Загрузка снежинок после загрузки DOM
        if (document.readyState === 'loading') {
            document.addEventListener('DOMContentLoaded', createSnowflakes);
        } else {
            createSnowflakes();
        }
        
        // Исправление viewport для iOS
        if (navigator.userAgent.match(/iPhone|iPad|iPod/i)) {
            const viewport = document.querySelector('meta[name="viewport"]');
            if (viewport) {
                viewport.content = viewport.content + ', shrink-to-fit=no';
            }
        }
        
        // Предотвращение масштабирования на двойной тап
        let lastTouchEnd = 0;
        document.addEventListener('touchend', function(event) {
            const now = (new Date()).getTime();
            if (now - lastTouchEnd <= 300) {
                event.preventDefault();
            }
            lastTouchEnd = now;
        }, false);
    </script>
</body>
</html>
