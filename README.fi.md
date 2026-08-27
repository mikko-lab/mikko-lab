[English](./README.md) | **Suomi**

# Mikko Tarkiainen

**AI-järjestelmäinsinööri** · Deterministiset päätösjärjestelmät · Tuotantoluotettavuus

Suomessa · Avoin freelance-toimeksiannoille, etärooleille ja ohjelmistokumppanuuksille

Kielimallit tulkitsevat ja kommunikoivat, mutta deterministinen ohjelmisto hallitsee päätöksiä, käyttöoikeuksia ja eskalointia. Järjestelmät ja referenssitoteutukset rakennetaan testattaviksi ja auditoitaviksi, ja niiden toimintarajat kuvataan selkeästi.

## Aloita tästä

- **[DDN Reference](https://github.com/mikko-lab/ddn-reference)** — todennettava deterministinen päätösverkko kvorumivalidoinnilla ja allekirjoitetuilla kuiteilla
- **[Kopilotti Sales](https://app.kopilotti.online/en/)** — deterministinen käytettyjen autojen hintaneuvottelu, live-demo
- **[Ruuhkavahti](https://github.com/mikko-lab/ruuhkavahti)** — Kafka-mittakaavan suojauskerros, kuormitustestattu 8 000 viestillä sekunnissa
- **[Yhteydenotto](#yhteystiedot)** — avoin freelance-toimeksiannoille, etärooleille ja ohjelmistokumppanuuksille

## Nykyinen painopiste

- **Agenttijärjestelmät** — jäsennelty orkestrointi, työkalujen käyttö ja skeemalla validoidut vastaukset
- **Deterministiset päätösjärjestelmät** — eksplisiittiset PASS-, ESCALATE-, BLOCK-, ACCEPT-, COUNTER- ja REJECT-tulokset, jotka päätetään kielimallin ulkopuolella
- **Tuotantoluotettavuus ja tekoälyjärjestelmien tietoturva** — todennettava suoritus, allekirjoitetut kuitit, prompt injection -suojaus ja SSRF-suojaus
- **Saavutettavuus arkkitehtuurissa** — WCAG 2.2 AA, semanttiset käyttöliittymät ja ruudunlukijatestaus

## Valitut työt

### DDN Reference — todennettava deterministinen päätösverkko

Avoimen lähdekoodin referenssitoteutus itsenäisesti todennettaville automatisoiduille päätöksille. Versioidut liiketoimintasäännöt suoritetaan kolmessa eristetyssä validaattoriprosessissa, jotka ajavat samaa WebAssembly-käytäntöpakettia; päätös hyväksytään vain 2/3-kvorumilla. Hyväksytyt päätökset saavat kryptografisesti allekirjoitetut kuitit, jotka voidaan tarkistaa itsenäisesti, koota Merkle-puuhun ja ankkuroida EVM-yhteensopivaan älysopimukseen.

Tämä on referenssitoteutus, ei väite aktiivisesta julkisesta tuotantokäytöstä.

`Rust · WebAssembly · TypeScript · Solidity · Ed25519 · Merkle trees`

→ [Repository](https://github.com/mikko-lab/ddn-reference)

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

## Muut työt

<details>
<summary>Näytä muut projektit</summary>

- **[osCommerce Checkout Refactor](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization)** — tekoälyavusteinen vanhan checkout-virtauksen modernisointi; epäonnistunut testi paljasti käänteisen varastosäännön, tuloksena 34 läpäisevää testiä ja säilytetty ajonaikainen käyttäytyminen
- **[Prompt Injection Gate](https://github.com/mikko-lab/prompt-injection-gate)** — deterministinen raja, joka eristää epäluotettavan työkaluvasteen, tuottaa PASS / ESCALATE / BLOCK -tuloksia ja tallentaa hash-ketjutetun audit-jäljen
- **[refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess)** — riippuvuudeton Python-suojaus ALV-luokitteluun, deterministisellä eskaloinnilla ja prompt injection -regressiotesteillä
- **[claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard)** — sama suojausperiaate toteutettuna Claude Coden runtime-primitiiveillä
- **[Provenanssi](https://github.com/mikko-lab/provenanssi)** — avointa tutkimusta, joka erottaa mitatun kuvatiedon mallin generoimasta rekonstruktiosta
- **[Karikko](https://github.com/mikko-lab/karikko)** — offline-first-periaatteella toimiva merivaarojen ilmoituspalvelu Suomen vesille, sisältäen [backendin](https://github.com/mikko-lab/karikko-api) ja [live-demon](https://demo.nordicmarinedata.com)

</details>

## Teknologiat

TypeScript · JavaScript · Node.js · Python · Rust · Solidity · PostgreSQL · Redis · Apache Kafka · Docker · WebAssembly · Claude API

## Suunnitteluperiaate

LLM-sovellukset muuttuvat luotettaviksi, kun todennäköisyyspohjainen päättely erotetaan auktoritatiivisesta päätöksenteosta. Kielimalleja käytetään siellä, missä tulkinta, synteesi ja vuorovaikutus tuovat arvoa; deterministinen ohjelmisto vastaa aina, kun kyse on oikeellisuudesta, käyttöoikeuksista, rahasta, tietoturvasta tai käyttäjän turvallisuudesta. Tämä raja suunnitellaan arkkitehtuuriin alusta asti — sitä ei lisätä jälkikäteen, kun malli saavuttaa tuotannon.

## Yhteystiedot

Avoinna ohjelmistokumppanuuksille, arkkitehtuurikonsultoinnille, valikoiduille freelance-projekteille ja etätöille.

**[Ota yhteyttä →](mailto:hello@kopilotti.online?subject=Software%20partnership%20inquiry)**
