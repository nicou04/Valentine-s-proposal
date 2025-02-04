# Valentine-s-proposal<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        h1 {
            font-size: 2.5em;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .buttons {
            margin-top: 20px;
        }

        button {
            font-size: 1.5em;
            padding: 15px 30px;
            margin: 10px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease-in-out;
            border-radius: 10px;
        }

        #yes {
            background-color: #ff4d6d;
            color: white;
            box-shadow: 3px 3px 6px rgba(0,0,0,0.2);
        }

        #no {
            background-color: #6c757d;
            color: white;
        }

        button:hover {
            transform: scale(1.1);
        }

        #message {
            font-size: 2em;
            margin-top: 20px;
            color: #fff;
            font-weight: bold;
            text-shadow: 2px 2px 6px rgba(0,0,0,0.3);
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>

    <h1>Alex, will you be my Valentine? ❤️</h1>

    <div class="buttons">
        <button id="yes" onclick="showLove()">Yes</button>
        <button id="no" onclick="changeNo()">No</button>
    </div>

    <p id="message" class="hidden"></p>

    <script>
        let noTexts = [
            "Are you sure? 💔",
            "Really? 😢",
            "Please reconsider? 🥺",
            "Think about it... ❤️",
            "Don't break my heart! 💞",
            "Last chance! 💘"
        ];
        let noIndex = 0;
        let yesButton = document.getElementById("yes");

        function changeNo() {
            let noButton = document.getElementById("no");

            if (noIndex < noTexts.length) {
                noButton.textContent = noTexts[noIndex];
                noIndex++;
            } else {
                noButton.textContent = "You can't say no! 😆";
            }

            let newSize = 1 + noIndex * 0.4; // Increase size each time
            if (newSize < 8) {
                yesButton.style.transform = `scale(${newSize})`;
            } else {
                yesButton.style.transform = `scale(8)`; // Max size
            }
        }

        function showLove() {
            document.getElementById("message").textContent = "I knew you would accept! ❤️ You are the ideal person for me to spend this beautiful day with. I love you! 💘";
            document.getElementById("message").classList.remove("hidden");
            document.querySelector(".buttons").style.display = "none";
        }
    </script>

</body>
</html>
