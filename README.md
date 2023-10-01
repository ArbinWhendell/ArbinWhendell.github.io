<html>
<head>
    <title>Movie?</title>
    <style>
        body {
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            height: 100vh;
            background-color: #ffecf2; /* Light pink background */
        }

        .container {
            border: 4px solid #ff1493; /* Pink border */
            border-radius: 20px; /* Rounded corners for the container */
            padding: 20px;
            margin: 20px;
        }

        h1 {
            margin-bottom: 40px; /* Increased margin */
            color: #ff1493; /* Deep pink text color */
            font-family: 'cursive', cursive;
            font-size: 48px; /* Larger font size */
        }

        .button-container {
            display: flex;
            justify-content: center;
        }

        button {
            margin: 10px; /* Increased margin */
            padding: 20px 40px; /* Larger padding */
            background-color: #ff1493; /* Deep pink button color */
            color: #fff; /* White text color */
            border: none;
            border-radius: 40px; /* Larger rounded corners */
            cursor: pointer;
            transition: background-color 0.3s ease;
            font-size: 24px; /* Larger font size */
        }

        button:hover {
            background-color: #ff0066; /* Darker pink on hover */
        }

        @keyframes disintegrate {
            0% {
                opacity: 1;
                transform: scale(1);
            }
            100% {
                opacity: 0;
                transform: scale(0);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Tara, nood movie?</h1>
        <div class="button-container">
            <button onclick="answerYes()">Sige</button>
            <button onclick="answerNo()" id="noButton">Ayaw</button>
        </div>
    </div>

    <script>
        let clickCount = 0;
        const buttonTexts = ['Really?', 'You sure?', 'No regrets?', 'K.', 'Wala kang choice'];

        function answerYes() {
            alert('Ocakes. P.S: May Virus na yung device mo.');
        }

        function answerNo() {
            const button = document.getElementById('noButton');

            if (clickCount < buttonTexts.length) {
                // Change the text of the "No" button
                button.textContent = buttonTexts[clickCount];
                moveButtonRandomly();
                clickCount++;
            } else if (clickCount === buttonTexts.length) {
                // After cycling through the array, hide the "No" button with animation
                button.style.animation = 'disintegrate 1s ease forwards';
                setTimeout(() => {
                    button.style.display = 'none';
                }, 1000);
                clickCount++;
            }
        }

        function moveButtonRandomly() {
            const button = document.getElementById('noButton');
            // Adjust these values for a smaller teleportation area
            const maxWidth = window.innerWidth - button.clientWidth - 1000; // Smaller width
            const maxHeight = window.innerHeight - button.clientHeight - 1000; // Smaller height

            const randomX = Math.floor(Math.random() * maxWidth);
            const randomY = Math.floor(Math.random() * maxHeight);

            button.style.transform = `translate(${randomX}px, ${randomY}px)`;
        }
    </script>
</body>
</html>
