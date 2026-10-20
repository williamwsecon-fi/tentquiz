# Tentquiz

Öva inför tentan med AI-frågor byggda på ditt eget kursmaterial.

**Öppna appen: https://williamwsecon-fi.github.io/tentquiz/**

- En mapp per tenta på datorn – lägg föreläsningsbilder, anteckningar och kompendier där (PDF, Word, PowerPoint, text eller bilder).
- Formler läses in från Words och PowerPoints formelverktyg och visas uppställda i frågor och förklaringar. Tabeller och talaranteckningar i PowerPoint kommer också med.
- Bilder, diagram, skannade sidor och PDF-sidor med figurer eller formler kan läsas av en AI-modell som ser bilder (*Läs bilderna* på tentans sida). Det görs en gång per bild och sparas.
- Beskriv tentans upplägg (frågetyper, poäng, minuspoäng, tid, vitsordsskala), eller klistra in lärarens information och låt AI:n fylla i det.
- Snabbövning med nya frågor varje gång, provtenta med tid och vitsord, AI-rättning av kortsvar, räkneuppgifter och essäer, repetition av missade frågor och statistik per ämnesområde.

## Kom igång (gratis)

1. **Öppna Tentquiz → Inställningar** och tryck *Logga in med OpenRouter*. Har du inget konto skapar du ett där – det är gratis och kräver inget kort.
2. **Godkänn** att Tentquiz får en nyckel. Du skickas tillbaka till appen och nyckeln sparas automatiskt. (Vill du hellre skapa nyckeln själv under [Settings → Keys](https://openrouter.ai/settings/keys) kan du klistra in den under *Klistra in en nyckel själv i stället*.)
3. **Välj en gratismodell** i listan (rutan *Visa bara gratismodeller* är ikryssad från början). Välj gärna en modell som kan läsa minst 128k, så får allt kursmaterial plats.
4. **Lägg till tentamapp** och välj mappen med ditt kursmaterial. Öppna *Inställningar för tentan* och klistra in vad läraren sagt om tentan.

Nyckeln sparas bara i din egen webbläsare och skickas bara till OpenRouter. Var och en som använder appen har sin egen nyckel.

Nyckeln finns kvar tills du loggar ut. Om den ändå försvinner mellan gångerna: använd inte privat fönster, och kontrollera att webbläsaren inte rensar webbplatsdata när den stängs. Varje inloggning skapar en ny nyckel med namnet *Tentquiz* i ditt OpenRouter-konto – gamla kan tas bort under Keys.

## Vad gratis räcker till

Gratismodellerna på OpenRouter (de som slutar på `:free`) kostar ingenting, men har gränser:

| | Gräns |
|---|---|
| Utan köpta krediter | **50 anrop per dag** till gratismodeller |
| Har köpt minst 10 krediter (≈ 10 $) | **1 000 anrop per dag** till gratismodeller |
| Dessutom | Ett tak för antal anrop per minut, och gratismodeller kan vara tillfälligt överbelastade |

Ungefär så mycket går åt i appen:

| | Anrop |
|---|---|
| En omgång snabbövning (10 frågor) | 1 |
| Rätta ett kortsvar eller en essä | 1 |
| Provtenta med 50 flervalsfrågor | 4–5 |
| Dela in materialet i ämnesområden / fylla i upplägget | 1 vardera |
| Läsa in bilder (görs en gång) | 1 per upp till 4 bilder |

50 anrop per dag räcker alltså till ungefär 30–40 omgångar snabbövning, eller några provtentor plus övning.

Tänk också på att gratismodeller ofta är svagare än betalmodeller: frågorna kan bli enklare och oftare innehålla fel (använd knappen *Frågan verkar fel – stryk den*), och essärättningen blir mindre träffsäker. Vilka gratismodeller som finns ändras med tiden – om en modell slutar fungera, välj en annan i listan. Vissa gratismodeller får dessutom bara användas i utvalda appar hos OpenRouter. Tentquiz testar därför varje modell när du väljer den och gömmer de som inte fungerar.

## Om gratis inte räcker

Får du meddelandet *Gränsen är nådd*, eller tycker att frågorna blir för dåliga:

1. **Vänta eller byt gratismodell.** Gränsen per minut släpper efter en stund, och en annan gratismodell kan vara mindre belastad.
2. **Köp krediter för 10 $** på OpenRouter under [Credits](https://openrouter.ai/settings/credits). Då höjs gränsen för gratismodellerna till 1 000 anrop per dag – och krediterna finns kvar så länge du bara använder gratismodeller. (OpenRouter tar en avgift på 5,5 %, minst 0,80 $, när man köper krediter.)
3. **Byt till en billig betalmodell.** Avmarkera *Visa bara gratismodeller* – listan visas då med de billigaste först. Billiga modeller kostar ofta bara någon cent per omgång frågor, beroende på hur mycket material kursen har (materialet skickas med i varje anrop). Vill du ha bättre essärättning, välj en starkare och dyrare modell.
4. **Sätt en utgiftsgräns** på nyckeln under [Keys](https://openrouter.ai/settings/keys) om du vill vara säker på att aldrig betala mer än en viss summa. Under *Inställningar → Testa nyckeln* i appen ser du hur mycket du har använt.

## Var sparas data?

| | Var |
|---|---|
| Kursmaterial | I tentans mapp på datorn (dina egna filer – appen bara läser dem) |
| Upplägg, ämnesområden, statistik, missade frågor | `tentquiz.json` i tentans mapp |
| Utläst text från filerna och beskrivningar av bilderna (cache) | `tentquiz-text.json` i tentans mapp |
| Listan över tentor och API-nyckeln | I webbläsaren |

Mappfunktionen kräver Chrome eller Edge på dator. I andra webbläsare (Safari, Firefox, telefon) sparas tentorna i webbläsaren i stället och man laddar upp filerna.

Materialet skickas till OpenRouter och den valda modellens leverantör när frågor skapas och rättas. Använd inte material du inte får dela med en AI-tjänst. Vissa gratismodeller kan använda det som skickas för att träna modeller – läs villkoren för modellen på OpenRouter.

## Teknik

En enda statisk HTML-fil utan byggsteg. Bibliotek laddas från cdnjs vid behov: pdf.js (PDF), JSZip (Word och PowerPoint, inklusive formler och bilder), mammoth (reserv för Word) och KaTeX (visar formler). AI-anrop går direkt från webbläsaren till OpenRouters API.
