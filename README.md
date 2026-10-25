# Spisa

**Laget av:** Aurora Guttormsen Fredly og Frida Knivsflå Strand

Spisa er en nettside der studenter kan se dagens meny i kantinene og hvor mange av hver vare som er igjen. Appen er inspirert av kantinene i bygg P35, P32 og P48 ved OsloMet, men er en prototype med oppdiktede data og er ikke en offisiell tjeneste.

**Demo:** https://aurorafredly.github.io/Spisa/

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

## Hvordan vi brukte AI

## Hvordan vi brukte AI

Vi brukte **Claude** som kodeassistent gjennom hele oppgaven, fra idé til publisering. Vi har ikke skrevet koden selv. Vår jobb var å bestemme hva som skulle lages, teste, finne feil og få AI-en til å rette dem.

### Slik jobbet vi

1. **Idéfase:** Vi skrev ned egne idéer til forbedring av kjente apper (blant annet Letterboxd, Prime Video, Temu, Outlook og Goodreads). Vi ba AI-en om flere forslag som passet oppgaveteksten, og fikk en liste sortert etter tilnærming (hverdagsproblem, hjelpe en organisasjon, forbedre en kjent app).
2. **Første prototype:** Vi valgte en Spotify-inspirert spilleliste-app og lot AI-en lage en første versjon med spillelister, dra og slipp-sortering og «mix» av to lister. Vi vurderte den og bestemte oss for å gå for en annen idé.
3. **Vår egen idé:** Vi kom selv på at kantinen på OsloMet kunne hatt en app som viser dagens meny og hvor mange som er igjen av varer som Monster. Vi beskrev idéen til AI-en, og fikk første versjon av Spisa med meny per dag, lagerstatus og en personalvisning.
4. **Utvidelse:** Vi ba om å legge til byggene P35, P32 og P48, som hver har egen meny og eget lager.
5. **Testing og retting:** AI-en kjørte automatiske tester i en nettleser og fant to feil som den rettet. Etterpå testet vi selv siden på GitHub Pages og fant en tredje feil (se «Testing og forbedringer» under), som AI-en også rettet.
6. **Publisering:** AI-en forklarte steg for steg hvordan vi la koden på GitHub og slo på GitHub Pages. Da vi fikk problemer (feil filnavn), sendte vi skjermbilder, og AI-en hjalp oss å finne årsaken.

### Hva AI-en gjorde, og hva vi gjorde

| AI-en | Vi |
|---|---|
| Skrev koden (HTML, CSS og JavaScript) | Valgte idé og hva appen skulle gjøre |
| Foreslo ideer og lagde utkast til README | Valgte byggene og bestemte hva som skulle med |
| Kjørte automatiske tester og rettet feil | Testet selv, fant feil og beskrev dem |
| Forklarte hvordan vi publiserer | Lastet opp, rettet filnavnet og publiserte |

### Hva vi lærte

- AI-en lager ikke alltid kode som fungerer perfekt. Vi fant feil som både den og vi måtte teste oss fram til.
- Det hjelper å beskrive nøyaktig hva vi ser, og å sende skjermbilde, når noe ikke fungerer.
- Små ting som et feil filnavn (`index(1).html` i stedet for `index.html`) kan stoppe hele siden fra å virke.
- AI-en er et verktøy, og vi må selv vurdere om resultatet er bra nok og passer til det vi ville lage.

### Prompt-logg

- Vi spurte: «Har du noen andre ideer til hva jeg kan lage oppgaven om? Som passer oppgaveteksten?» (brainstorming av idé)
- Vi spurte: «Kan du lage en ny applikasjon. Kantinen på OsloMet kunne hatt en app/nettside hvor det står meny i kantinen for hver dag, hva de selger, hvor mange som er igjen av f.eks. Monster» (vår egen idé, første versjon av Spisa)
- Vi ba om: «Du må legge til ulike bygg: bygg P35, bygg P32 og P48. Test applikasjonen» (utvidelse og testing)
- Vi oppdaget under egen testing: «Det går ikke å trykke på personalvisning» (feilen førte til en forbedring)
- Vi spurte: «Forklar meg enkelt hvordan jeg tester siden» (hjelp til testing)

Automatiske tester i nettleser (Playwright) som AI-en kjørte:

| Hva som ble testet | Resultat | Endring |
|---|---|---|
| Bytte dag, kostfiltre og kategorier | Fungerte | Ingen |
| +1, −1, fyll opp og utsolgt i personalvisning | Fungerte | Ingen |
| Når «Skjul utsolgte» var på, forsvant en vare som personalet satte til utsolgt, og de kunne ikke fylle den opp igjen | Feil | Personalvisningen viser nå alltid alle varer |
| Datoer på fanene i helgen viste forrige uke | Feil | Viser nå neste uke |
| Hvert bygg har eget lager, og oppdatering i ett bygg påvirker ikke de andre | Fungerte | Ingen |
| Lagring etter at siden lastes på nytt, og ugyldig lagring | Fungerte | Ingen |

### Våre egne tester

Vi testet siden selv på pc [og mobil] etter at den var publisert på GitHub Pages.

| Hva vi testet | Resultat | Hva vi endret |
|---|---|---|
| Åpnet GitHub Pages-lenken første gang | Vi så bare README-teksten, og ingenting kunne trykkes på. Filen het `index(1).html` i stedet for `index.html` | Vi slettet den gamle filen og lastet opp riktig fil, og da fungerte siden |
| Trykket på «Personalvisning» | Det virket som om ingenting skjedde, fordi knappene kom langt nede på siden | AI-en rettet det: siden scroller nå ned til lageret, viser en melding, og knappen endrer tekst |
| Trykket på dagene og byggene (P35, P32, P48) | [Fungerte / skriv det dere så] | [Ingen / skriv hva dere endret] |
| Brukte −1 på Monster Energy i personalvisning | [Tallet gikk ned / skriv det dere så] | [Ingen] |

Dette lærte vi: når noe ikke fungerer, må vi beskrive nøyaktig hva vi ser (eller sende skjermbilde) for at AI-en skal kunne hjelpe oss å finne feilen.

## Kjøre lokalt

Last ned `index.html` og åpne den i nettleseren.
