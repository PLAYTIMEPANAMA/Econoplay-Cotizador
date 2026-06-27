# ECONOPLAY — Cotizador de Productos

A web-based product estimating tool for **ECONOPLAY** (by Playtime Panama). Clients browse the product catalog, select items with quantities, fill out their contact info, and send a pre-formatted WhatsApp message directly to the sales team.

**Live demo:** *(paste your Netlify or GitHub Pages URL here)*

---

## How It Works

1. Client visits the page
2. Browses products by category or searches by name
3. Adds products and sets quantities
4. Fills out name, phone, email, and business name
5. Clicks **"Enviar Cotización por WhatsApp"**
6. WhatsApp opens with a formatted message ready to send

---

## How to Update Products

All products are defined in the `products` array inside `index.html`, starting around line 200 inside the `<script>` tag.

Each product looks like this:

```js
{ id: 1, name: "PALMERAS PARK Parque Infantil", price: 5700, cat: "Parques Infantiles", icon: "🌴", url: "parques-infantiles-panama-palmeras-park" },
```

| Field  | Description                                              |
|--------|----------------------------------------------------------|
| `id`   | Unique number — increment from the last one              |
| `name` | Product display name                                     |
| `price`| Price in USD (number, no $ sign)                         |
| `cat`  | Category — must be one of the four below                 |
| `icon` | Emoji shown on the product card                          |
| `url`  | Slug from playtimepanama.com/product-page/...            |

### Valid Categories

- `"Parques Infantiles"`
- `"Maquinas Biosaludables"`
- `"Mobiliario Urbano"`
- `"Parques Caninos"`

### To add a new product

Copy any existing line, paste it at the end of the array (before the `];`), update the fields, and make sure the `id` is unique.

### To remove a product

Delete its line from the `products` array.

### To update a price

Change the `price` value on that product's line.

---

## How to Change the WhatsApp Number

Find this line near the top of the `<script>` tag:

```js
const WHATSAPP_NUMBER = "50760903223";
```

Replace `50760903223` with your number in international format — country code first, no `+`, no spaces, no dashes.

> Panama example: +507 6000-0000 → `"50760000000"`

---

## Deployment

This is a single `index.html` file with no dependencies or build step.

### Netlify (recommended)
1. Go to [netlify.com/drop](https://netlify.com/drop)
2. Drag and drop `index.html`
3. Share the generated URL

### GitHub Pages
1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your app will be live at `https://yourusername.github.io/repo-name`

---

## Contact

**Playtime Panama / ECONOPLAY**
WhatsApp: +507 6090-3223
Website: [playtimepanama.com](https://www.playtimepanama.com)
