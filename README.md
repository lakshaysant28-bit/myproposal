<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Be My Valentine?</title>

<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: #ffebee;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        text-align: center;
    }

    .container {
        padding: 20px;
    }

    h1 {
        color: #d32f2f;
        margin-bottom: 30px;
        font-size: 2rem;
    }

    .buttons {
        position: relative;
        height: 150px;
    }

    button {
        padding: 12px 25px;
        font-size: 16px;
        border: none;
        border-radius: 25px;
        cursor: pointer;
        position: absolute;
        transition: all 0.2s ease;
    }

    #yesBtn {
        background-color: #e91e63;
        color: white;
        left: 30%;
        top: 60px;
    }

    #noBtn {
        background-color: #9e9e9e;
        color: white;
        left: 60%;
        top: 60px;
    }

    .message {
        margin-top: 20px;
        font-size: 1.5rem;
        color: #c2185b;
        display: none;
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 1.5rem;
        }

        button {
            font-size: 14px;
            padding: 10px 20px;
        }
    }
</style>
</head>

<body>

<div class="container">
    <h1>Will you be my Valentine? ❤️</h1>

    <div class="buttons">
        <button id="yesBtn">Yes 💖</button>
        <button id="noBtn">No 🙈</button>
    </div>

    <div class="message" id="message">Yay!! I knew it 😍💘</div>
</div>

<script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const message = document.getElementById("message");

    function moveNoButton() {
        const container = document.querySelector(".buttons");

        const maxX = container.clientWidth - noBtn.offsetWidth;
        const maxY = container.clientHeight - noBtn.offsetHeight;

        const newX = Math.random() * maxX;
        const newY = Math.random() * maxY;

        noBtn.style.left = newX + "px";
        noBtn.style.top = newY + "px";
    }

    // For desktop hover
    noBtn.addEventListener("mouseover", moveNoButton);

    // For mobile touch
    noBtn.addEventListener("touchstart", moveNoButton);

    yesBtn.addEventListener("click", () => {
        message.style.display = "block";
    });
</script>

</body>
</html>
