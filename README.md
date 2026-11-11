# PIN Drinks — Ayrılmaz İkili ana sayfa bileşeni

pindrinks.com ana sayfası için GTA temalı kampanya bileşeni.
**Ana söylem:** "Peşindeki tek şey 5 yıldızlı lezzet." · **Görev:** Şekeri sıfırla.

## Önizleme

- **Canlı önizleme:** GitHub Pages linki (depo ayarlarında *Pages* bölümünde).
- **Yerelde:** klasörde bir sunucu açıp `onizleme.html`'yi açın:
  ```bash
  python3 -m http.server 8765
  ```
  ardından `http://localhost:8765/onizleme.html`.

Önizleme sayfasının altındaki çubukla bileşenin her hali tek tıkla görülebilir:
**Sıfırla (ilk hal)**, **Oyunu aç**, **Çözülmüş hal**, **Ödül ekranı**. Bu çubuk sadece önizlemede var, siteye gitmez.

## Akış

1. **Bekleme hali:** 5 aranma yıldızı (GTA tarzı kırmızı/mavi yanıp söner), başlık, "Göreve Başla: İndirim Kodunu Al" butonu.
2. **Mini oyun:** tenekelerin etrafında süzülen 5 şeker küpü. Her dokunuş bir küpü patlatır, bir yıldızı altına çevirir ve Şeker/Kalori barlarını azaltır. Masaüstünde bölümün içinde, mobilde tam ekran açılır.
3. **Ödül ekranı:** %40 indirim kodu (tek tuşla kopyala) + "Ayrılmaz İkili'yi Sepete Ekle".
4. Kodu alan kullanıcı tarayıcıda hatırlanır; yıldızlar altın kalır, yanında 0 Şeker Kalori logosu görünür.

## Dosyalar

| Dosya | Ne işe yarar |
|---|---|
| `aranma-seviyesi-sifir.html` | **Siteye konacak bileşen.** CSS + HTML + JS tek dosyada, stiller `.pgta-` önekiyle izole. |
| `onizleme.html` | Sadece önizleme: site ortamını taklit eder, bileşeni yükler, geliştirici çubuğu içerir. |
| `img/` | Teneke görselleri (WebP) ve 0 Şeker Kalori logosu (SVG, beyaz/lacivert). |
| `TASARIM-NOTLARI.md` | Tasarım kararları ve açık konular. |

## Yayına almadan önce

1. `data-id="AYRILMAZ_IKILI_URUN_ID"` → Ayrılmaz İkili paketinin ürün ID'si (sayı). Sepete ekleme sitenin kendi `.add-to-cart-button` akışını kullanır.
2. `getCode()` → kodları sunucudan tek kullanımlık ve kişi başı bir tane alacak şekilde bağlanmalı. Şu an **demo** kodlar kullanılıyor: `2VBF9U`, `AD955A`, `UJ4E6U` (gerçek değil). Kodlar panelde %40, tüm ürünlerde geçerli ve tek kullanımlık tanımlanmalı.
3. `PAKET-LINKI-AYRILMAZ-IKILI` → paketin ürün sayfası linki.
4. `img/...` yolları → CDN adresleri (`cdn.pindrinks.com/...`).

Fontlar (Poppins, Kabut Hitam) sitede zaten yüklü. GTM olayları: `pgta_oyun_basladi`, `pgta_oyun_tamamlandi`, `pgta_kod_kopyalandi`, `pgta_sepete_ekle`, `pgta_odul_tekrar`.
