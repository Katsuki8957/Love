
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Do You Love Me?</title>
  <style>
    body {
      text-align: center;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #ffe6e9;
      overflow: hidden;
    }

    h1 {
      font-size: 3.5rem;
      color: #ff3366;
      margin-top: 50px;
      text-shadow: 2px 2px 5px #ff99aa;
    }

    button {
      font-size: 1.8rem;
      padding: 15px 30px;
      margin: 20px;
      cursor: pointer;
      position: relative;
      background-color: #ff6699;
      color: white;
      border: none;
      border-radius: 30px;
      box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
      transition: transform 0.2s, background-color 0.3s;
    }

    button:hover {
      transform: scale(1.1);
      background-color: #ff3366;
    }

    #noButton {
      position: absolute;
    }

    #yesMessage {
      display: none;
      font-size: 2rem;
      color: #ff3366;
      margin-top: 30px;
      text-shadow: 2px 2px 5px #ff99aa;
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: #ff6699;
      border-radius: 50%;
      animation: float 4s infinite ease-in-out;
    }

    .heart:before,
    .heart:after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: #ff6699;
      border-radius: 50%;
    }

    .heart:before {
      top: -10px;
      left: 0;
    }

    .heart:after {
      left: 10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-100vh) rotate(720deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <h1>Do you love me?</h1>
  <button id="yesButton" onclick="showYesMessage()">Yes</button>
  <button id="noButton" onmouseover="moveNoButton()">No</button>
  <div id="yesMessage">UUUU CLICKED YES SO THAT MEANS U LOVE MEEEE EHHEHE</div>

  <!-- Floating hearts -->
  <script>
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = Math.random() * 2 + 3 + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    setInterval(createHeart, 300);

    const noButton = document.getElementById("noButton");
    const yesMessage = document.getElementById("yesMessage");

    function moveNoButton() {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 100);
      noButton.style.left = x + "px";
      noButton.style.top = y + "px";
    }

    function showYesMessage() {
      yesMessage.style.display = "block";
    }
  </script>
</body>
</html>
