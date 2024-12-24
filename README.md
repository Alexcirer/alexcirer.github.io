<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Get Key</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background-color: #1e1e1e;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            width: 90%;
            max-width: 400px;
        }
        .container h1 {
            font-size: 24px;
            margin-bottom: 10px;
        }
        .container p {
            font-size: 14px;
            color: #b0b0b0;
            margin-bottom: 20px;
        }
        .button {
            background-color: #00b894;
            color: #ffffff;
            border: none;
            border-radius: 5px;
            padding: 10px 20px;
            font-size: 16px;
            margin-bottom: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            transition: background-color 0.3s;
        }
        .button i {
            margin-right: 10px;
        }
        .button.loading {
            animation: blink 0.5s step-end infinite alternate;
        }
        @keyframes blink {
            50% {
                background-color: #00a383;
            }
        }
        .progress {
            background-color: #333333;
            border-radius: 5px;
            overflow: hidden;
            margin-bottom: 20px;
        }
        .progress-bar {
            background-color: #00b894;
            height: 5px;
            width: 0;
            transition: width 0.3s;
        }
        .unlock-button {
            background-color: #555555;
            color: #b0b0b0;
            border: none;
            border-radius: 5px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: not-allowed;
            width: 100%;
        }
        .unlock-button.enabled {
            background-color: #00b894;
            color: #ffffff;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Get Key 2/2</h1>
        <p>Complete the actions to unlock</p>
        <button class="button" onclick="visitPage(this)"><i class="fas fa-link"></i> Visit a page</button>
        <button class="button" onclick="visitPage(this)"><i class="fas fa-link"></i> Visit a page</button>
        <button class="button" onclick="visitPage(this)"><i class="fas fa-link"></i> Visit a page</button>
        <button class="button" onclick="visitPage(this)"><i class="fas fa-link"></i> Visit a page</button>
        <div class="progress">
            <div class="progress-bar" id="progress-bar"></div>
        </div>
        <p id="progress-text">unlock progress 0/4</p>
        <button class="unlock-button" id="unlock-button" onclick="unlockLink()">Unlock link</button>
    </div>

    <script>
        let progress = 0;
        const totalTasks = 4;

        function visitPage(button) {
            if (button.classList.contains('loading')) return;

            button.classList.add('loading');
            setTimeout(() => {
                button.classList.remove('loading');
                progress++;
                updateProgress();
            }, 6500);
        }

        function updateProgress() {
            const progressBar = document.getElementById('progress-bar');
            const progressText = document.getElementById('progress-text');
            const unlockButton = document.getElementById('unlock-button');

            const progressPercentage = (progress / totalTasks) * 100;
            progressBar.style.width = progressPercentage + '%';
            progressText.textContent = `unlock progress ${progress}/${totalTasks}`;

            if (progress === totalTasks) {
                unlockButton.classList.add('enabled');
                unlockButton.disabled = false;
                unlockButton.style.cursor = 'pointer';
            }
        }

        function unlockLink() {
            if (progress === totalTasks) {
                window.location.href = 'https://example.com/unlock-link';
            }
        }
    </script>
</body>
</html>
