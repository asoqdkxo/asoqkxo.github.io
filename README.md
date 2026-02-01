<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>💘 Willst du mein Valentin sein?</title>

<style>
    * {
        box-sizing: border-box;
        font-family: "Comic Sans MS", "Poppins", sans-serif;
    }

    body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(135deg, #ff4d6d, #ff8fab);
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        color: white;
        text-align: center;
    }

    .container {
        padding: 20px;
        width: 100%;
        max-width: 400px;
    }

    h1 {
        font-size: 2rem;
        margin-bottom: 20px;
    }

    .buttons {
        position: relative;
        height: 200px;
    }

    button {
        padding: 15px 25px;
        font-size: 1.1rem;
        border: none;
        border-radius: 30px;
        cursor: pointer;
    }

    #yesBtn {
        background-color: #fff;
        color: #ff4d6d;
        font-weight: bold;
    }

    #noBtn {
        position: absolute;
        background-color: #ffccd5;
        color: #b00020;
    }

    /* Floating hearts */
    .heart {
        position: absolute;
        bottom: -20px;
        font-size: 20px;
        animation: floatUp 6s linear infinite;
        opacity: 0.8;
    }

    @keyframes floatUp {
        0% {
            transform: translateY(0);
            opacity: 0.8;
        }
        100% {
            transform: translateY(-120vh);
            opacity: 0;
        }
    }

    /* Balloons */
    .balloon {
        position: absolute;
        bottom: -100px;
        width: 40px;
        height: 55px;
        background: red;
        border-radius: 50% 50% 50% 50%;
        animation: balloonUp 10s linear infinite;
        opacity: 0.7;
    }

    @keyframes balloonUp {
        0% { transform: translateY(0); }
        100% { transform: translateY(-130vh); }
    }
</style>
</head>

<body>

<div class="container">
    <h1>💖 Willst du mein Valentin sein? 💖</h1>

    <div class="buttons">
        <button id="yesBtn" onclick="sayYes()">Ja 💕</button>
        <button id="noBtn">Nein 😅</button>
    </div>
</div>

<script>
    const noBtn = document.getElementById("noBtn");

    function moveButton() {
        const x = Math.random() * 250;
        const y = Math.random() * 150;
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    }

    // Move on hover (desktop) & touch (mobile)
    noBtn.addEventListener("mouseover", moveButton);
    noBtn.addEventListener("touchstart", moveButton);

    function sayYes() {
        document.body.innerHTML = `
            <div style="text-align:center; padding:40px;">
                <h1>🥰 JAAA! 🥰</h1>
                <p style="font-size:1.5rem;">Bestes Valentinstag-Date überhaupt 💘</p>
            </div>
        `;
    }

    // Create floating hearts
    setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerText = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (4 + Math.random() * 3) + "s";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 7000);
    }, 500);

    // Create balloons
    setInterval(() => {
        const balloon = document.createElement("div");
        balloon.className = "balloon";
        balloon.style.left = Math.random() * 100 + "vw";
        balloon.style.background = ["#ff4d6d", "#ff758f", "#ffb3c1"][Math.floor(Math.random()*3)];
        balloon.style.animationDuration = (8 + Math.random() * 5) + "s";
        document.body.appendChild(balloon);
        setTimeout(() => balloon.remove(), 13000);
    }, 1200);
</script>

</body>
</html>
