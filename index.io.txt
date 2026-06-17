<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Telegram App</title>
    <!-- Подключаем скрипт Telegram -->
    <script src="https://telegram.org"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: var(--tg-theme-bg-color, #ffffff);
            color: var(--tg-theme-text-color, #000000);
            text-align: center;
            padding: 20px;
        }
        button {
            padding: 10px 20px;
            background-color: var(--tg-theme-button-color, #2481cc);
            color: var(--tg-theme-button-text-color, #ffffff);
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Привет, <span id="username">Гость</span>!</h1>
    <p>Это твое первое мини-приложение.</p>
    <button onclick="closeApp()">Закрыть приложение</button>

    <script>
        // Инициализируем Telegram Web App
        const tg = window.Telegram.WebApp;
        tg.expand(); // Расширяем на весь экран

        // Показываем имя пользователя, если оно есть
        if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
            document.getElementById('username').innerText = tg.initDataUnsafe.user.first_name;
        }

        // Функция закрытия
        function closeApp() {
            tg.close();
        }
    </script>
</body>
</html>
