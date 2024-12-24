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
        }
        .button i {
            margin-right: 10px;
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
    </style>
</head>
<body>
    <div class="container">
        <h1>Get Key 2/2</h1>
        <p>Complete the actions to unlock</p>
        <button class="button"><i class="fas fa-link"></i> Visit a page</button>
        <button class="button"><i class="fas fa-link"></i> Visit a page</button>
        <div class="progress">
            <div class="progress-bar" style="width: 0%;"></div>
        </div>
        <p>unlock progress 0/2</p>
        <button class="unlock-button">Unlock link</button>
    </div>
</body>
</html>
