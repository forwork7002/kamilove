# Kamilove — sotuv sahifasi (2+1 aksiya)

Jonli koʻrinish: https://forwork7002.github.io/kamilove/

Bitta `index.html` (HTML + CSS + JS, build kerak emas), `img/` — rasmlar (webp), `reels/` — videolar (mp4 + poster).
Dizayn LIPS 1-variantiga oʻxshatib qilingan: aksiya kartasi, katalog, yuz/tana parvarishi, videolar, buyurtma formasi, savollar.

## Narx va aksiyani oʻzgartirish

`index.html` ichida, `<script>` boshida — **SOZLAMALAR** bloki:

```js
const NEED = 2;      // 2 → "2+1", 3 → "3+1"
const PRODUCTS = [   // har bir mahsulot: nom, hajm, narx (soʻm), rasm, tavsif
  {id:'gel', ..., price:150000, ...},
];
```

Aksiya qoidasi: buyurtmada `NEED + 1` ta va undan koʻp mahsulot boʻlsa, **eng arzoni bepul** (bitta).
Eng arzon narxdagi mahsulotlar bir nechta boʻlsa, mijoz qaysi biri sovgʻa boʻlishini tanlaydi.

## Buyurtmalar

Forma `POST /api/order` ga yuboradi — LIPS saytidagi `server.js` bilan bir xil format
(`items`, `gift`, `bonus`, `name`, `phone`, `total`, `sum`, `site`, `page`, `utm`).
GitHub Pages'da server yoʻq, shuning uchun `*.github.io` da sahifa **koʻrish nusxasi** rejimida ishlaydi:
tepada ogohlantirish chiqadi va buyurtma hech qayerga yuborilmaydi.
Haqiqiy buyurtma olish uchun sahifani `server.js` bor serverga (`public/` papkasiga) qoʻyish kerak.

## Rasmlar va videolar

Manba: `IMG_.zip`. Rasmlar webp ga oʻtkazilgan, mahsulot rasmlarining fon shaffof (`p-*.webp`),
telefon uchun kichik nusxalari `p-*-s.webp`, `hero-s.webp`. Videolar H.264 mp4, 576×1024.
