Här är ett konkret nästa steg: gör om från “3 kort + popup-form” till:

/paket/ med riktiga landningssidor per paket

en enkel katalog-sida (startsidan) som länkar vidare

email-gate på produktsidan, inte via JS-alert

Nedan får du allt du behöver: filstruktur + färdig HTML-copy (svenska) + minimal JS (bara för att spara vilket paket).

1) Ny filstruktur (rekommenderad)

Skapa detta i projektet:

digitalgifts/
  index.html
  assets/
    style.css
  paket/
    superhjaltar.html
    pirater.html
    kalas-superhjalte.html

2) Uppdatera startsidan: index.html

Byt subtitle-texten och gör korten till länkar till produktsidor.

<!DOCTYPE html>
<html lang="sv">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Gratis aktivitetspaket för barn (5–10 år)</title>
  <link rel="stylesheet" href="assets/style.css" />
</head>
<body>
  <div class="container">
    <header>
      <h1>Gratis aktivitetspaket för barn (5–10 år)</h1>
      <p class="subtitle">
        Utskrivbara lekar och färdiga upplägg som funkar direkt hemma.
        Välj ett tema, få länken via email, skriv ut och kör.
      </p>
    </header>

    <main>
      <section class="products">
        <a class="product-card" href="paket/superhjaltar.html">
          <h2>Skattjakt – Superhjältar</h2>
          <p class="age-range">5–7 år</p>
          <p class="description">Gåtor, ledtrådar och ett färdigt upplägg i superhjältetema.</p>
          <span class="badge">Gratis – få via email</span>
          <span class="cta-link">Visa paket →</span>
        </a>

        <a class="product-card" href="paket/pirater.html">
          <h2>Skattjakt – Pirater</h2>
          <p class="age-range">6–8 år</p>
          <p class="description">Piratäventyr med karta, ledtrådar och finalskatt.</p>
          <span class="badge">Gratis – få via email</span>
          <span class="cta-link">Visa paket →</span>
        </a>

        <a class="product-card" href="paket/kalas-superhjalte.html">
          <h2>Kalaspaket – Superhjälte</h2>
          <p class="age-range">6–9 år</p>
          <p class="description">Enkel plan + printables: inbjudan, lekar och diplom.</p>
          <span class="badge">Gratis – få via email</span>
          <span class="cta-link">Visa paket →</span>
        </a>
      </section>
    </main>

    <footer>
      <p>Allt är gratis i starten. Inga abonnemang. Bara färdiga paket du kan använda direkt.</p>
    </footer>
  </div>
</body>
</html>


Notera: Jag bytte “button + JS” till länkar – bättre för känsla, SEO senare och enklare struktur.

3) Exempel på riktig produktsida: paket/superhjaltar.html

Det här är en “landningssida” som känns som en produkt, men fortfarande gratis.

<!DOCTYPE html>
<html lang="sv">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Skattjakt – Superhjältar (5–7 år) | Gratis paket</title>
  <link rel="stylesheet" href="../assets/style.css" />
</head>
<body>
  <div class="container">
    <header>
      <a href="../index.html" class="back-link">← Tillbaka</a>
      <h1>Skattjakt – Superhjältar</h1>
      <p class="subtitle">Ett färdigt upplägg med ledtrådar och gåtor. Skriv ut och kör.</p>
    </header>

    <main>
      <section class="product-hero">
        <div class="product-meta">
          <span class="badge">Gratis – få via email</span>
          <p class="age-range">Rekommenderad ålder: <strong>5–7 år</strong></p>
          <p class="time">Tid: <strong>30–45 min</strong> • Förberedelser: <strong>10 min</strong></p>
        </div>

        <div class="product-details">
          <h2>Det här ingår</h2>
          <ul>
            <li>8 ledtrådar/gåtor (utskrivbara)</li>
            <li>Instruktionsblad: hur du sätter upp skattjakten</li>
            <li>Finalkort + “superhjälte-diplom”</li>
          </ul>

          <h2>Du behöver</h2>
          <ul>
            <li>Sax (valfritt), tejp</li>
            <li>En liten “skatt” (godis/leksak/klistermärken)</li>
          </ul>
        </div>
      </section>

      <section class="email-form-section">
        <div class="email-form-container">
          <h2>Få paketet via email</h2>
          <p class="form-description">
            Skriv din e-postadress så skickar vi en nedladdningslänk.
          </p>

          <!-- MailerLite placeholder -->
          <form class="email-form" onsubmit="handleSubmit(event)">
            <input type="email" required class="email-input" placeholder="Din e-postadress" />
            <input type="hidden" name="product" value="superhjaltar" />
            <button class="submit-button" type="submit">Skicka mig länken</button>
          </form>

          <p class="privacy-note">Du kan avregistrera dig när som helst.</p>
        </div>
      </section>

      <section class="product-faq">
        <h2>Vanliga frågor</h2>
        <details>
          <summary>Är det verkligen gratis?</summary>
          <p>Ja. I starten är alla paket gratis – vi vill bara veta vilka teman som är mest populära.</p>
        </details>
        <details>
          <summary>Funkar det utan färgskrivare?</summary>
          <p>Ja, det ska fungera även i svartvitt.</p>
        </details>
      </section>
    </main>

    <footer>
      <p><a href="../index.html">Se fler gratis paket</a></p>
    </footer>
  </div>

  <script>
    function handleSubmit(event) {
      event.preventDefault();
      alert('Tack! När MailerLite är integrerat skickas länken direkt till din e-post.');
    }
  </script>
</body>
</html>


Kopiera den och gör två varianter för pirater + kalas.

4) Liten CSS-justering (så korten funkar som länkar)

I din assets/style.css (lägg till om det saknas):

.product-card {
  display: block;
  text-decoration: none;
  color: inherit;
}

.cta-link {
  display: inline-block;
  margin-top: 10px;
  font-weight: 600;
}
.back-link {
  display: inline-block;
  margin-bottom: 10px;
  text-decoration: none;
}

5) Ny copy som inte säger “stressade”

Om du vill ha en ännu mer “premium-neutral” ton kan du byta subtitle på startsidan till:

“När du vill ha något som funkar direkt – utan att planera i timmar.”

“Färdiga upplägg att skriva ut och köra hemma.”

“Aktiviteter som sparar tid och ger en kul stund.”