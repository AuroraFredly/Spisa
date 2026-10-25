# Spisa

Spisa er en nettside der studenter kan se dagens meny i kantinene og hvor mange av hver vare som er igjen. Appen er inspirert av kantinene i bygg P35, P32 og P48 ved OsloMet, men er en prototype med oppdiktede data og er ikke en offisiell tjeneste.

**Demo:** [legg inn lenke her]

## Problemet

Man går ned til kantina og oppdager at favorittdrikken eller maten er utsolgt, eller at dagens rett ikke er den man hadde håpet på. Spisa lar deg sjekke menyen og lagerstatusen på forhånd, så du slipper turen for ingenting.

## Funksjoner

1. **Meny per dag og bygg:** faner for mandag til fredag, med pris, allergener og filter for vegetar, vegansk og glutenfri.
2. **Lagerstatus:** viser hvor mange som er igjen av for eksempel Monster Energy, med fargestolpe og status (På lager, Få igjen, Utsolgt). Filtrer på kategori, og skjul utsolgte varer.
3. **Flere bygg:** P35, P32 og P48 har hver sin meny, sine åpningstider og sitt lager.
4. **Personalvisning:** kantinepersonalet kan trykke −1, +1, «Fyll opp» eller «Utsolgt», og studentene ser oppdateringen.

## Teknologi

Ren HTML, CSS og JavaScript i én fil (`index.html`). Ingen bibliotek, server eller API-nøkler.

## Data og personvern

Menyer, priser, åpningstider og lagertall er oppdiktede eksempeldata. Appen samler ikke inn personopplysninger.

## Begrensninger

- Lagertallene lagres kun i den enkelte nettleseren (localStorage). En ekte løsning ville trengt en database, slik at alle ser de samme tallene.
- Personalvisningen har ingen innlogging, siden dette er en prototype.

## Hvordan jeg brukte AI

- Verktøy: Claude
- Prosess: brainstormet ideer, valgte kantine-idéen selv, lot AI lage første versjon, la til flere bygg, og testet.
- Prompt-logg: [legg inn 3-5 sentrale prompter, for eksempel idéen om kantineappen og ønsket om bygg P35, P32 og P48]

## Testing og forbedringer

Automatiske tester i nettleser (Playwright) som AI-en kjørte:

| Hva som ble testet | Resultat | Endring |
|---|---|---|
| Bytte dag, kostfiltre og kategorier | Fungerte | Ingen |
| +1, −1, fyll opp og utsolgt i personalvisning | Fungerte | Ingen |
| Når «Skjul utsolgte» var på, forsvant en vare som personalet satte til utsolgt, og de kunne ikke fylle den opp igjen | Feil | Personalvisningen viser nå alltid alle varer |
| Datoer på fanene i helgen viste forrige uke | Feil | Viser nå neste uke |
| Hvert bygg har eget lager, og oppdatering i ett bygg påvirker ikke de andre | Fungerte | Ingen |
| Lagring etter at siden lastes på nytt, og ugyldig lagring | Fungerte | Ingen |

Mine egne tester: [fyll inn hva du selv testet, på pc og mobil, og hva du fant]

## Kjøre lokalt

Last ned `index.html` og åpne den i nettleseren.
