<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🔥 КРУТОЙ СЮРПРИЗ 🔥</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow: hidden;
            height: 100vh;
            width: 100vw;
            font-family: 'Arial', sans-serif;
        }
        
        /* Стартовый экран */
        .start-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            transition: opacity 0.8s;
        }
        
        .start-screen.hidden {
            opacity: 0;
            pointer-events: none;
        }
        
        .content {
            text-align: center;
            padding: 20px;
            cursor: pointer;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        h1 {
            color: white;
            font-size: 4em;
            margin-bottom: 30px;
            text-shadow: 0 0 30px rgba(255,255,255,0.5);
            animation: glow 1.5s infinite;
        }
        
        @keyframes glow {
            0% { text-shadow: 0 0 30px rgba(255,255,255,0.5); }
            50% { text-shadow: 0 0 60px rgba(255,255,255,0.8); }
            100% { text-shadow: 0 0 30px rgba(255,255,255,0.5); }
        }
        
        .subtitle {
            color: white;
            font-size: 2em;
            margin-bottom: 50px;
            opacity: 0.9;
        }
        
        .click-box {
            background: rgba(255,255,255,0.2);
            border: 3px solid white;
            border-radius: 50px;
            padding: 30px 60px;
            display: inline-block;
            box-shadow: 0 0 50px rgba(255,255,255,0.3);
        }
        
        .click-text {
            color: white;
            font-size: 2.5em;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 5px;
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }
        
        .mouse-icon {
            font-size: 3em;
            margin-top: 20px;
            color: white;
            animation: move 1s infinite;
        }
        
        @keyframes move {
            0% { transform: translateY(0); }
            50% { transform: translateY(10px); }
            100% { transform: translateY(0); }
        }
        
        .hint {
            color: white;
            margin-top: 40px;
            font-size: 1.2em;
            opacity: 0.7;
        }
        
        /* Видео контейнер (скрыт до клика) */
        .video-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            opacity: 0;
            transition: opacity 0.5s;
            pointer-events: none;
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
        }
        
        .rick-text {
            color: #ff0000;
            font-size: 4vw;
            font-weight: bold;
            text-shadow: 0 0 40px #ff0000;
            animation: shake 0.2s infinite;
        }
        
        @keyframes shake {
            0% { transform: translate(2px, 2px); }
            25% { transform: translate(-2px, -2px); }
            50% { transform: translate(-2px, 2px); }
            75% { transform: translate(2px, -2px); }
            100% { transform: translate(0, 0); }
        }
        
        /* Скрываем элементы управления */
        video::-webkit-media-controls {
            display: none !important;
        }
    </style>
</head>
<body>
    <!-- Стартовый экран с призывом кликнуть -->
    <div class="start-screen" id="startScreen">
        <div class="content" onclick="showSurprise()">
            <h1>🎁 КРУТОЙ СЮРПРИЗ 🎁</h1>
            <div class="subtitle">ТОЛЬКО ДЛЯ ТЕБЯ!</div>
            
            <div class="click-box">
                <div class="click-text">НАЖМИ МЫШКУ</div>
                <div class="mouse-icon">🖱️</div>
            </div>
            
            <div class="hint">ЧТОБЫ ПОЛУЧИТЬ ЧТО-ТО КРУТОЕ</div>
        </div>
    </div>
    
    <!-- Видео контейнер (появляется после клика) -->
    <div class="video-container" id="videoContainer">
        <video id="rickrollVideo" loop playsinline>
            <source src="https://github.com/RomaMakarov/rickrool/raw/main/rickroll_5y6r4Tso.mp4" type="video/mp4">
        </video>
        
        <div class="overlay">
            <div class="rick-text">🎵 NEVER GONNA GIVE YOU UP! 🎵</div>
        </div>
    </div>

    <script>
        const startScreen = document.getElementById('startScreen');
        const videoContainer = document.getElementById('videoContainer');
        const video = document.getElementById('rickrollVideo');
        
        function showSurprise() {
            // Прячем стартовый экран
            startScreen.classList.add('hidden');
            
            // Показываем видео контейнер
            videoContainer.classList.add('show');
            
            // Запускаем видео со звуком
            video.muted = false;
            video.volume = 1.0;
            
            // Форсированный запуск
            const playVideo = () => {
                video.play()
                    .then(() => {
                        console.log('✅ СЮРПРИЗ АКТИВИРОВАН!');
                    })
                    .catch(error => {
                        console.log('⏳ Пробуем снова...');
                        setTimeout(playVideo, 100);
                    });
            };
            
            playVideo();
            
            // Добавляем эффект вибрации если поддерживается
            if (navigator.vibrate) {
                navigator.vibrate([200, 100, 200]);
            }
            
            // Меняем заголовок вкладки
            document.title = '🎵 RICKROLL 🎵';
        }
        
        // Предзагружаем видео
        window.onload = () => {
            video.load();
        };
    </script>
</body>
</html>
