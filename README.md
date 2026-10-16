# Kamilove — sotuv sahifasi (2+1 aksiya), 4 xil dizayn

Jonli koʻrinish: https://forwork7002.github.io/kamilove/ — bosh sahifada 4 variantni tanlash mumkin.

| Papka | Dizayn | Qisqacha |
|---|---|---|
| `v1/` | Ink & Pastel | oq fon, myatniy aksiya kartasi, qora-oq marmar; keng sahifa (LIPS 1-variantiga oʻxshash) |
| `v2/` | Bir ustun | telefon ekranidek tor bitta ustun, narx jadvali (LIPS 2-variantiga oʻxshash) |
| `v3/` | Noir Marble | toʻq fon, galereya uslubi, katta sarlavhalar |
| `v4/` | Pastel Bento | yorliq ranglaridagi kataklar, quvnoq |
| `v5/` | Oq + qizil | oddiy tovarka sahifasi: Enzim pudra + skrab + gel sovgʻa, 290 000 soʻm, 5 blok |
| `v6/` | Oq + yashil | v5 bilan bir xil, tugmalar yashil |
| `v7/` | Oq + qora | v5 bilan bir xil, qora-oq, narx qizil |

Har bir variant — bitta `index.html` (HTML + CSS + JS, build kerak emas). Umumiy fayllar ildizda:
`img/` (rasmlar, webp), `reels/` (videolar), `previews/` (bosh sahifa uchun skrinshotlar).
Mahsulotlar, narxlar, aksiya va buyurtma mantigʻi toʻrttalasida bir xil — farqi faqat dizaynda.

## Narx va aksiyani oʻzgartirish

Har bir variantning `index.html` faylida, `<script>` boshida — **SOZLAMALAR** bloki:

```js
const NEED = 2;      // 2 → "2+1", 3 → "3+1"
const PRODUCTS = [   // har bir mahsulot: nom, hajm, narx (soʻm), rasm, tavsif
  {id:'gel', ..., price:150000, ...},
];
```

Aksiya qoidasi: buyurtmada `NEED + 1` ta va undan koʻp mahsulot boʻlsa, **eng arzoni bepul** (har bir buyurtmada bitta).
Eng arzon narxdagi mahsulotlar bir nechta boʻlsa, mijoz qaysi biri sovgʻa boʻlishini tanlaydi.
Narxni oʻzgartirsangiz — toʻrttala variantda ham oʻzgartiring.

## Buyurtmalar

Forma `POST /api/order` ga yuboradi — LIPS saytidagi `server.js` bilan bir xil format
(`items`, `gift`, `bonus`, `name`, `phone`, `total`, `sum`, `site`, `page`, `utm`, `hp`).
GitHub Pages'da server yoʻq, shuning uchun `*.github.io` da sahifa **koʻrish nusxasi** rejimida ishlaydi:
tepada ogohlantirish chiqadi va buyurtma hech qayerga yuborilmaydi.
Haqiqiy buyurtma olish uchun tanlangan variantni `server.js` bor serverga qoʻyish kerak
(variant `index.html` + `img/` + `reels/`; bunda rasm yoʻllari `../img/` → `img/` boʻladi).

## Rasmlar va videolar

Manba: `IMG_.zip`. Rasmlar webp ga oʻtkazilgan, mahsulot rasmlarining foni shaffof (`p-*.webp`),
telefon uchun kichik nusxalari `p-*-s.webp`, `hero-s.webp`. Videolar H.264 mp4, 576×1024.

## v5–v7 (Enzim pudra 290 000)

Bitta taklif: Papaya enzim pudra + tana skrabi (mijoz hidini tanlaydi) + yuvinish geli sovgʻa. Narx `index.html` dagi SOZLAMALAR blokida (`PRICE`). Buyurtma `/api/order` ga `items` (pudra, skrab) va `gift` (gel) bilan, `site: 'KAMILOVE ENZIM 290'` belgisi bilan ketadi.
