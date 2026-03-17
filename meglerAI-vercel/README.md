# MeglerAI — Deploy til Vercel

## Struktur
```
meglerAI-vercel/
├── api/
│   └── generer.js       ← Backend-rute (håndterer Anthropic API-kall)
├── public/
│   └── index.html       ← Nettsiden
├── vercel.json
└── package.json
```

## Deploy (tar ~3 minutter)

### 1. Skaff Anthropic API-nøkkel
Gå til https://console.anthropic.com → API Keys → Create Key

### 2. Installer Vercel CLI (én gang)
```bash
npm install -g vercel
```

### 3. Deploy
```bash
cd meglerAI-vercel
vercel
```
Følg instruksjonene i terminalen (logg inn med GitHub/Google).

### 4. Legg til API-nøkkel i Vercel
Gå til https://vercel.com → ditt prosjekt → Settings → Environment Variables

Legg til:
- **Name:** `ANTHROPIC_API_KEY`
- **Value:** `sk-ant-...` (din nøkkel)
- **Environment:** Production + Preview + Development

### 5. Redeploy
```bash
vercel --prod
```

Nettsiden er nå live med fungerende salgsoppgave-generator! 🎉

## Lokal utvikling
```bash
# Lag .env.local fil
echo "ANTHROPIC_API_KEY=sk-ant-din-nokkel" > .env.local

# Start lokalt
vercel dev
```
Åpne http://localhost:3000
