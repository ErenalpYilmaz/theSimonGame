# 🎮 Simon Game - Web Uygulaması

Bu proje, klasik **Simon Says** oyununu temel alan bir **web tabanlı hafıza oyunudur**. Oyun, rastgele yanıp sönen butonları kullanıcıdan doğru sırayla tekrar etmesini ister. Kullanıcı hatalı bir giriş yaparsa oyun biter ve baştan başlatılır.

## 🚀 Teknolojiler
- **HTML**: Sayfa yapısını oluşturmak için
- **CSS**: Görsel tasarım ve animasyonlar için
- **JavaScript (jQuery kütüphanesi)**: Oyun mekaniğini yönetmek için

## 📌 Nasıl Çalışır?
1. Kullanıcı herhangi bir tuşa basarak oyunu başlatır.
2. Rastgele bir renk yanıp söner ve **kullanıcı bu rengi tıklamalıdır**.
3. Kullanıcı doğru tıkladıkça yeni bir renk eklenir ve **sıralı olarak tıklaması gerekir**.
4. Yanlış bir renk seçildiğinde oyun biter ve kullanıcı tekrar başlayabilir.

## 📂 Dosya Yapısı

- `index.html` → Oyun arayüzünü oluşturur.
- `styles.css` → Görselleri ve animasyonları yönetir.
- `game.js` → Oyun mantığını ve etkileşimi sağlar.

## 📜 Kod Açıklamaları

### 🎨 HTML - Oyun Arayüzü
Oyun **4 buton** ve bir **başlık** içermektedir.
```html
<h1 id="level-title">Press A Key to Start</h1>
<div class="container">
  <div class="row">
    <div type="button" id="green" class="btn green"></div>
    <div type="button" id="red" class="btn red"></div>
  </div>
  <div class="row">
    <div type="button" id="yellow" class="btn yellow"></div>
    <div type="button" id="blue" class="btn blue"></div>
  </div>
</div>
```

### 🎨 CSS - Tasarım
Oyun ekranı **mavi arka plan** üzerine **renkli butonlar** içerir.
```css
.btn {
  height: 200px;
  width: 200px;
  border: 10px solid black;
  border-radius: 20%;
}
.green { background-color: green; }
.red { background-color: red; }
.blue { background-color: blue; }
.yellow { background-color: yellow; }
```

### 🧠 JavaScript - Oyun Mantığı
- **Tuşa basılınca oyun başlar.**
- **Rastgele bir renk seçilir ve yanıp söner.**
- **Kullanıcının girdiği renkler doğrulanır.**
- **Yanlış renk seçilirse oyun biter ve baştan başlar.**

```javascript
$(document).keypress(function() {
  if (!started) {
    $("#level-title").text("Level " + level);
    nextSequence();
    started = true;
  }
});

$(".btn").click(function() {
  var userChosenColour = $(this).attr("id");
  userClickedPattern.push(userChosenColour);
  playSound(userChosenColour);
  animatePress(userChosenColour);
  checkAnswer(userClickedPattern.length-1);
});
```

## 🎵 Sesler
Oyun, **yanlış seçim yapıldığında hata sesi çalar** ve arayüz kırmızıya döner.
```javascript
function playSound(name) {
  var audio = new Audio("sounds/" + name + ".mp3");
  audio.play();
}
```

## 🔥 Oynama Adımları
1. Projeyi bilgisayarınıza klonlayın veya indirin.
2. `index.html` dosyasını bir tarayıcıda açın.
3. Bir tuşa basarak oyunu başlatın ve yönergeleri takip edin!

## 📌 Eklemeler
- **Zorluk seviyesi artırılabilir**.
- **Mobil uyumlu hale getirilebilir**.
- **Skor tablosu eklenebilir**.

Bu oyun, **JavaScript ve jQuery** kullanarak **DOM manipülasyonu** ve **event handling** konularını pekiştirmek için harika bir projedir! 🚀

