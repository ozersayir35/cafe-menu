# 📱 GitHub Desktop + JSON Menü Sistemi Rehberi

## 🎯 Sistem Nasıl Çalışır?

```
menu.json (Menü verileri)
    ↓
index.html (JSON'dan okur ve menüyü oluşturur)
    ↓
Web'de görünür → Müşterileriniz telefonda açar
```

---

## ⚙️ KURULUM (İlk Defa)

### Adım 1: Dosyaları GitHub'a Yükle

1. **GitHub repository'nize gidin** (newcafe_menu)
2. **Code sekmesinde eski dosyaları silin**:
   - `cafe_menu.html` (eski dosya) → delete
   - Commit et
3. **"Add file" → "Upload files"** yapın
4. Bu dosyaları yükleyin:
   - ✅ `index_final.html` → **İsmi `index.html`'ye değiştir** (upload sırasında)
   - ✅ `menu.json` (böyle kalabilir)
5. **Commit changes** tıklayın

### Adım 2: GitHub Desktop'ta Repository Clone Et

1. **GitHub Desktop'ı aç**
2. **File → Clone Repository**
3. **ozersayir35/newcafe_menu** seç
4. **Local Path**: İşletim sisteminizde bir klasör seç
   - Örn: `C:\Projeler\HicbiYer` (Windows)
   - Örn: `~/Documents/HicbiYer` (Mac)
5. **Clone** tıklayın

Şimdi klasöründe bu dosyaları göreceksiniz:
```
📁 newcafe_menu/
  ├ index.html (menüyü oluşturan dosya)
  ├ menu.json (menü verileri - BU'YU DÜZENLEYECEKSİN)
  └ .git/ (gizli klasör)
```

---

## 🔄 MENÜ GÜNCELLEME (Günlük İşlem)

### SENARYO 1: Ürün Fiyatını Değiştir

**Örn: Espresso'yu 45₺ → 50₺ yap**

1. **VS Code'u aç** (veya favori metin editörün)
2. `menu.json` dosyasını aç (klasörde)
3. Bul:
   ```json
   {
     "name": "Espresso",
     "price": 45,  ← BURASI
   ```
4. `45` → `50` yap
5. **Ctrl+S** (Save)

---

### SENARYO 2: Yeni Ürün Ekle

**Örn: Kahveler kategorisine "Flat White" ekle**

1. **menu.json** aç
2. Kahveler kategorisindeki son ürüne git (Iced Coffee)
3. Virgülü kopyala ve şöyle ekle:

```json
        {
          "name": "Iced Coffee",
          "description": "Soğuk kahve, buz ve serinlik",
          "price": 60,
          "size": "300ml",
          "emoji": "❄️",
          "recommended": false
        },
        {
          "name": "Flat White",
          "description": "Yoğun espresso, sıcak süt, ince köpük",
          "price": 58,
          "size": "300ml",
          "emoji": "🤎",
          "recommended": false
        }
```

4. **Ctrl+S** (Save)

---

### SENARYO 3: Ürünü Sil

**Örn: "Iced Coffee" kaldır**

1. **menu.json** aç
2. Tüm bloğu sil:
   ```json
   {
     "name": "Iced Coffee",
     "description": "Soğuk kahve, buz ve serinlik",
     "price": 60,
     "size": "300ml",
     "emoji": "❄️",
     "recommended": false
   }
   ```
3. ⚠️ Eğer başka ürün var ise, **üstündeki virgülü kaldır**
4. **Ctrl+S** (Save)

---

### SENARYO 4: Önerilen Ürün Işaretle

Ürüne `"recommended": true` ekle:

```json
{
  "name": "Yeşil Smoothie",
  "description": "Kiwi, ıspanak, elma ve yeşil çay",
  "price": 70,
  "size": "350ml",
  "emoji": "🥝",
  "recommended": true  ← BÖYLE
}
```

---

## 📤 GİTHUB'A GÖNDER (GitHub Desktop)

Değişiklikleri yaptıktan sonra:

1. **GitHub Desktop'ı aç**
2. **"Changes" sekmesini gör** (sol üstte)
   - Değiştirdiğin dosyalar görünecek (mavi)
3. **Sol altta "Commit to main"** bölümüne tıkla
4. **Commit message** yaz:
   - Örn: `Espresso fiyatını güncelle`
   - Örn: `Yeni ürün: Flat White ekle`
   - Örn: `Iced Coffee kaldır`
5. **Commit to main** tıklayın
6. **Sağ üstte "Push origin"** tıklayın

✅ **Bitti!** Menünüz güncellenmiş!

---

## 🔍 GERİ KONTROL

Değişiklikleri görmek için:

1. **1-2 dakika bekle**
2. **Linki yeniyle**:
   ```
   https://ozersayir35.github.io/newcafe_menu/
   ```
3. Telefonunuzla QR kodla tarayın ve kontrol edin

---

## 🛠️ JSON YAPISI HAKKINDA IPUÇLARI

### Virgül (,) Kuralı
- **Eğer eleman sonrası başka eleman varsa** → virgül koy
- **Eğer eleman sonrası başka eleman yoksa** → virgül koymaz

```json
{
  "name": "Espresso",
  "price": 45,       ← virgül var (başka alan var)
},                   ← virgül (başka item var)
{
  "name": "Americano",
  "price": 50        ← virgül yok (son alan)
}                    ← virgül yok (son item)
```

### Emoji İçin Kullan
☕ 🤍 🖤 ☁️ 🍫 ❄️ 🍵 🌿 🌼 🍋 🍓 🥝 🧁 🥐 🍪 🍰 🥪 🧀 🍟 🥒 🍳 🍯 🍞 🎁 👥 🧘

---

## ⚠️ HATA AYIKLAMA

### "Menü yüklenmiyor" hatası
1. VS Code'da **menu.json** aç
2. **Ctrl+Shift+P** → "JSON: Format Document"
3. **Ctrl+S** (Save)
4. GitHub Desktop → Commit → Push
5. Yenilenmeyi bekle

### "Push başarısız" hatası
1. GitHub Desktop'ta **Pull origin** tıkla
2. Çakışmalar varsa çöz
3. Tekrar **Push origin** tıkla

---

## 📋 MENU.JSON ALAN AÇIKLAMA

```json
{
  "name": "Espresso",                    // Ürün adı
  "description": "Yoğun ve aromalı...",   // Kısa açıklama
  "price": 45,                            // Fiyat (₺ işareti otomatik)
  "size": "30ml",                         // Boyut/Porsiyon
  "emoji": "☕",                           // Görsel (emoji veya unicode)
  "recommended": false                    // 🧘 Önerilen badge göster mi?
}
```

---

## 🎨 CAFÉ BİLGİSİNİ GÜNCELLE

**menu.json** dosyasının en üstünde café bilgileri var:

```json
{
  "cafe": {
    "name": "HİÇBİ' YER",
    "tagline": "Coffee • Yoga • Workshop",
    "description": "Kahve, Meditasyon, Yaratıcılık Bir Yerde",
    "phone": "+90 (555) 123-4567",        // ← Bunu güncelle
    "location": "İzmir, Türkiye",         // ← Bunu güncelle
    "hours": "08:00 - 22:00"              // ← Bunu güncelle
  }
}
```

---

## 💡 ÖRNEK WORKFLOW

**Pazartesi sabahı: Hafta başı fiyat kontrolü**

1. VS Code'da menu.json aç
2. Fiyatları kontrol et ve gerekirse değiştir
3. Ctrl+S
4. GitHub Desktop → Commit ("Pazartesi fiyat kontrolü")
5. Push origin
6. Menü güncellenmiş! ✅

**Çarşamba: Yeni ürün**

1. VS Code'da menu.json aç
2. "Smoothie" kategorisine yeni smoothie ekle
3. Ctrl+S
4. GitHub Desktop → Commit ("Muz smoothie'si ekle")
5. Push origin

**Cuma: Hafta sonu özel**

1. Tüm "recommended" alanlarını kontrol et
2. Hafta sonu kampanyasında olacak ürünleri işaretle
3. Commit ("Hafta sonu özel ürünler")
4. Push

---

## 🔗 HIZLI LINKLER

- GitHub Repository: https://github.com/ozersayir35/newcafe_menu
- Menü Canlı: https://ozersayir35.github.io/newcafe_menu/
- VS Code İndir: https://code.visualstudio.com/
- GitHub Desktop İndir: https://desktop.github.com/

---

## ❓ SORULAR?

Her şey doğru görünüyor ancak harita yüklenmiyorsa:
- GitHub Desktop'ta "Fetch origin" yap
- 1-2 dakika daha bekle
- Tarayıcı cache'ini temizle (Ctrl+Shift+Delete)
- Sayfayı yenilenmeyi dene

**Bu sistem sayesinde menüyü saniyeler içinde güncelleyebilirsin!** 🚀
