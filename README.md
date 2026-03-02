<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>🔥 ТОЛЬКО ДЛЯ ТЕБЯ 🔥</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }
        
        body {
            background: linear-gradient(135deg, #ff6b6b, #4ecdc4);
            overflow: hidden;
            height: 100vh;
            width: 100vw;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            position: fixed;
            cursor: default;
        }
        
        /* Стартовый экран */
        .start-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #ff6b6b, #4ecdc4);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            transition: opacity 0.5s;
        }
        
        .start-screen.hidden {
            opacity: 0;
            pointer-events: none;
        }
        
        .content {
            text-align: center;
            padding: 20px;
            cursor: pointer;
            width: 100%;
            max-width: 700px;
            animation: float 3s infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        h1 {
            color: white;
            font-size: clamp(2.5rem, 10vw, 5rem);
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(0,0,0,0.3);
            animation: glow 1.5s infinite;
            font-weight: bold;
            line-height: 1.2;
        }
        
        @keyframes glow {
            0% { text-shadow: 0 0 30px rgba(255,255,255,0.5); }
            50% { text-shadow: 0 0 60px rgba(255,255,255,0.8); }
            100% { text-shadow: 0 0 30px rgba(255,255,255,0.5); }
        }
        
        .personal-message {
            background: rgba(255,255,255,0.2);
            border: 3px solid white;
            border-radius: 30px;
            padding: 20px 40px;
            margin: 30px auto;
            display: inline-block;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }
        
        .personal-message h2 {
            color: white;
            font-size: clamp(2rem, 7vw, 3.5rem);
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 3px;
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.05); }
            100% { opacity: 1; transform: scale(1); }
        }
        
        .surprise-box {
            background: rgba(255,255,255,0.2);
            border: 3px solid white;
            border-radius: 50px;
            padding: clamp(25px, 6vw, 50px) clamp(40px, 10vw, 100px);
            display: inline-block;
            box-shadow: 0 0 80px rgba(255,255,255,0.4);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            transition: all 0.3s;
            margin: 30px auto;
        }
        
        .surprise-box:hover {
            transform: scale(1.1);
            box-shadow: 0 0 120px rgba(255,255,255,0.6);
        }
        
        .surprise-text {
            color: white;
            font-size: clamp(2rem, 7vw, 3.5rem);
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 4px;
            animation: pulse 1s infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 0.9; }
            50% { opacity: 1; }
            100% { opacity: 0.9; }
        }
        
        .icon {
            font-size: clamp(3rem, 10vw, 5rem);
            margin-top: 20px;
            color: white;
            animation: bounce 1s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        .secret-text {
            color: white;
            margin-top: 40px;
            font-size: clamp(1rem, 3vw, 1.3rem);
            opacity: 0.9;
            font-style: italic;
        }
        
        /* Видео контейнер */
        .video-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            opacity: 0;
            transition: opacity 0.3s;
            pointer-events: none;
            background: #000;
        }
        
        .video-container.show {
            opacity: 1;
            pointer-events: auto;
        }
        
        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.3);
            z-index: 2;
            pointer-events: none;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
        }
        
        .personal-rick {
            color: #ff0000;
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: bold;
            text-shadow: 0 0 40px #ff0000, 0 0 80px #ff0000;
            animation: shake 0.2s infinite;
            line-height: 1.3;
            -webkit-text-stroke: 2px white;
            margin-bottom: 20px;
        }
        
        @keyframes shake {
            0% { transform: translate(3px, 3px); }
            25% { transform: translate(-3px, -3px); }
            50% { transform: translate(-3px, 3px); }
            75% { transform: translate(3px, -3px); }
            100% { transform: translate(0, 0); }
        }
        
        .personal-sub {
            color: white;
            font-size: clamp(1.2rem, 4vw, 2rem);
            text-shadow: 0 0 30px #ff0000;
            animation: fade 2s infinite;
        }
        
        @keyframes fade {
            0%, 100% { opacity: 0.8; }
            50% { opacity: 1; }
        }
        
        /* Скрываем элементы управления */
        video::-webkit-media-controls {
            display: none !important;
        }
    </style>
</head>
<body>
    <!-- Персональный стартовый экран -->
    <div class="start-screen" id="startScreen" onclick="showSurprise()" ontouchstart="showSurprise()">
        <div class="content">
            <h1>🎁 ОСОБЫЙ СЮРПРИЗ 🎁</h1>
            
            <div class="personal-message">
                <h2>ТОЛЬКО ДЛЯ ТЕБЯ!</h2>
            </div>
            
            <div class="surprise-box">
                <div class="surprise-text" id="actionText">НАЖМИ СЮДА</div>
                <div class="icon" id="deviceIcon">🎯</div>
            </div>
            
            <div class="secret-text" id="secretMessage">
                ✨ Этот сюрприз создан специально для тебя ✨
            </div>
        </div>
    </div>
    
    <!-- Видео контейнер -->
    <div class="video-container" id="videoContainer">
        <video id="rickrollVideo" loop playsinline webkit-playsinline x5-playsinline>
            <source src="https://github.com/RomaMakarov/rickrool/raw/main/rickroll_5y6r4Tso.mp4" type="video/mp4">
        </video>
        
        <div class="overlay">
            <div class="personal-rick" id="personalRickText">🎵 ТЕБЯ ЗАРИКРОЛИЛИ! 🎵</div>
            <div class="personal-sub" id="personalSubText">это только для тебя</div>
        </div>
    </div>

    <script>
        const startScreen = document.getElementById('startScreen');
        const videoContainer = document.getElementById('videoContainer');
        const video = document.getElementById('rickrollVideo');
        const personalRickText = document.getElementById('personalRickText');
        const personalSubText = document.getElementById('personalSubText');
        const actionText = document.getElementById('actionText');
        const deviceIcon = document.getElementById('deviceIcon');
        const secretMessage = document.getElementById('secretMessage');
        
        // Определяем устройство
        const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
        
        // Массив персональных сообщений
        const rickMessages = [
            "🎵 ТЕБЯ ЗАРИКРОЛИЛИ! 🎵",
            "🎶 ЭТО ТОЛЬКО ДЛЯ ТЕБЯ! 🎶",
            "🔥 ТЫ ПОПАЛСЯ! 🔥",
            "⭐ ТВОЙ ПЕРСОНАЛЬНЫЙ RICKROLL ⭐",
            "🎵 NEVER GONNA GIVE YOU UP! 🎵",
            "💫 ТОЛЬКО ТЫ И RICKROLL 💫"
        ];
        
        const subMessages = [
            "теперь ты часть истории",
            "этот момент только твой",
            "помни этот день",
            "рискролл навсегда",
            "никогда не сдавайся",
            "ты это заслужил"
        ];
        
        // Настраиваем текст под устройство
        if (isMobile) {
            actionText.textContent = 'ТАПНИ ПАЛЬЦЕМ';
            deviceIcon.textContent = '👉';
            secretMessage.textContent = '✨ Персонально для тебя на телефоне ✨';
        } else {
            actionText.textContent = 'КЛИКНИ МЫШКОЙ';
            deviceIcon.textContent = '🎯';
            secretMessage.textContent = '✨ Персонально для тебя на ПК ✨';
        }
        
        let messageIndex = 0;
        let subIndex = 0;
        
        function showSurprise() {
            // Прячем стартовый экран
            startScreen.classList.add('hidden');
            
            // Показываем видео
            videoContainer.classList.add('show');
            
            // Вибрация для телефона
            if (isMobile && navigator.vibrate) {
                navigator.vibrate([200, 100, 200, 100, 300]);
            }
            
            // Настройки видео
            video.muted = false;
            video.volume = 1.0;
            
            // Запускаем видео
            const playVideo = () => {
                video.play()
                    .then(() => {
                        console.log('✅ ПЕРСОНАЛЬНЫЙ RICKROLL АКТИВИРОВАН');
                        
                        // Меняем сообщения
                        setInterval(() => {
                            messageIndex = (messageIndex + 1) % rickMessages.length;
                            subIndex = (subIndex + 1) % subMessages.length;
                            
                            personalRickText.style.opacity = '0';
                            personalSubText.style.opacity = '0';
                            
                            setTimeout(() => {
                                personalRickText.textContent = rickMessages[messageIndex];
                                personalSubText.textContent = subMessages[subIndex];
                                personalRickText.style.opacity = '1';
                                personalSubText.style.opacity = '1';
                            }, 200);
                        }, 2500);
                    })
                    .catch(error => {
                        console.log('⏳ Пробуем снова...');
                        setTimeout(playVideo, 100);
                    });
            };
            
            playVideo();
            setTimeout(playVideo, 300);
            
            // Меняем заголовок
            document.title = '🎵 ТОЛЬКО ДЛЯ ТЕБЯ 🎵';
        }
        
        // Предзагрузка видео
        window.onload = () => {
            video.load();
        };
        
        // Защита от скролла
        document.body.addEventListener('touchmove', (e) => {
            e.preventDefault();
        }, { passive: false });
        
        document.addEventListener('contextmenu', (e) => {
            e.preventDefault();
        });
    </script>
</body>
</html>