<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Special Invitation ✨</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe4e1;
            font-family: 'Comic Sans MS', cursive, sans-serif;
            text-align: center;
            overflow: hidden;
        }
        .container {
            background: white;
            padding: 2.5rem;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            max-width: 450px;
            width: 90%;
            transition: all 0.3s ease;
            position: relative;
            z-index: 1;
        }
        img {
            width: 180px;
            height: 180px;
            border-radius: 15px;
            margin-bottom: 20px;
            object-fit: contain;
        }
        h1 { color: #ff4d6d; font-size: 1.6rem; min-height: 80px; }
        .buttons {
            margin-top: 2rem;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            min-height: 100px;
        }
        button {
            padding: 12px 25px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            transition: transform 0.2s ease-in-out;
        }
        #yesBtn { background-color: #70e000; color: white; position: relative; z-index: 1000; }
        #noBtn { background-color: #ff4d6d; color: white; position: relative; z-index: 10; }
    </style>
</head>
<body>

    <div class="container" id="mainContainer">
        <img id="displayGif" src="https://gifdb.com/images/high/peachcat-mochi-hello-and-goodbye-cute-4v2w6e4r9n48d08q.gif" alt="Cute character waving">
        
        <h1 id="question">Will you go out with me? ✨</h1>
        
        <div class="buttons">
            <button id="yesBtn">Yes!</button>
            <button id="noBtn">No</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const question = document.getElementById('question');

        let noCount = 0;
        let yesScale = 1;

        const messages = [
            "Are you sure? 🥺",
            "Pookie please... 🎀",
            "Don't do this to me! 💔",
            "I will be really sad... 😭",
            "Last chance! ⚠️",
            "Okay, now you're just being mean. 🤡",
            "Just click Yes already! 😤"
        ];

        noBtn.addEventListener('mouseover', () => {
            // 1. Random Movement
            const maxX = window.innerWidth - noBtn.offsetWidth;
            const maxY = window.innerHeight - noBtn.offsetHeight;
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);
            
            noBtn.style.position = 'fixed';
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';

            // 2. Fixed Text Logic
            if (noCount < messages.length) {
                question.innerText = messages[noCount];
            } else {
                question.innerText = "There is no escape! Click Yes! 😈";
            }

            // 3. Make the Yes button massive (0.3 growth)
            yesScale += 0.3;
            yesBtn.style.transform = `scale(${yesScale})`;
            
            noCount++;
        });

        yesBtn.addEventListener('click', () => {
            document.getElementById('mainContainer').innerHTML = `
                <img src="https://i.pinimg.com/originals/9e/c3/82/9ec382909f1873b40f2f36f6d0a790f5.gif" alt="Happy dance animation">
                <h1 style="color: #ff4d6d;">Knew you'd say yes! <br> I'll text you the details! 🍦💕</h1>
            `;
        });
    </script>
</body>
</html>
