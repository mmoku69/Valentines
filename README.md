# Valentines
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine 💖</title>

  <style>
    body {
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Comic Sans MS', cursive;
      overflow: hidden;
    }

    .container {
      background: white;
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      position: relative;
      width: 350px;
    }

    h1 {
      color: #ff4d6d;
    }

    button {
      font-size: 18px;
      padding: 12px 25px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      margin: 10px;
      transition: 0.2s;
    }

    #yesBtn {
      background-color: #ff4d6d;
      color: white;
    }

    #noBtn {
      background-color: #999;
      color: white;
      position: absolute;
      left: 200px;
      top: 200px;
    }

    .heart {
      position: fixed;
      font-size: 24px;
      animation: floatUp 3s forwards;
    }

    @keyframes floatUp {
      to {
        transform: translateY(-200px) scale(1.8);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <div class="container">
    <h1>Will you be my Valentine? 💘</h1>
    <button id="yesBtn">Yes 💖</button>
    <button id="noBtn">No 🙄</button>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");

    const messages = [
      "No, try again 😤",
      "Are you sure? C’mon click yes already 💕",
      "OMG! Come on fr stop playing w/ me I know you gonna say yes 😭"
    ];

    let clickCount = 0;

    // Slight wiggle so it never leaves the screen
    noBtn.addEventListener("mouseover", () => {
      const offsetX = Math.random() * 30 - 15;
      const offsetY = Math.random() * 30 - 15;

      const newLeft = noBtn.offsetLeft + offsetX;
      const newTop = noBtn.offsetTop + offsetY;

      noBtn.style.left = newLeft + "px";
      noBtn.style.top = newTop + "px";
    });

    // Sweet messages when clicking "No"
    noBtn.addEventListener("click", () => {
      if (clickCount < messages.length) {
        alert(messages[clickCount]);
        clickCount++;
      } else {
        alert(messages[messages.length - 1]);
      }
    });

    // Yes button celebration
    yesBtn.addEventListener("click", () => {
      alert("YAYYYY 💖💖 I knew you'd say yes!!!");

      for (let i = 0; i < 25; i++) {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.top = Math.random() * window.innerHeight + "px";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 3000);
      }
    });
  </script>

</body>
</html>
