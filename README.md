<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PREMIUM SATIŞ</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f9f9f9;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      position: relative;
      min-height: 100vh;
    }

    .menu-dots {
      position: absolute;
      top: 15px;
      left: 20px;
      display: flex;
      flex-direction: column;
      gap: 4px;
      cursor: pointer;
      z-index: 1001;
    }

    .menu-dots span {
      width: 6px;
      height: 6px;
      background: #333;
      border-radius: 50%;
    }

    .side-menu {
      position: fixed;
      top: 0;
      left: -50%;
      width: 50%;
      height: 100%;
      background-color: #fff;
      box-shadow: 2px 0 10px rgba(0,0,0,0.2);
      padding: 30px 20px;
      box-sizing: border-box;
      transition: left 0.3s ease;
      z-index: 1000;
    }

    .side-menu.active {
      left: 0;
    }

    .side-menu h3 {
      margin-top: 0;
      margin-bottom: 20px;
      color: #cc0000;
    }

    .side-menu button {
      display: block;
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      background: #cc0000;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
    }

    h2 {
      text-align: center;
      color: #cc0000;
      margin-top: 40px;
    }

    .offer {
      display: flex;
      align-items: center;
      background: #f1f1f1;
      padding: 15px;
      border-radius: 15px;
      margin: 15px 0;
      border-left: 5px solid #cc0000;
      cursor: pointer;
    }

    .logo {
      width: 50px;
      height: 35px;
      background: #FF0000;
      border-radius: 8px;
      position: relative;
      margin-right: 20px;
    }

    .logo::after {
      content: '';
      position: absolute;
      top: 9px;
      left: 18px;
      width: 0;
      height: 0;
      border-left: 12px solid white;
      border-top: 8px solid transparent;
      border-bottom: 8px solid transparent;
    }

    .text {
      font-size: 18px;
    }

    .price {
      color: #333;
      font-weight: bold;
      margin-top: 5px;
    }

    .note {
      color: green;
      font-size: 14px;
    }

    .game-card {
      display: flex;
      align-items: center;
      background: #fff;
      padding: 15px 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 400px;
      margin: 30px auto;
      cursor: pointer;
    }

    .game-logo {
      width: 60px;
      height: 60px;
      background-color: #0ea34d;
      border-radius: 10px;
      color: white;
      font-size: 24px;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-right: 20px;
    }

    .game-title {
      font-size: 20px;
      color: #222;
    }

    .back-button {
      display: block;
      margin: 20px auto 0;
      padding: 10px 20px;
      background-color: #444;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
    }

    #mainPage, #gamePage, #contactPage, #youtubeForm {
      display: none;
    }

    #mainPage.active, #gamePage.active, #contactPage.active, #youtubeForm.active {
      display: block;
    }

    .whatsapp-button {
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #25D366;
      color: white;
      padding: 10px 20px;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
      text-decoration: none;
      margin-top: 20px;
    }

    .whatsapp-button img {
      margin-right: 10px;
      width: 20px;
      height: 20px;
    }

    .input-container {
      margin-top: 20px;
    }

    .input-container input {
      width: 100%;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
      margin-top: 10px;
    }

    .input-container button {
      width: 100%;
      padding: 10px;
      background-color: #cc0000;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 15px;
    }
  </style>
</head>
<body>

  <!-- Menü -->
  <div class="side-menu" id="sideMenu">
    <h3>Menü</h3>
    <button onclick="goToPage('gamePage')">Oyun</button>
    <button onclick="goToContact()">İletişim</button>
  </div>

  <!-- Sayfa Nokta Menüsü -->
  <div class="menu-dots" onclick="toggleMenu()">
    <span></span>
    <span></span>
    <span></span>
  </div>

  <!-- Ana Sayfa -->
  <div class="container" id="mainPage">
    <h2>PREMIUM SATIŞ</h2>

    <div class="offer" onclick="selectOffer('1 Abone - 2₺')">
      <div class="logo"></div>
      <div class="text">
        1 Abone <div class="price">2₺</div>
      </div>
    </div>

    <div class="offer" onclick="selectOffer('3 Abone - 5₺')">
      <div class="logo"></div>
      <div class="text">
        3 Abone <div class="price">5₺ <span class="note">(kârlı!)</span></div>
      </div>
    </div>

    <div class="offer" onclick="selectOffer('5 Abone - 10₺')">
      <div class="logo"></div>
      <div class="text">
        5 Abone <div class="price">10₺</div>
      </div>
    </div>
  </div>

  <!-- Oyun Sayfası -->
  <div class="container" id="gamePage">
    <h2>Oyunlar</h2>

    <div class="game-card" onclick="selectOffer('Minecraft')">
      <div class="game-logo">M</div>
      <div class="game-title">Minecraft</div>
    </div>

    <button class="back-button" onclick="goToPage('mainPage')">Geri</button>
  </div>

  <!-- İletişim Sayfası -->
  <div class="container" id="contactPage">
    <h2>İletişim</h2>
    <div class="whatsapp-button" onclick="window.open('https://wa.me/905445773600')">
      <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Logo">
      WhatsApp ile İletişime Geç
    </div>
    <button class="back-button" onclick="goToPage('mainPage')">Geri</button>
  </div>

  <!-- YouTube Kanalı ve Satın Alma -->
  <div class="container" id="youtubeForm">
    <h2>Satın Alma İşlemi</h2>
    <div class="input-container">
      <input type="text" id="youtube-channel" placeholder="YouTube Kanal Adınızı Girin">
      <button onclick="sendWhatsApp()">Tamam</button>
      <button class="back-button" onclick="goToPage('mainPage')">Geri</button>
    </div>
  </div>

  <script>
    let selectedOffer = '';

    function toggleMenu() {
      document.getElementById('sideMenu').classList.toggle('active');
    }

    function goToPage(pageId) {
      document.getElementById('sideMenu').classList.remove('active');
      ['mainPage', 'gamePage', 'contactPage', 'youtubeForm'].forEach(id => {
        document.getElementById(id).classList.remove('active');
      });
      document.getElementById(pageId).classList.add('active');
    }

    function goToContact() {
      goToPage('contactPage');
    }

    function selectOffer(offer) {
      selectedOffer = offer;

      if (offer === 'Minecraft') {
        const message = `Oyun Satın Alımı: Minecraft`;
        const url = `https://wa.me/905445773600?text=${encodeURIComponent(message)}`;
        window.open(url, '_blank');
      } else {
        goToPage('youtubeForm');
      }
    }

    function sendWhatsApp() {
      const channel = document.getElementById('youtube-channel').value.trim();
      if (!channel) {
        alert('Lütfen YouTube kanal adınızı girin.');
        return;
      }
      const message = `Teklif: ${selectedOffer}\nYouTube Kanal Adı: ${channel}`;
      const url = `https://wa.me/905445773600?text=${encodeURIComponent(message)}`;
      window.open(url, '_blank');
    }

    // Başlangıçta ana sayfa aktif
    goToPage('mainPage');
  </script>
</body>
</html><!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PREMIUM SATIŞ</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f9f9f9;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      position: relative;
      min-height: 100vh;
    }

    .menu-dots {
      position: absolute;
      top: 15px;
      left: 20px;
      display: flex;
      flex-direction: column;
      gap: 4px;
      cursor: pointer;
      z-index: 1001;
    }

    .menu-dots span {
      width: 6px;
      height: 6px;
      background: #333;
      border-radius: 50%;
    }

    .side-menu {
      position: fixed;
      top: 0;
      left: -50%;
      width: 50%;
      height: 100%;
      background-color: #fff;
      box-shadow: 2px 0 10px rgba(0,0,0,0.2);
      padding: 30px 20px;
      box-sizing: border-box;
      transition: left 0.3s ease;
      z-index: 1000;
    }

    .side-menu.active {
      left: 0;
    }

    .side-menu h3 {
      margin-top: 0;
      margin-bottom: 20px;
      color: #cc0000;
    }

    .side-menu button {
      display: block;
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      background: #cc0000;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
    }

    h2 {
      text-align: center;
      color: #cc0000;
      margin-top: 40px;
    }

    .offer {
      display: flex;
      align-items: center;
      background: #f1f1f1;
      padding: 15px;
      border-radius: 15px;
      margin: 15px 0;
      border-left: 5px solid #cc0000;
      cursor: pointer;
    }

    .logo {
      width: 50px;
      height: 35px;
      background: #FF0000;
      border-radius: 8px;
      position: relative;
      margin-right: 20px;
    }

    .logo::after {
      content: '';
      position: absolute;
      top: 9px;
      left: 18px;
      width: 0;
      height: 0;
      border-left: 12px solid white;
      border-top: 8px solid transparent;
      border-bottom: 8px solid transparent;
    }

    .text {
      font-size: 18px;
    }

    .price {
      color: #333;
      font-weight: bold;
      margin-top: 5px;
    }

    .note {
      color: green;
      font-size: 14px;
    }

    .game-card {
      display: flex;
      align-items: center;
      background: #fff;
      padding: 15px 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 400px;
      margin: 30px auto;
      cursor: pointer;
    }

    .game-logo {
      width: 60px;
      height: 60px;
      background-color: #0ea34d;
      border-radius: 10px;
      color: white;
      font-size: 24px;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-right: 20px;
    }

    .game-title {
      font-size: 20px;
      color: #222;
    }

    .back-button {
      display: block;
      margin: 20px auto 0;
      padding: 10px 20px;
      background-color: #444;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
    }

    #mainPage, #gamePage, #contactPage, #youtubeForm {
      display: none;
    }

    #mainPage.active, #gamePage.active, #contactPage.active, #youtubeForm.active {
      display: block;
    }

    .whatsapp-button {
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #25D366;
      color: white;
      padding: 10px 20px;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
      text-decoration: none;
      margin-top: 20px;
    }

    .whatsapp-button img {
      margin-right: 10px;
      width: 20px;
      height: 20px;
    }

    .input-container {
      margin-top: 20px;
    }

    .input-container input {
      width: 100%;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
      margin-top: 10px;
    }

    .input-container button {
      width: 100%;
      padding: 10px;
      background-color: #cc0000;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 15px;
    }
  </style>
</head>
<body>

  <!-- Menü -->
  <div class="side-menu" id="sideMenu">
    <h3>Menü</h3>
    <button onclick="goToPage('gamePage')">Oyun</button>
    <button onclick="goToContact()">İletişim</button>
  </div>

  <!-- Sayfa Nokta Menüsü -->
  <div class="menu-dots" onclick="toggleMenu()">
    <span></span>
    <span></span>
    <span></span>
  </div>

  <!-- Ana Sayfa -->
  <div class="container" id="mainPage">
    <h2>PREMIUM SATIŞ</h2>

    <div class="offer" onclick="selectOffer('1 Abone - 2₺')">
      <div class="logo"></div>
      <div class="text">
        1 Abone <div class="price">2₺</div>
      </div>
    </div>

    <div class="offer" onclick="selectOffer('3 Abone - 5₺')">
      <div class="logo"></div>
      <div class="text">
        3 Abone <div class="price">5₺ <span class="note">(kârlı!)</span></div>
      </div>
    </div>

    <div class="offer" onclick="selectOffer('5 Abone - 10₺')">
      <div class="logo"></div>
      <div class="text">
        5 Abone <div class="price">10₺</div>
      </div>
    </div>
  </div>

  <!-- Oyun Sayfası -->
  <div class="container" id="gamePage">
    <h2>Oyunlar</h2>

    <div class="game-card" onclick="selectOffer('Minecraft')">
      <div class="game-logo">M</div>
      <div class="game-title">Minecraft</div>
    </div>

    <button class="back-button" onclick="goToPage('mainPage')">Geri</button>
  </div>

  <!-- İletişim Sayfası -->
  <div class="container" id="contactPage">
    <h2>İletişim</h2>
    <div class="whatsapp-button" onclick="window.open('https://wa.me/905445773600')">
      <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Logo">
      WhatsApp ile İletişime Geç
    </div>
    <button class="back-button" onclick="goToPage('mainPage')">Geri</button>
  </div>

  <!-- YouTube Kanalı ve Satın Alma -->
  <div class="container" id="youtubeForm">
    <h2>Satın Alma İşlemi</h2>
    <div class="input-container">
      <input type="text" id="youtube-channel" placeholder="YouTube Kanal Adınızı Girin">
      <button onclick="sendWhatsApp()">Tamam</button>
      <button class="back-button" onclick="goToPage('mainPage')">Geri</button>
    </div>
  </div>

  <script>
    let selectedOffer = '';

    function toggleMenu() {
      document.getElementById('sideMenu').classList.toggle('active');
    }

    function goToPage(pageId) {
      document.getElementById('sideMenu').classList.remove('active');
      ['mainPage', 'gamePage', 'contactPage', 'youtubeForm'].forEach(id => {
        document.getElementById(id).classList.remove('active');
      });
      document.getElementById(pageId).classList.add('active');
    }

    function goToContact() {
      goToPage('contactPage');
    }

    function selectOffer(offer) {
      selectedOffer = offer;

      if (offer === 'Minecraft') {
        const message = `Oyun Satın Alımı: Minecraft`;
        const url = `https://wa.me/905445773600?text=${encodeURIComponent(message)}`;
        window.open(url, '_blank');
      } else {
        goToPage('youtubeForm');
      }
    }

    function sendWhatsApp() {
      const channel = document.getElementById('youtube-channel').value.trim();
      if (!channel) {
        alert('Lütfen YouTube kanal adınızı girin.');
        return;
      }
      const message = `Teklif: ${selectedOffer}\nYouTube Kanal Adı: ${channel}`;
      const url = `https://wa.me/905445773600?text=${encodeURIComponent(message)}`;
      window.open(url, '_blank');
    }

    // Başlangıçta ana sayfa aktif
    goToPage('mainPage');
  </script>
</body>
</html>
