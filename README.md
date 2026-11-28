# Hanımefendi Butik · Efsane Cuma Kürk Kampanyası

İki ayrı parça, ikas'a ayrı ayrı eklenir. Sayaç **her gece 00:00'da (Türkiye saati) sıfırlanır** ve yeniden 24 saat geri sayar. Sabit bir bitiş için `AYAR.bitis`'e tarih yazılır (örn. `"2026-11-30T23:59:59+03:00"`).

| Dosya | Adres | Nereye |
|---|---|---|
| `kurk-slayt.html` | https://uzaydijital.github.io/hanimefendi-kampanya/kurk-slayt.html | Anasayfa – ürün slaytı + sayaç |
| `kurk-kategori-sayac.html` | https://uzaydijital.github.io/hanimefendi-kampanya/kurk-kategori-sayac.html | Kategori sayfalarının üstü |

## 1) Anasayfa – ürün slaytı

```html
<iframe id="kurk-slayt" src="https://uzaydijital.github.io/hanimefendi-kampanya/kurk-slayt.html"
  style="width:100%;border:0;display:block;height:720px" loading="lazy" title="Kürk kampanyası"></iframe>
<script>
window.addEventListener("message",function(e){
  if(e.data&&e.data.tip==="kurk-kampanya-yukseklik"&&e.data.mod==="slayt")
    document.getElementById("kurk-slayt").style.height=e.data.h+"px";
});
</script>
```

## 2) Kategori sayfası üstü – sayaç bandı

```html
<iframe id="kurk-bant" src="https://uzaydijital.github.io/hanimefendi-kampanya/kurk-kategori-sayac.html"
  style="width:100%;border:0;display:block;height:110px" loading="lazy" title="Kürk kampanya sayacı"></iframe>
<script>
window.addEventListener("message",function(e){
  if(e.data&&e.data.tip==="kurk-kampanya-yukseklik"&&e.data.mod==="bant")
    document.getElementById("kurk-bant").style.height=e.data.h+"px";
});
</script>
```

Script eklenemezse sadece `<iframe>` satırı yeterli (yükseklik sabit kalır; mobilde slayt için ~1000px, bant için ~170px).

## İndirimin kendisi
Sayaç sadece duyurudur. %5'in sepette düşmesi için ikas → Pazarlama → Kampanyalar → Sepette indirim, koşul *Kategori = Kürk*, %5, 27.11.2026 23:59'a kadar.

## Ürün / tarih değiştirme
Her dosyanın içindeki `AYAR` bloğu: `bitis` (boş = her gece sıfırlanır), `urunler` (ad, fiyat, link, görsel), `kategoriLink`. GitHub'da dosyayı ✏️ ile düzenleyip Commit'lemek yeterli; ikas tarafına dokunmaya gerek yok.
