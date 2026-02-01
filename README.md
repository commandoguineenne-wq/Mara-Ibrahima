# Mara-Ibrahima
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mini App iPhone Pro Max</title>

<!-- Icône écran d’accueil -->
<link rel="apple-touch-icon" href="https://img.icons8.com/ios-filled/100/ffffff/smartphone.png">

<style>
  body {
    font-family: 'Arial', sans-serif;
    text-align: center;
    margin: 0;
    padding: 20px;
    background: linear-gradient(to bottom, #ffe0b2, #ffcc80);
    transition: background 0.5s;
  }
  h1 {
    color: #e65100;
    margin-bottom: 30px;
    text-shadow: 1px 1px 3px #ffcc80;
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%,100%{transform:scale(1);}
    50%{transform:scale(1.05);}
  }
  .menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 12px;
    margin-bottom: 20px;
  }
  .menu button {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 80px;
    height: 80px;
    border: none;
    border-radius: 20px;
    font-size: 14px;
    color: white;
    cursor: pointer;
    transition: 0.3s transform, 0.3s background-color;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  }
  .menu button:hover { transform: translateY(-5px) rotate(2deg);}
  .menu button img { width: 35px; height: 35px; margin-bottom: 5px;}
  p {
    font-size: 18px;
    color: #e65100;
    margin-top: 20px;
    transition: transform 0.3s, color 0.3s;
  }
  img#image {
    margin-top: 20px;
    max-width: 80%;
    border-radius: 20px;
    box-shadow: 0 6px 20px rgba(0,0,0,0.3);
    transition: transform 0.3s;
  }
  img#image:hover { transform: scale(1.05);}
  .dropdown {
    position: relative;
    display: inline-block;
    margin: 10px;
  }
  .dropdown-content {
    display: none;
    position: absolute;
    background-color: #fb8c00;
    border-radius: 12px;
    min-width: 140px;
    z-index: 1;
    flex-direction: column;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  }
  .dropdown-content button {
    width: 100%;
    margin: 0;
    border-radius: 12px;
    margin-bottom: 5px;
    background-color: #fb8c00;
    transition: 0.3s background-color, 0.3s transform;
  }
  .dropdown-content button:hover {
    background-color: #ef6c00;
    transform: translateX(5px);
  }
  .dropdown:hover .dropdown-content { display: flex;}
</style>
</head>
<body>

<h1>Mini App iPhone Pro Max</h1>

<div class="menu">
  <button style="background-color:#fb8c00;" onclick="changerTexte()">
    <img src="https://img.icons8.com/ios-filled/50/ffffff/edit.png" alt="Texte">
    Texte
  </button>
  <button style="background-color:#f4511e;" onclick="changerImage()">
    <img src="https://img.icons8.com/ios-filled/50/ffffff/picture.png" alt="Image">
    Image
  </button>
  <button style="background-color:#6a1b9a;" onclick="changerFond()">
    <img src="https://img.icons8.com/ios-filled/50/ffffff/color-palette.png" alt="Fond">
    Fond
  </button>
  <button style="background-color:#25D366;" onclick="ouvrirWhatsApp()">
    <img src="https://img.icons8.com/ios-filled/50/ffffff/whatsapp.png" alt="WhatsApp">
    WhatsApp
  </button>
  <button style="background-color:#0288d1;" onclick="appeler()">
    <img src="https://img.icons8.com/ios-filled/50/ffffff/phone.png" alt="Appel">
    Appel
  </button>
  <button style="background-color:#ff7043;" onclick="envoyerSMS()">
    <img src="https://img.icons8.com/ios-filled/50/ffffff/sms.png" alt="SMS">
    SMS
  </button>

  <div class="dropdown">
    <button style="background-color:#d32f2f;">
      <img src="https://img.icons8.com/ios-filled/50/ffffff/social-network.png" alt="Social">
      Social
    </button>
    <div class="dropdown-content">
      <button style="background-color:#e1306c;" onclick="ouvrirInstagram()">Instagram</button>
      <button style="background-color:#3b5998;" onclick="ouvrirFacebook()">Facebook</button>
      <button style="background-color:#ff0000;" onclick="ouvrirYouTube()">YouTube</button>
      <button style="background-color:#69c9d0;" onclick="ouvrirTikTok()">TikTok</button>
    </div>
  </div>
</div>

<p id="texte">Voici un texte interactif.</p>
<img id="image" src="https://via.placeholder.com/300x200.png?text=Image+1" alt="Image">

<audio id="sonBouton" src="https://www.soundjay.com/button/sounds/button-16.mp3"></audio>
<audio id="sonSucces" src="https://www.soundjay.com/button/sounds/button-3.mp3"></audio>

<script>
  const monNumero = "621362247";
  const monInstagram = "https://instagram.com/tonprofil";
  const monFacebook = "https://facebook.com/tonprofil";
  const monYouTube = "https://youtube.com";
  const monTikTok = "https://tiktok.com";

  function jouerSon(id) { document.getElementById(id).play(); }

  function changerTexte() {
    jouerSon('sonBouton');
    const p = document.getElementById('texte');
    p.textContent = "Bravo ! Tu as cliqué sur le bouton 😎";
    p.style.color="#4caf50"; p.style.transform="scale(1.1)";
    setTimeout(()=>{p.style.transform="scale(1)";p.style.color="#e65100";},300);
    jouerSon('sonSucces');
  }

  function changerImage() {
    jouerSon('sonBouton');
    const img=document.getElementById('image');
    img.src=img.src.includes("Image+1")?"https://via.placeholder.com/300x200.png?text=Image+2":"https://via.placeholder.com/300x200.png?text=Image+1";
    img.style.transform="scale(1.05)"; setTimeout(()=>{img.style.transform="scale(1)";},300);
    jouerSon('sonSucces');
  }

  function changerFond() {
    jouerSon('sonBouton');
    const body=document.body;
    body.style.background = body.style.background.includes("ffe0b2")?"linear-gradient(to bottom, #c5cae9, #7986cb)":"linear-gradient(to bottom, #ffe0b2, #ffcc80)";
    jouerSon('sonSucces');
  }

  function ouvrirWhatsApp() { jouerSon('sonBouton'); window.open(`https://wa.me/${monNumero}`,"_blank"); }
  function appeler() { jouerSon('sonBouton'); window.open(`tel:${monNumero}`,"_blank"); }
  function envoyerSMS() { jouerSon('sonBouton'); window.open(`sms:${monNumero}`,"_blank"); }
  function ouvrirInstagram() { jouerSon('sonBouton'); window.open(monInstagram,"_blank"); }
  function ouvrirFacebook() { jouerSon('sonBouton'); window.open(monFacebook,"_blank"); }
  function ouvrirYouTube() { jouerSon('sonBouton'); window.open(monYouTube,"_blank"); }
  function ouvrirTikTok() { jouerSon('sonBouton'); window.open(monTikTok,"_blank"); }
</script>

Ouvrir WhatsApp et envoyer message
