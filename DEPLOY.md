# Deployment-guide för Cloudflare Pages

Denna guide visar steg-för-steg hur du deployar KlaraPaket till Cloudflare Pages.

## Steg 1: Skapa nytt Pages-projekt

1. Logga in på [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. I vänstermenyn, klicka på **"Pages"** (eller gå direkt till [dash.cloudflare.com/pages](https://dash.cloudflare.com/pages))
3. Klicka på knappen **"Create a project"**
4. Välj **"Connect to Git"**

## Steg 2: Koppla GitHub-konto

1. Om du inte redan är inloggad med GitHub, klicka på **"Connect GitHub"**
2. Följ instruktionerna för att auktorisera Cloudflare Pages att komma åt dina repositories
3. Välj vilka repositories Cloudflare ska ha tillgång till (rekommenderat: bara det specifika repot eller alla)

## Steg 3: Välj repository

1. I listan över repositories, hitta och välj **`bltg85/klarapaket`**
2. Klicka på **"Begin setup"**

## Steg 4: Konfigurera build-inställningar

Fyll i följande inställningar:

- **Project name**: `klarapaket` (eller valfritt namn)
- **Production branch**: `main`
- **Framework preset**: Välj **"None"** (eller "Plain HTML")
- **Build command**: Lämna **tomt** (ingen build behövs)
- **Build output directory**: `/` (root-mappen)

## Steg 5: Deploy

1. Klicka på **"Save and Deploy"**
2. Vänta medan Cloudflare bygger och deployar projektet (tar vanligtvis 1-2 minuter)
3. När deployment är klar visas en grön checkmark

## Steg 6: Hitta din live URL

1. Efter deployment, klicka på projektnamnet för att öppna projektet
2. Du hittar din live URL under **"Custom domains"** eller i övre högra hörnet
3. URL:en ser ut som: `https://klarapaket.pages.dev` (eller liknande)

## Så här triggar du en ny deployment

Cloudflare Pages deployar automatiskt när du pushar till `main`-branchen:

1. Gör ändringar i ditt projekt lokalt
2. Committa ändringarna: `git commit -m "Beskrivning av ändringar"`
3. Pusha till GitHub: `git push origin main`
4. Cloudflare kommer automatiskt att detektera push:en och starta en ny deployment
5. Du kan se deployment-status i Cloudflare Dashboard under ditt projekt

**Manuell redeploy:**
- Gå till ditt projekt i Cloudflare Pages
- Klicka på **"Deployments"**-fliken
- Hitta den senaste deployment:en och klicka på de tre prickarna (...)
- Välj **"Retry deployment"** för att deploya samma version igen

## Lägga till egen domän (högnivå)

1. Gå till ditt projekt i Cloudflare Pages
2. Klicka på fliken **"Custom domains"**
3. Klicka på **"Set up a custom domain"**
4. Ange din domän (t.ex. `klarapaket.se`)
5. Följ instruktionerna för att konfigurera DNS:
   - Om din domän redan är på Cloudflare: DNS uppdateras automatiskt
   - Om din domän är på annan provider: Lägg till CNAME-post enligt instruktionerna
6. Vänta på att SSL-certifikatet genereras (tar vanligtvis några minuter)

## Felsökning

**Problem: Sidan visar 404**
- Kontrollera att `index.html` finns i root-mappen
- Verifiera att "Build output directory" är satt till `/`

**Problem: CSS laddas inte**
- Kontrollera att sökvägar är relativa (inte absoluta)
- Verifiera att `assets/style.css` finns

**Problem: Länkar fungerar inte**
- Kontrollera att alla länkar är relativa (t.ex. `paket/superhjaltar.html` inte `/paket/superhjaltar.html`)
