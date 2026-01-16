# KlaraPaket Produktmaskin

Detta system hjälper dig att skapa nya digitala aktivitetspaket på ett konsekvent sätt.

## Översikt

Produktmaskinen använder strukturerat YAML-innehåll som sedan används för att skapa PDF:er. Processen är:

1. **AI genererar innehåll** → `content.yaml` (enligt `content-schema.yaml`)
2. **Manuell layout** → PDF-mall i Slides/Canva
3. **Produkt klar** → Lägg i `/products/[produktnamn]/`

## Skapa en ny produkt

### Steg 1: Generera innehåll

1. Öppna `master-prompt.md`
2. Fyll i parametrar: produktnamn, ålder, tema, antal ledtrådar
3. Skicka prompten till AI (t.ex. ChatGPT/Cursor)
4. Kopiera den returnerade YAML:n

### Steg 2: Spara innehåll

1. Skapa ny mapp: `/products/[produktnamn]/`
2. Kopiera `/products/_TEMPLATE/content.yaml` till den nya mappen
3. Klistra in det genererade innehållet i `content.yaml`

**Eller** kopiera och redigera exempel:
```bash
cp machine/examples/skattjakt-superhjaltar.yaml products/mitt-paket/content.yaml
```

### Steg 3: Skapa PDF

Använd `content.yaml` som källa för att manuellt skapa PDF:n i:

- **Google Slides**: Skapa en presentation enligt mall, fyll i från YAML
- **Canva**: Använd mall-template, kopiera innehåll från YAML
- **LaTeX/InDesign**: Mer avancerat, samma princip

### Steg 4: Spara produkten

Lägg allt i produktmappen:
```
/products/mitt-paket/
  ├── content.yaml          # Strukturerat innehåll
  ├── paket.pdf            # Färdig PDF
  └── README.md            # Kort produktinfo (valfritt)
```

## Filstruktur

```
machine/
  ├── content-schema.yaml    # Kontrakt för alla produkter
  ├── master-prompt.md       # Prompt för AI-generering
  ├── examples/              # Fyllda exempel
  └── README.md             # Denna fil

products/
  ├── _TEMPLATE/            # Mall att kopiera
  │   └── content.yaml
  └── [produktnamn]/        # Individuella produkter
      ├── content.yaml
      └── paket.pdf

assets/themes/              # Framtida användning (t.ex. temat-filer)
```

## Checklist: Produkt klar

För att en produkt ska vara klar för publicering:

- [ ] `content.yaml` följer `content-schema.yaml`
- [ ] Alla fält i YAML är ifyllda (inga tomma strings)
- [ ] Gåtor/riddles är lämpliga för åldern
- [ ] Instruktioner är tydliga och enkla att följa
- [ ] PDF är skapad enligt innehållet
- [ ] PDF är testad (läsbar, korrekt layout)
- [ ] Produktmapp finns i `/products/[produktnamn]/`

## Tips

- **Använd exempel**: Börja med `machine/examples/skattjakt-superhjaltar.yaml` som referens
- **Testa gåtor**: Kolla att gåtorna fungerar för angiven ålder
- **Kort är bättre**: Håll instruktioner och texter korta
- **Konsekvent ton**: Alltid skriv till föräldern, trevlig ton

## Nästa steg (framtida)

- Automatisering: Script som läser YAML och genererar PDF
- Maller: Färdiga PDF-mallar per produkttyp
- Validering: Automatisk kontroll att YAML följer schema
