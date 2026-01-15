# Nordal Store Locator

Simpel store locator der henter data fra Google Sheets og gør det tilgængeligt via CDN.

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Test connection
npm test

# Update store data
npm run update

# Deploy til GitHub
npm run deploy
```

## 📦 CDN URL

Efter data er pushed til GitHub, er det tilgængeligt på:

```
https://cdn.jsdelivr.net/gh/NicoBang/nordal-store-locator@main/stores.min.json
```

## 📊 Data Source

- **Google Sheet:** [View/Edit](https://docs.google.com/spreadsheets/d/1cDrpjLdUyvpKR1_1iPos94Q9q_kEDQR2IVMBBNAWe8w)
- **Sheet Name:** store_finder_import

## 🔄 Automatisk Opdatering

Data opdateres automatisk hver dag kl. 07:00 CET via GitHub Actions.

### Manuel opdatering

1. Rediger data i Google Sheet
2. Kør: `npm run update`
3. Push til GitHub: `git push`

## 📁 Output Filer

- `stores.json` - Formateret JSON (læsbar)
- `stores.min.json` - Minified JSON (til produktion)
- `stores.csv` - CSV format

## 📝 Google Sheet Kolonner

Påkrævede kolonner:
- Company
- Address
- Postal Code
- City
- Country
- Phone
- Website

Valgfrie kolonner:
- Email
- Physical (marker med "X")
- Online (marker med "X")
- Enhver anden kolonne du ønsker

## 🔒 Sikkerhed

- API keys gemmes i `.env` (committes aldrig)
- GitHub Secrets bruges til automation
- Google Sheet skal være delt som "Alle med link kan se"

## 🛠️ Shopify Integration

I din Shopify butik kan du bruge data sådan:

```javascript
fetch('https://cdn.jsdelivr.net/gh/NicoBang/nordal-store-locator@main/stores.min.json')
  .then(response => response.json())
  .then(stores => {
    // Brug stores data til at vise butikker
    console.log(stores);
  });
```

---
Generated: 2026-01-15T09:22:26.516Z
