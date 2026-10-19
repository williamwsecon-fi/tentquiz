# Tentquiz

Öva inför tentan med AI-frågor byggda på ditt eget kursmaterial.

**Öppna appen: https://williamwsecon-fi.github.io/tentquiz/**

- En mapp per tenta på datorn – lägg föreläsningsbilder, anteckningar och kompendier där (PDF, Word, PowerPoint eller text).
- Beskriv tentans upplägg (frågetyper, poäng, minuspoäng, tid, vitsordsskala), eller klistra in lärarens information och låt AI:n fylla i det.
- Snabbövning med nya frågor varje gång, provtenta med tid och vitsord, AI-rättning av kortsvar, räkneuppgifter och essäer, repetition av missade frågor och statistik per ämnesområde.

## Kom igång (gratis)

1. **Skapa ett konto på [OpenRouter](https://openrouter.ai).** Det är gratis och kräver inget kort.
2. **Skapa en API-nyckel** under [Settings → Keys](https://openrouter.ai/settings/keys). Kopiera den – den visas bara en gång.
3. **Öppna Tentquiz → Inställningar**, klistra in nyckeln och tryck *Spara nyckeln*.
4. **Välj en gratismodell** i listan (rutan *Visa bara gratismodeller* är ikryssad från början). Välj gärna en modell som kan läsa minst 128k, så får allt kursmaterial plats.
5. **Lägg till tentamapp** och välj mappen med ditt kursmaterial. Öppna *Inställningar för tentan* och klistra in vad läraren sagt om tentan.

Nyckeln sparas bara i din egen webbläsare och skickas bara till OpenRouter. Var och en som använder appen har sin egen nyckel.

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
| Utläst text från filerna (cache) | `tentquiz-text.json` i tentans mapp |
| Listan över tentor och API-nyckeln | I webbläsaren |

Mappfunktionen kräver Chrome eller Edge på dator. I andra webbläsare (Safari, Firefox, telefon) sparas tentorna i webbläsaren i stället och man laddar upp filerna.

Materialet skickas till OpenRouter och den valda modellens leverantör när frågor skapas och rättas. Använd inte material du inte får dela med en AI-tjänst. Vissa gratismodeller kan använda det som skickas för att träna modeller – läs villkoren för modellen på OpenRouter.

## Teknik

En enda statisk HTML-fil utan byggsteg. Bibliotek laddas från cdnjs vid behov: pdf.js (PDF), mammoth (Word) och JSZip (PowerPoint). AI-anrop går direkt från webbläsaren till OpenRouters API.
