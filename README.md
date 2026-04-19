# Janamdin-mubarak-jii
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Bhonduu</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --pink: #ff85a1;
            --soft-white: #fff5f7;
        }

        body, html {
            margin: 0; padding: 0; height: 100%;
            font-family: 'Poppins', sans-serif;
            background-color: var(--soft-white);
            overflow: hidden; text-align: center;
        }

        .page {
            display: none; height: 100vh; width: 100vw;
            flex-direction: column; justify-content: center;
            align-items: center; position: absolute;
            transition: all 0.5s ease; padding: 20px; box-sizing: border-box;
        }

        .active { display: flex; animation: fadeIn 1.2s ease-in; }

        @keyframes fadeIn { from { opacity: 0; transform: scale(0.95); } to { opacity: 1; transform: scale(1); } }

        .animation-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none; z-index: 100;
        }

        h1 { font-family: 'Dancing Script', cursive; color: var(--pink); font-size: 2.5rem; text-shadow: 2px 2px #fff; }
        
        .bhondu-img { 
            width: 280px; height: 280px; 
            border-radius: 20px; border: 8px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            object-fit: cover; margin: 20px;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(-2deg); }
            50% { transform: translateY(-15px) rotate(2deg); }
        }

        button, input {
            padding: 12px 25px; border-radius: 25px;
            border: 2px solid var(--pink); margin: 10px;
            font-size: 1rem; outline: none;
        }

        button {
            background: var(--pink); color: white;
            cursor: pointer; transition: 0.3s; font-weight: bold;
        }

        button:hover { transform: scale(1.1); box-shadow: 0 5px 15px rgba(255,133,161,0.4); }

        .gift-box { font-size: 120px; cursor: pointer; animation: wobble 1s infinite; }
        @keyframes wobble {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px) rotate(-5deg); }
            75% { transform: translateX(5px) rotate(5deg); }
        }

        .letter-container {
            background: white; padding: 30px; border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            max-width: 500px; line-height: 1.8; border: 2px dashed var(--pink);
        }

        .hindi-text { font-size: 1.3rem; color: #444; padding: 0 20px; font-weight: 500; }
    </style>
</head>
<body>

    <div class="animation-overlay" id="anime"></div>

    <div class="page active" id="page1">
        <h1>THIS IS FOR YOU MY BHONDUU....</h1>
        <img src="https://i.ibb.co/gLJp1wVv/image.jpg" class="bhondu-img" alt="Bhondu">
        <input type="password" id="pass" placeholder="Password is 'panda'...">
        <button onclick="checkPassword()">Enter 🐼</button>
    </div>

    <div class="page" id="page2">
        <h1>Happy Birthday Pyaaari Bhonduu</h1>
        <img src="https://i.ibb.co/N2H4tjs8/image.jpg" style="width: 90%; max-width: 450px; border-radius: 15px; border: 5px solid white; box-shadow: 0 5px 15px rgba(0,0,0,0.2);" alt="Collage">
        <button onclick="nextPage(3)">Next Page ❤️</button>
    </div>

    <div class="page" id="page3">
        <h1 id="gift-msg">Click to Open</h1>
        <div class="gift-box" id="box" onclick="openGift()">🎁</div>
        <div id="gift-content" style="display:none;">
            <img src="https://i.ibb.co/1t6WjQzx/image.jpg" class="bhondu-img" alt="Surprise">
            <p style="font-size: 1.2rem; color: #ff4d7d;"><strong>Cutest thing in the whole world!</strong></p>
            <button onclick="nextPage(4)">Continue ✨</button>
        </div>
    </div>

    <div class="page" id="page4">
        <img src="https://i.ibb.co/Cs5CMRm3/image.jpg" class="bhondu-img" alt="Beauty">
        <p class="hindi-text">"आपका व्यक्तित्व उस अलौकिक आभा के समान है, जो बिना किसी श्रृंगार के भी मन को मुग्ध कर लेती है। आपकी सादगी ही आपका वास्तविक सौंदर्य है।"</p>
        <button onclick="nextPage(5)">Read my letter ✉️</button>
    </div>

    <div class="page" id="page5">
        <div class="letter-container">
            <p><strong>Happy Birthday pyaari Bhonduuuu! 🎂❤️</strong></p>
            <p>Tumhe pata hai na ki tum mere liye kitni special ho? Tum thodi si buddhu ho thodi si ziddi bhi 😝😝 lekin jaisi bhi ho... Bestest ever ho.</p>
            <p>I promise ki main hamesha tumahre saath khada raunga tumhari saari baate sunne ke liye aur tumhe har mushkil mein sambhalne ke liye Tayyar hu tum hamesha aise hi hasti rehna kyunki tumhari smile dekh kar mera din ban jata hai.</p>
            <p>Stay the same, my favorite Bhonduuuu! ✨🥹🎈</p>
        </div>
        <button onclick="location.reload()">See it again? 🐼</button>
    </div>

    <script>
        function checkPassword() {
            const p = document.getElementById('pass').value;
            if(p.toLowerCase() === "panda") {
                nextPage(2);
            } else {
                alert("Wrong password! Hint: panda 🐼");
            }
        }

        function nextPage(num) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('page' + num).classList.add('active');
        }

        function openGift() {
            document.getElementById('box').style.display = 'none';
            document.getElementById('gift-msg').innerText = "Surprise!";
            document.getElementById('gift-content').style.display = 'block';
        }

        function createEmoji() {
            const emojis = ['❤️', '🐼', '💖', '✨', '🐾'];
            const e = document.createElement('div');
            e.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
            e.style.position = 'fixed';
            e.style.left = Math.random() * 100 + 'vw';
            e.style.top = '110vh';
            e.style.fontSize = Math.random() * 20 + 20 + 'px';
            e.style.transition = 'transform 6s linear, opacity 6s';
            e.style.zIndex = '100';
            document.getElementById('anime').appendChild(e);

            setTimeout(() => {
                e.style.transform = `translateY(-125vh) rotate(${Math.random() * 360}deg)`;
                e.style.opacity = '0';
            }, 100);

            setTimeout(() => e.remove(), 6500);
        }
        setInterval(createEmoji, 400);
    </script>
</body>
</html>
