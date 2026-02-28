# Hayatımın Anlamı 💙
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Senin İçin ❤️</title>
<style>
body{
    margin:0;
    font-family: Arial, sans-serif;
    background: black;
    color: gold;
    text-align:center;
    overflow:hidden;
}
.container{
    position:relative;
    z-index:2;
    padding:30px;
    margin-top:50px;
}
input{
    padding:10px;
    border-radius:20px;
    border:none;
    text-align:center;
}
button{
    padding:10px 20px;
    border-radius:20px;
    border:none;
    background:gold;
    color:black;
    font-weight:bold;
    margin-top:10px;
}
.hidden{
    display:none;
}
#hearts span{
    position:absolute;
    color:red;
    animation:float 5s linear infinite;
}
@keyframes float{
    0%{transform:translateY(100vh);opacity:1;}
    100%{transform:translateY(-10vh);opacity:0;}
}
img{
    width:200px;
    border-radius:20px;
    margin-top:20px;
}
</style>
</head>
<body>

<div id="hearts"></div>

<div class="container">

<div id="login">
    <h2>Bu site sadece bir kişi için 💖</h2>
    <p>İlk buluştuğumuz yer?</p>
    <input type="text" id="password" placeholder="Cevabı yaz bebeğim">
    <br>
    <button onclick="checkPassword()">Giriş Yap</button>
</div>

<div id="content" class="hidden">
    <h1>Hoş geldin bebeğim ❤️</h1>
    <p>Trip atsanda, kızsanda...</p>
    <p>Ben seni her halinle seviyorum.</p>

    <h3>Birlikte Geçirdiğimiz Süre:</h3>
    <p id="timer"></p>

    <img src="https://drive.google.com/file/d/1cICamBFrD4G1SMEwU33R_eLsM6n2_Dku/view" alt="biz">

    <br>
    <button onclick="playMusic()">Müziği Başlat 🎶</button>
</div>

<audio id="music" src="https://drive.google.com/file/d/1H9lol10_hxgfaoYCEhUxYQ50-W8AN3p5/view?usp=drive_link"></audio>

</div>

<script>
function checkPassword(){
    var answer = document.getElementById("password").value.toLowerCase();
    if(answer === "Çengelköy"){  // Çengelköy
        document.getElementById("login").classList.add("hidden");
        document.getElementById("content").classList.remove("hidden");
    } else {
        alert("Yanlış cevap 😏 Tekrar dene bebeğim.");
    }
}

function playMusic(){
    document.getElementById("music").play();
}

var startDate = new Date("2022-09-09"); // İLİŞKİ BAŞLANGIÇ TARİHİ
setInterval(function(){
    var now = new Date();
    var diff = now - startDate;
    var days = Math.floor(diff / (1000*60*60*24));
    document.getElementById("timer").innerHTML = days + " gündür birlikteyiz 💖";
},1000);

function createHeart(){
    var heart = document.createElement("span");
    heart.innerHTML = "❤";
    heart.style.left = Math.random()*100 + "vw";
    heart.style.fontSize = Math.random()*20+10 + "px";
    document.getElementById("hearts").appendChild(heart);
    setTimeout(()=>{heart.remove();},5000);
}
setInterval(createHeart,300);
</script>

</body>
</html>
