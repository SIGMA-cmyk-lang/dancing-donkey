<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Танцующий ослик на горе</title>
    <style>
        /* Стили для страницы */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
            background-color: #f0f0f0;
        }

        #show-donkey {
            font-size: 20px;
            color: blue;
            text-decoration: none;
        }

        #show-donkey:hover {
            text-decoration: underline;
        }

        /* Модальное окно */
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
        }

        .modal-content {
            position: relative;
            margin: 10% auto;
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            text-align: center;
            width: 60%;
        }

        .close {
            color: #aaa;
            font-size: 28px;
            font-weight: bold;
            position: absolute;
            top: 0;
            right: 20px;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }

        /* Анимация ослика на горе */
        .donkey-container {
            position: relative;
            margin-top: 20px;
            font-size: 80px;
            animation: dance 1s infinite alternate;
        }

        .donkey {
            display: inline-block;
            animation: jump 1.5s infinite;
        }

        .mountain {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            height: 200px;
            background: linear-gradient(to top, #7f8c8d, #2c3e50);
            border-radius: 50%;
        }

        @keyframes dance {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }

        @keyframes jump {
            0% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
            100% {
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>

    <!-- Ссылка на модальное окно -->
    <a href="#" id="show-donkey">Смотреть видео</a>

    <!-- Модальное окно с танцующим осликом -->
    <div id="donkey-modal" class="modal">
        <div class="modal-content">
            <span id="close" class="close">&times;</span>
            <div class="donkey-container">
                <div class="mountain"></div>
                <div class="donkey">🦙</div>
            </div>
        </div>
    </div>

    <script>
        // Получаем элементы
        const modal = document.getElementById('donkey-modal');
        const showDonkeyButton = document.getElementById('show-donkey');
        const closeButton = document.getElementById('close');

        // Открытие модального окна при клике на ссылку
        showDonkeyButton.onclick = function(event) {
            event.preventDefault(); // Отменяем стандартное поведение ссылки
            modal.style.display = 'block';
        };

        // Закрытие модального окна
        closeButton.onclick = function() {
            modal.style.display = 'none';
        };

        // Закрытие модального окна при клике вне его области
        window.onclick = function(event) {
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        };
    </script>

</body>
</html>
