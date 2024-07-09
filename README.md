# tianyi-loves-ruolin
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tianyi Loves Ruolin</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe4e1;
            background-image: linear-gradient(to top, #ff9a9e 0%, #fecfef 100%);
            text-align: center;
        }
        h1 {
            color: #ff69b4;
            font-size: 4em;
            text-shadow: 2px 2px #ffb6c1;
        }
        .love-message {
            font-size: 2em;
            margin-top: 20px;
            color: #ff1493;
            text-shadow: 1px 1px #ffc0cb;
        }
        .heart {
            cursor: pointer;
            font-size: 3em;
            color: red;
            margin-left: 10px;
            transition: transform 0.3s;
        }
        .heart:hover {
            transform: scale(1.2);
        }
        .counter {
            font-size: 1.5em;
            margin-top: 10px;
            color: #ff4500;
            text-shadow: 1px 1px #ffa07a;
        }
        .time-message {
            font-size: 2em;
            margin-top: 20px;
            color: #ff4500;
            text-shadow: 1px 1px #ffa07a;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>TIANYI LOVE RUOLIN</h1>
    <div class="love-message">
        Click the heart if you love us 
        <span class="heart" onclick="incrementCounter()">❤️</span>
    </div>
    <div class="counter" id="counter">0</div>
    <div class="time-message" id="timeMessage" onclick="toggleTimeFormat()">It's been <span id="timeValue"></span> with my baby</div>

    <script>
        let count = 0;
        let startDate = new Date('2022-11-08');  // Updated start date for 609 days
        let timeFormat = 'days';

        function incrementCounter() {
            count++;
            document.getElementById('counter').textContent = count;
        }

        function updateTimeValue() {
            const currentDate = new Date();
            const timeDifference = currentDate - startDate;
            const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
            let value;

            switch (timeFormat) {
                case 'days':
                    value = `${days} days`;
                    break;
                case 'weeks':
                    value = `${(days / 7).toFixed(2)} weeks`;
                    break;
                case 'years':
                    value = `${(days / 365).toFixed(2)} years`;
                    break;
            }
            document.getElementById('timeValue').textContent = value;
        }

        function toggleTimeFormat() {
            switch (timeFormat) {
                case 'days':
                    timeFormat = 'weeks';
                    break;
                case 'weeks':
                    timeFormat = 'years';
                    break;
                case 'years':
                    timeFormat = 'days';
                    break;
            }
            updateTimeValue();
        }

        // Update the time value every day
        setInterval(updateTimeValue, 24 * 60 * 60 * 1000);
        updateTimeValue();
    </script>
</body>
</html>
