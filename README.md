# Orman Nefesim — yayınlanan site

Bu depo **yalnızca derlenmiş statik siteyi** barındırır (GitHub Pages).
Elle düzenlenmez; `orman-nefesim-kod` deposundaki kaynaktan üretilir.

🌐 https://alidevai.github.io/orman-nefesim/
📦 Kaynak kod: https://github.com/alidevai/orman-nefesim-kod

---

## ⚠️ Bu bir uyarı sistemi değildir

Deneysel bir araştırma prototipidir. Resmî bir kurum ürünü değildir, resmî yangın
verilerine dayanmaz ve **resmî uyarı yerine geçmez**. Model doğrulaması yapılmış
ve şanstan ayırt edilememiştir (ROC-AUC 0.44–0.57, %95 güven aralığı 0.50'yi
içeriyor). Ölçüm yöntemi kaynak depodaki `05_Model_Accuracy.md` dosyasındadır.

- Yangın ihbarı: **177** (ALO 177) · Acil durum: **112**
- Resmî kaynaklar: [OGM](https://www.ogm.gov.tr) · [AFAD](https://www.afad.gov.tr) · [MGM](https://www.mgm.gov.tr)

## Statik yayın kısıtı

GitHub Pages'te sunucu çalışmaz. Risk verisi `data/risk.geojson` dosyasından
okunur; **detaylandırma, alarm listesi ve aktif yangın katmanı** API gerektirdiği
için bu demoda devre dışıdır.

## Yeniden üretim

```bash
# kaynak depoda
python scripts/build_risk_geojson.py --aoi turkey --out apps/web/public/data/risk.geojson
cd apps/web && npx next build      # out/ üretir
```

Veri kaynakları ve lisansları: Open-Meteo, NASA FIRMS, Copernicus (CORINE,
EFFIS/GWIS), Kontur Population (CC BY 4.0), OpenStreetMap/CARTO (ODbL),
Mapzen/AWS Terrain Tiles.
