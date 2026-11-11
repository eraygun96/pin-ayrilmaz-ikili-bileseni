# Ayrılmaz İkili / Ana Sayfa Bileşeni – Tasarım Notları

Son güncelleme: 2026-11-11

## Kararlar (bileşene uygulandı)
- **Ana söylem:** "Peşindeki tek şey 5 yıldızlı lezzet."
- **5 yıldız dolu (altın) gelir:** son halde "Lezzet · 5/5".
- **Ürün seçimi yok.** Ürün ikili paket: **Ayrılmaz İkili** = Beyaz Şeftali teneke + Vitaminli Şeftali teneke.
- **Görev işaretçisi** (zıplayan sarı imleç) ikili paketin üstünde, paketi işaret ediyor.
- **Bekleme hali:** HUD kutusunda yazı yok, sadece 5 aranma yıldızı (34px, mobilde 30px), sürekli kırmızı/mavi yanıp söner. Çözülünce yıldız kutusunun sağına 0 Şeker Kalori logosu gelir (bölüm aşağı büyümez).
- **Açıklama:** "Görevi tamamla, 0 şeker, 0 kalori oyun eşlikçini **%40 indirimle** al."
- **Ayrılmaz İkili alt satırı:** "Efsane yeni ambalajında" + sadece Vitaminli Şeftali üstünde altın "Efsane" etiketi.
- **Buton:** "Göreve Başla: İndirim Kodunu Al"; altında beyaz hap içinde nabız noktalı "Sınırlı sayıda" → mini oyun açılır (masaüstünde bölümün içinde, mobilde tam ekran).
- **Mini oyun — "Görev: Şekeri sıfırla" / "Şekerleri patlat":** tenekelerin etrafında yavaşça süzülen 5 şeker küpü.
  Her dokunuş bir küpü patlatır, bir aranma yıldızını altına çevirir ve **Şeker** ile **Kalori** barlarını beşte bir azaltır
  (sayı yok, sadece dolu bar). Barlar sıfırlanınca ödül ekranı açılır. Başarısızlık yok; klavyede Tab + Enter ile de oynanır, Esc kapatır.
- **Yerleşim sıkılaştırıldı:** gökyüzü ve zemin kırpıldı, ürünler ve sol metin yukarı alındı (masaüstü ~565px).
- **Mobil:** bölüm ~715px, "Göreve Başla" butonu ilk ekranda görünür (360/375/414px test edildi).
  Başlık 2 satır ("PEŞİNDEKİ TEK ŞEY" / "5 YILDIZLI LEZZET"), tenekeler 215px,
  "Sınırlı sayıda" mobil ve tablette butonun üstünde.
- **Ödül ekranı:** "Görev tamamlandı · Şeker sıfırlandı!" + 5 altın yıldız + 0 Şeker Kalori logosu
  (alt metin yok) + büyük parlayan **%40** ve altın çerçeveli, nabız gibi parlayan kod kutusu +
  sepete ekle butonunda sitedeki lacivert daire içinde beyaz artı ikonu +
  **%40 indirim kodu** (6 hane harf+rakam, tüm ürünlerde geçerli, tek kullanımlık, tek tuşla kopyala) +
  **"Ayrılmaz İkili'yi Sepete Ekle"** (sitenin kendi .add-to-cart-button akışı) → "Sepete git" linki.
- Çözen kullanıcı ve aldığı kod hatırlanır: HUD altın yıldız + "Lezzet · 5/5", buton "Kodun hazır: KOD".
- **DEMO kodları:** 2VBF9U, AD955A, UJ4E6U (getCode() rastgele birini verir). Gerçekte kodlar sunucudan sırayla, kişi başı bir tane gelecek; sadece getCode() değişecek.
- **Fiyat / ödül etiketi tamamen kaldırıldı** (tenekelerin altında kart yok).
- Önizleme sayfasında geliştirici çubuğu: Sıfırla / Oyunu aç / Çözülmüş hal / Ödül ekranı (siteye gitmez).
- GTM olayları: pgta_oyun_basladi, pgta_oyun_tamamlandi, pgta_kod_kopyalandi, pgta_sepete_ekle, pgta_odul_tekrar.
- "Delil yok" söylemi **kullanılmayacak**.
- **"Ayrılmaz İkili"** yazısı Kabut Hitam ile tenekelerin üstünde, tenekelere binmiyor (font sitede app.css ile yüklü).
- **"Hile" kelimesi hiçbir yerde kullanılmayacak.**
- Resmi "0 Şeker Kalori" logosu (img/0-seker-kalori-beyaz.svg, kaynak: 0-Seker-Kalori.pdf 2. sayfa).
  Lacivert versiyonu da img/0-seker-kalori-lacivert.svg olarak hazır.

## Açık konular
- Ayrılmaz İkili ürün ID'si (data-id="AYRILMAZ_IKILI_URUN_ID"), ürün linki (PAKET-LINKI-AYRILMAZ-IKILI), CDN görsel yolları.
- Kod kaynağı: kodların sırayla alınacağı yer (sunucu ucu) → getCode() buna bağlanacak. Kodlar panelde %40, tüm ürünler, tek kullanımlık tanımlı olmalı.
- Figma: "Ayrılmaz İkili – Ürün detay" başlığı (Kabut Hitam) elle güncellenecek; mobil versiyon en sona.
