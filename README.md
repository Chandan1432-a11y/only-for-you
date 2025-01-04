<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>🌹 Do You Love Me? 💖</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background-color: #ffe4e1;
      overflow: hidden;
    }
    .container {
      text-align: center;
      max-width: 600px;
      position: relative;
    }
    h1 {
      font-size: 2.8em;
      margin-bottom: 20px;
      color: #ff1493;
    }
    p {
      font-size: 1.5em;
      color: #ff1493;
    }
    .button {
      padding: 15px 30px;
      margin: 10px;
      font-size: 1.5em;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.3s, background-color 0.3s;
    }
    .yes-btn {
      background-color: #ff69b4;
      color: white;
    }
    .yes-btn:hover {
      transform: scale(1.1);
      background-color: #ff1493;
    }
    .no-btn {
      background-color: #ff6347;
      color: white;
      position: relative;
    }
    .no-btn:hover {
      transform: scale(1.1) rotate(10deg);
    }
    .input-box, .textarea-box {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 2px solid #ff69b4;
      border-radius: 8px;
      font-size: 1.2em;
    }
    .submit-btn {
      padding: 10px 20px;
      font-size: 1.5em;
      border: none;
      border-radius: 8px;
      background-color: #ff69b4;
      color: white;
      cursor: pointer;
      transition: transform 0.3s;
    }
    .submit-btn:hover {
      transform: scale(1.1);
    }
    .hidden {
      display: none;
    }
    .falling-emoji {
      position: absolute;
      top: 0;
      font-size: 2em;
      animation: fall 3s infinite;
    }
    .falling-flower {
      position: absolute;
      top: 0;
      font-size: 2em;
      animation: fall 5s infinite;
    }
    @keyframes fall {
      to {
        transform: translateY(100vh);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <!-- First Page -->
  <div class="container" id="page1">
    <h1>🌸 Do you love me? 🌸</h1>
    <button class="button yes-btn" onclick="showLovePage()">Yes 💖</button>
    <button class="button no-btn" id="noButton" onmouseover="moveNoButton()">No ❌</button>
  </div>

  <!-- Second Page -->
  <div class="container hidden" id="page2">
    <h1>I Labh uoy, Meri Jaan 💖</h1>
    <input type="text" class="input-box" placeholder="I labh uoy too, meri jaan🤍🥰🤗 💞" required id="loveMessage">
    
    <p>Sorry meri jaan jo bhi hua uske liye.... Write a note for your love (this is compulsory, don't worry madam this meaasage will never reach me.❤️):</p>
    <textarea class="textarea-box" rows="5" placeholder="Write what's in your heart right now..." required id="loveNote"></textarea>
    
    <button class="submit-btn" onclick="submitLove()">Submit 💖</button>
  </div>

  <script>
    function moveNoButton() {
      const noButton = document.getElementById('noButton');
      const randomX = Math.random() * 300 - 150; // Random X offset
      const randomY = Math.random() * 300 - 150; // Random Y offset
      noButton.style.transform = `translate(${randomX}px, ${randomY}px)`;
    }

    function showLovePage() {
      document.getElementById('page1').classList.add('hidden');
      document.getElementById('page2').classList.remove('hidden');
      createFallingItems();
    }

    function createFallingItems() {
      const emojis = ['💖', '😍', '🥰', '😘', '🌹', '🌸'];
      const flowers = ['🌻', '🌺', '🌷', '🌼', '🌸'];
      const numEmojis = 10;
      const numFlowers = 10;
      
      for (let i = 0; i < numEmojis; i++) {
        let emoji = document.createElement('div');
        emoji.classList.add('falling-emoji');
        emoji.innerText = emojis[Math.floor(Math.random() * emojis.length)];
        emoji.style.left = `${Math.random() * 100}vw`;
        document.body.appendChild(emoji);
      }

      for (let i = 0; i < numFlowers; i++) {
        let flower = document.createElement('div');
        flower.classList.add('falling-flower');
        flower.innerText = flowers[Math.floor(Math.random() * flowers.length)];
        flower.style.left = `${Math.random() * 100}vw`;
        document.body.appendChild(flower);
      }
    }

    function submitLove() {
      const loveInput = document.getElementById('loveMessage').value.trim();
      const noteInput = document.getElementById('loveNote').value.trim();

      if (loveInput === '' || noteInput === '') {
        alert("Please fill out both fields! 💌");
        return;
      }

      alert("Thank you for your beautiful note! I love you too! 💖you can take screeshot of your note because it will never show again..");
      createFallingItems();  // Create falling items after submission
    }
  </script>
</body>
</html>
