# KlaraPaket

Färdiga digitala paket att skriva ut och köra direkt.

## Vad är detta projekt?

KlaraPaket är en enkel MVP-webbplats som erbjuder **gratis digitala aktivitetspaket** för föräldrar med barn i åldern 5–10 år. Syftet är att validera efterfrågan och samla in e-postadresser innan vi investerar i mer innehåll och funktionalitet.

## Vem är detta för?

- **Stressade föräldrar** som behöver snabba, roliga aktiviteter för sina barn
- **Föräldrar med barn 5–10 år** som letar efter gratis, utskrivbara aktiviteter
- Människor som värdesätter enkelhet och tydlighet över komplexa funktioner

## Varför är allt gratis?

I denna första version är allt helt gratis av flera anledningar:

1. **Validering**: Vi vill först se om det finns efterfrågan innan vi investerar mer tid och resurser
2. **Förtroende**: Genom att erbjuda något värdefullt gratis bygger vi förtroende med våra användare
3. **Enkelhet**: Genom att hålla det gratis undviker vi komplexitet kring betalningar, fakturering och kundservice
4. **Fokus**: Vi kan fokusera på att skapa bra innehåll och samla feedback istället för att bygga betalningssystem

## Hur fungerar e-postgating?

För närvarande är e-postformuläret en placeholder. När vi är redo att lansera kommer vi att:

1. **Integrera MailerLite**: Ersätta placeholder-formuläret med ett riktigt MailerLite-formulär
2. **Automatisera nedladdningar**: Konfigurera MailerLite att automatiskt skicka nedladdningslänkar via e-post när någon registrerar sig
3. **Hantera produkter**: Varje produkt kommer att ha sin egen nedladdningslänk som skickas automatiskt

Instruktioner för MailerLite-integration finns kommenterade i `index.html`.

## Vad betyder "framgång" för denna MVP?

För denna första version definierar vi framgång som:

- **E-postregistreringar**: Antal personer som lämnar sin e-postadress
- **Engagemang**: Antal nedladdningar som faktiskt görs (när MailerLite är integrerat)
- **Feedback**: Kvalitativ feedback från föräldrar om vad de tycker om produkterna
- **Validering**: Bekräftelse att det finns efterfrågan på gratis digitala aktivitetspaket

Vi letar INTE efter:
- Perfekt design (räcker med "rent och pålitligt")
- SEO-optimering
- Komplex funktionalitet
- Betalningar eller abonnemang

## Nuvarande MVP

Denna version innehåller:
- **Startsida** (`index.html`) med katalog över produkter
- **Produktsidor** (`/paket/*.html`) med detaljerad information och e-postformulär
- **MailerLite-placeholders** för framtida e-postintegration

## Teknisk struktur

```
klarapaket/
├── index.html          # Huvudsida med produkter
├── assets/
│   └── style.css      # Styling för webbplatsen
├── paket/             # Produktsidor
│   ├── superhjaltar.html
│   ├── pirater.html
│   └── kalas-superhjalte.html
└── README.md          # Denna fil
```

## Nästa steg

1. **Koppla MailerLite**: Ersätt placeholder-formulären med riktig MailerLite-integration
2. **Spåra taggar per produkt**: Konfigurera MailerLite att automatiskt tagga användare baserat på vilket paket de laddar ner
3. **Skapa produktfiler**: Skapa PDF-filer eller andra nedladdningsbara filer för varje aktivitetspaket
4. **Introducera PRO-paket**: I framtiden kan betalda PRO-paket läggas till för att generera intäkter
5. **Testa flödet**: Verifiera att e-postgating och nedladdningar fungerar smidigt
6. **Samla feedback**: Fråga användare vad de tycker och vad de vill ha mer av

## Deployment

Denna webbplats är designad för att deployas på:

- **Cloudflare Pages**: Dra och släpp mappen eller koppla till Git-repository
- **GitHub Pages**: Pusha till ett repository och aktivera GitHub Pages

Ingen build-process eller server krävs – det är ren HTML/CSS.

## Licens och användning

Detta är ett MVP-projekt för validering. Allt innehåll är gratis att använda för föräldrar.
