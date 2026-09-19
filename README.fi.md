[English](./README.md) | **Suomi**

# Mikko Tarkiainen

**AI-järjestelmäinsinööri** · Deterministiset päätösjärjestelmät · Tuotantoluotettavuus

Suomessa · Avoin freelance-toimeksiannoille, etärooleille ja ohjelmistokumppanuuksille

Kielimallit tulkitsevat ja kommunikoivat, mutta deterministinen ohjelmisto hallitsee päätöksiä, käyttöoikeuksia ja eskalointia. Järjestelmät ja referenssitoteutukset rakennetaan testattaviksi ja auditoitaviksi, ja niiden toimintarajat kuvataan selkeästi.

## Aloita tästä

- **[DDN Reference](https://github.com/mikko-lab/ddn-reference)** — todennettava deterministinen päätösverkko kvorumivalidoinnilla ja allekirjoitetuilla kuiteilla
- **[ACS Guardrail Demo](https://github.com/mikko-lab/acs-guardrail-demo)** — todennetut agentin ajonaikaiset kontrollit, autentikoidut hyväksynnät, replay-suojaus, execution permitit ja hallittu tool-result-polku
- **[Kopilotti Sales](https://app.kopilotti.online/en/)** — deterministinen käytettyjen autojen hintaneuvottelu, live-demo
- **[Ruuhkavahti](https://github.com/mikko-lab/ruuhkavahti)** — Kafka-mittakaavan suojauskerros, kuormitustestattu 8 000 viestillä sekunnissa
- **[Yhteydenotto](#yhteystiedot)** — avoin freelance-toimeksiannoille, etärooleille ja ohjelmistokumppanuuksille

## Nykyinen painopiste

- **Agenttijärjestelmät** — jäsennelty orkestrointi, työkalujen käyttö ja skeemalla validoidut vastaukset
- **Deterministiset päätösjärjestelmät** — eksplisiittiset PASS-, ESCALATE-, BLOCK-, ACCEPT-, COUNTER- ja REJECT-tulokset, jotka päätetään kielimallin ulkopuolella
- **AI-järjestelmien arviointi ja testaus** — API-, integraatio-, regressio-, black box- ja tietoturvatestaus rajatun AI-käyttäytymisen todentamiseen
- **Tuotantoluotettavuus ja tekoälyjärjestelmien tietoturva** — todennettava suoritus, allekirjoitetut kuitit, prompt injection -suojaus ja SSRF-suojaus
- **Saavutettavuus arkkitehtuurissa** — WCAG 2.2 AA, semanttiset käyttöliittymät ja ruudunlukijatestaus

## Valitut työt

### DDN Reference — todennettava deterministinen päätösverkko

Avoimen lähdekoodin referenssitoteutus itsenäisesti todennettaville automatisoiduille päätöksille. Versioidut liiketoimintasäännöt suoritetaan kolmessa eristetyssä validaattoriprosessissa, jotka ajavat samaa WebAssembly-käytäntöpakettia; päätös hyväksytään vain 2/3-kvorumilla. Hyväksytyt päätökset saavat kryptografisesti allekirjoitetut kuitit, jotka voidaan tarkistaa itsenäisesti, koota Merkle-puuhun ja ankkuroida EVM-yhteensopivaan älysopimukseen.

Tämä on referenssitoteutus, ei väite aktiivisesta julkisesta tuotantokäytöstä.

`Rust · WebAssembly · TypeScript · Solidity · Ed25519 · Merkle trees`

→ [Repository](https://github.com/mikko-lab/ddn-reference)

### ACS Guardrail Demo — todennetut agentin ajonaikaiset kontrollit

Julkinen referenssitoteutus valituista ACS v0.1.0 -kontrollimalleista rajattuun agentin työkalusuoritukseen. Se yhdistää kanonisesti HMAC-allekirjoitetut request- ja result-rajat, replay-suojauksen, kryptografisesti todennetut ihmishyväksynnät, kertakäyttöiset execution permitit, session/request/tool-korrelaation ja suorituksen jälkeisen output governance -portin.

v0.1.0-julkaisu käytiin defensive review -kierroksen läpi: kaikki löydetyt High-, Medium- ja Low-tason havainnot käsiteltiin ja regressiotestattiin. Julkaisu sisältää 174 läpäisevää testiä sekä mutation-todisteet keskeisille runtime-kontrolleille. Toteutus demonstroi valittuja ACS-malleja eikä väitä ACS-Core-conformanssia.

`TypeScript · Node.js · ACS v0.1.0 · HMAC-SHA256 · Ed25519 · AJV · JCS · Jest`

→ [Repository](https://github.com/mikko-lab/acs-guardrail-demo)

### Kopilotti Sales — deterministinen käytettyjen autojen hintaneuvottelu

Asiakasrajapintainen myyntikanava käytettyjen ajoneuvojen hintaneuvotteluun. Kielimalli hoitaa keskustelun, mutta ei koskaan päätä hintaa — jälleenmyyjän määrittämät liiketoimintasäännöt ohjaavat hyväksynnän, vastatarjoukset, hylkäyksen ja eskaloinnin, ja taustajärjestelmä valvoo erikseen ajoneuvon varausta, organisaatio- ja asiakaskohtaista omistajuutta, sopimuksen etenemistä sekä maksutilan oikeuksia.

Hinnan hyväksynnän jälkeen referenssitoteutus voi havainnollistaa konseptisopimusta ja maksutilan seurantaa. Asiakkaat eivät voi vahvistaa maksuja, eikä Kopilotti vastaanota, säilytä tai siirrä varoja. Julkisessa demossa ei ole maksettavia pankkitietoja, eikä täysi invoice-to-PAID-polku ole aktiivinen julkisessa tuotantoliikenteessä; DDN-integraatiorajapinta on olemassa, mutta ei aktiivinen siellä.

`Node.js · Express · PostgreSQL · JavaScript · Claude API · Playwright`

→ [Repository](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live demo](https://app.kopilotti.online/en/)

### Ruuhkavahti — Kafka-mittakaavan suojaukset kuormassa

Deterministinen PASS / ESCALATE / BLOCK -kerros, joka toimii skaalautuvassa Kafka-kuluttajaryhmässä; kuormitustestattu simuloidulla live-TV-liikennepiikillä, 8 000 viestiä sekunnissa.

Kojelauta tekee näkyviksi todellisen kuluttajaviiveen, duplikaattien käsittelyn ja Kafka-kuluttajaryhmän uudelleentasapainotukset 3D-visualisoinnin, liikettä vähentävän 2D-näkymän, semanttisen HTML-taulukon ja saavutettavien reaaliaikaisten tilapäivitysten avulla.

`Python · TypeScript · Apache Kafka · Docker Compose · axe-core`

→ [Repository](https://github.com/mikko-lab/ruuhkavahti)

### A11Y Lead Engine — automatisoitu saavutettavuusauditointiputki

TypeScript-pohjainen saavutettavuusauditointiputki, joka löytää suomalaisia yrityssivustoja, ajaa WCAG-auditointeja, rikastaa tuloksia yritysrekisterin tiedoilla ja tuottaa jäsenneltyä yhteydenottomateriaalia.

Yhdistää Playwright- ja axe-core-skannauksen jonopohjaiseen käsittelyyn ja Claude-avusteisiin yhteenvetoihin; infrastruktuuri sisältää Redis-autentikoinnin, API-välikerroksen, SSRF- ja DNS-rebinding-suojauksen, automatisoidut testit ja GitHub Actions -CI:n.

`TypeScript · Node.js · Playwright · axe-core · Redis · BullMQ · Claude API`

→ [Repository](https://github.com/mikko-lab/a11y-lead-engine)

## Avoimen lähdekoodin kontribuutiot

- **[567-labs/instructor](https://github.com/567-labs/instructor)** — jäljitin kutsujan omistaman viestilistan mutaatiovirheen useisiin provider-handlereihin; PR:issä #2418 ja #2419 ehdotetut korjaukset yhdistettiin maintainerin mergattuun PR:ään #2434 alkuperäisten kontribuoijien tekijyys säilyttäen
- **[langchain-ai/langgraph](https://github.com/langchain-ai/langgraph/issues/8314)** — tilakanavien referenssitransparenssin juurisyyanalyysi ja 12 kommentin tekninen keskustelu
- **[Aiven-Open/karapace](https://github.com/Aiven-Open/karapace/issues/1329)** — raportoitu RecursionError itseensä viittaavan JSON Scheman yhteensopivuustarkistuksessa sekä vian jäljitys schema registryn kirjoituspolun läpi

## Muut työt

<details>
<summary>Näytä muut projektit</summary>

- **[Kopilotti WebMCP](https://github.com/mikko-lab/kopilotti-webmcp)** — avoimen lähdekoodin selainagenttihaasteen toteutus, jossa työkalut on rajattu skeemoilla, tila näkyy käyttäjälle ja hyväksyntä tehdään sivun omalla ihmisen vahvistuksella
- **[osCommerce Checkout Refactor](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization)** — tekoälyavusteinen vanhan checkout-virtauksen modernisointi; epäonnistunut testi paljasti käänteisen varastosäännön, tuloksena 34 läpäisevää testiä ja säilytetty ajonaikainen käyttäytyminen
- **[Prompt Injection Gate](https://github.com/mikko-lab/prompt-injection-gate)** — deterministinen raja, joka eristää epäluotettavan työkaluvasteen, tuottaa PASS / ESCALATE / BLOCK -tuloksia ja tallentaa hash-ketjutetun audit-jäljen
- **[refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess)** — riippuvuudeton Python-suojaus ALV-luokitteluun, deterministisellä eskaloinnilla ja prompt injection -regressiotesteillä
- **[claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard)** — sama suojausperiaate toteutettuna Claude Coden runtime-primitiiveillä
- **[Provenanssi](https://github.com/mikko-lab/provenanssi)** — avointa tutkimusta, joka erottaa mitatun kuvatiedon mallin generoimasta rekonstruktiosta
- **[Karikko](https://github.com/mikko-lab/karikko)** — offline-first-periaatteella toimiva merivaarojen ilmoituspalvelu Suomen vesille, sisältäen [backendin](https://github.com/mikko-lab/karikko-api) ja [live-demon](https://demo.nordicmarinedata.com)

</details>

## Teknologiat

TypeScript · JavaScript · Node.js · Python · Rust · Solidity · PostgreSQL · Redis · Apache Kafka · Docker · WebAssembly · Claude API · LangGraph · Playwright · Vitest · GitHub Actions

## Suunnitteluperiaate

LLM-sovellukset muuttuvat luotettaviksi, kun todennäköisyyspohjainen päättely erotetaan auktoritatiivisesta päätöksenteosta. Kielimalleja käytetään siellä, missä tulkinta, synteesi ja vuorovaikutus tuovat arvoa; deterministinen ohjelmisto vastaa aina, kun kyse on oikeellisuudesta, käyttöoikeuksista, rahasta, tietoturvasta tai käyttäjän turvallisuudesta. Tämä raja suunnitellaan arkkitehtuuriin alusta asti — sitä ei lisätä jälkikäteen, kun malli saavuttaa tuotannon.

## Yhteystiedot

Avoinna ohjelmistokumppanuuksille, arkkitehtuurikonsultoinnille, valikoiduille freelance-projekteille ja etätöille.

**[Ota yhteyttä →](mailto:hello@kopilotti.online?subject=Software%20partnership%20inquiry)**
