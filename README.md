<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мегафон</title>
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: #00b956;
        color: #000;
        overflow-x: hidden;
    }

    header {
        position: relative;
        background: #fff;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        padding: 10px;
        text-align: center;
    }

    header img {
        height: 40px;
    }

    .search-container {
        text-align: center;
        margin: 20px 0;
    }

    .search-container input {
        width: 80%;
        padding: 10px;
        font-size: 16px;
        border: none;
        border-radius: 8px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    }

    .buttons-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
        margin: 20px;
    }

    .button {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        width: 150px;
        padding: 10px;
        background-color: #fff;
        color: #000;
        border-radius: 8px;
        text-decoration: none;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        transition: transform 0.2s, box-shadow 0.2s;
    }

    .button:hover {
        transform: translateY(-4px);
        box-shadow: 0 8px 12px rgba(0, 0, 0, 0.2);
    }

    /* Background animation */
    .background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        z-index: -1;
    }

    .circle-animation {
        position: absolute;
        width: 10px;
        height: 10px;
        background-color: rgba(255, 255, 255, 0.5);
        border-radius: 50%;
        opacity: 0.7;
        animation: move 10s linear infinite;
    }

    @keyframes move {
        from {
            transform: translateY(-10px) translateX(0);
        }
        to {
            transform: translateY(100vh) translateX(calc(100vw - 10px));
        }
    }
</style>
</head>
<body>
    <div class="background">
        <!-- Generate multiple animated circles -->
        <script>
            for (let i = 0; i < 50; i++) {
                const circle = document.createElement('div');
                circle.classList.add('circle-animation');
                circle.style.left = `${Math.random() * 100}vw`;
                circle.style.animationDuration = `${5 + Math.random() * 10}s`;
                circle.style.animationDelay = `${Math.random() * 5}s`;
                document.body.querySelector('.background').appendChild(circle);
            }
        </script>
    </div>

    <header>
        <div class="circle"></div>
        <img src="logo.png" alt="Логотип Мегафон">
    </header>

    <div class="search-container">
        <input type="text" id="search" placeholder="Поиск по языкам..." oninput="filterButtons()">
    </div>

    <div class="buttons-container" id="buttons-container">
        <a href="Азербайджанский.pdf" class="button">Azərbaycan <span class="subtext">Азербайджанский</span></a>
        <a href="Английский.pdf" class="button">English <span class="subtext">Английский</span></a>
        <a href="Арабский.pdf" class="button">العربية <span class="subtext">Арабский</span></a>
        <a href="Армянский.pdf" class="button">Հայերեն <span class="subtext">Армянский</span></a>
        <a href="Хинди.pdf" class="button">हिंदी <span class="subtext">Хинди</span></a>
        <a href="Буклет_инструкция_на_русском_языке.pdf" class="button">Русский <span class="subtext">Русский</span></a>
        <a href="Вьетнамский.pdf" class="button">Tiếng Việt <span class="subtext">Вьетнамский</span></a>
        <a href="Испанский.pdf" class="button">Español <span class="subtext">Испанский</span></a>
        <a href="Итальянский.pdf" class="button">Italiano <span class="subtext">Итальянский</span></a>
        <a href="Киргизский.pdf" class="button">Кыргызча <span class="subtext">Киргизский</span></a>
        <a href="Китайский.pdf" class="button">中文 <span class="subtext">Китайский</span></a>
        <a href="Монгольский.pdf" class="button">Монгол <span class="subtext">Монгольский</span></a>

    </div>

    <script>
        function filterButtons() {
            const query = document.getElementById('search').value.toLowerCase();
            const buttons = document.querySelectorAll('.button');
            buttons.forEach(button => {
                const text = button.textContent.toLowerCase();
                if (text.includes(query)) {
                    button.style.display = 'flex';
                } else {
                    button.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>
