<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>World Clock</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        .clock {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }
        .city {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .time {
            font-size: 2em;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="clock">
        <div class="city" id="new-york">
            <div>New York</div>
            <div class="time" id="new-york-time"></div>
        </div>
        <div class="city" id="london">
            <div>London</div>
            <div class="time" id="london-time"></div>
        </div>
        <div class="city" id="tokyo">
            <div>Tokyo</div>
            <div class="time" id="tokyo-time"></div>
        </div>
    </div>
    <script>
        function updateTime() {
            const now = new Date();
            
            // New York
            const newYorkTime = new Date(now.toLocaleString("en-US", { timeZone: "America/New_York" }));
            document.getElementById('new-york-time').textContent = newYorkTime.toLocaleTimeString();

            // London
            const londonTime = new Date(now.toLocaleString("en-GB", { timeZone: "Europe/London" }));
            document.getElementById('london-time').textContent = londonTime.toLocaleTimeString();

            // Tokyo
            const tokyoTime = new Date(now.toLocaleString("ja-JP", { timeZone: "Asia/Tokyo" }));
            document.getElementById('tokyo-time').textContent = tokyoTime.toLocaleTimeString();
        }

        setInterval(updateTime, 1000);
        updateTime();
    </script>
</body>
</html>
