[English](./README.md) | **Suomi**

# Mikko Tarkiainen

**AI-järjestelmäinsinööri · Agenttien ajonaikaiset kontrollit, arviointi ja luotettavuus · Deterministiset päätösjärjestelmät**

Suomessa · Avoin freelance-toimeksiannoille, etärooleille ja ohjelmistokumppanuuksille

Suunnittelen ja rakennan tekoälyjärjestelmiä, joilla on selkeät toimintarajat. Kielimallit tulkitsevat, keskustelevat ja ehdottavat; ohjelmisto valvoo käyttöoikeuksia, liiketoimintasääntöjä ja tilasiirtymiä.

Kaksi vuosikymmentä yrittäjänä autoalalla muovasi työtapani: ota vastuu ongelmasta, tee päätöksiä epävarmuudessa ja vastaa lopputuloksesta.

Nykyinen työni keskittyy kolmeen erilliseen kysymykseen:

- **Kontrollit:** Mitä agentti saa tehdä?
- **Arviointi:** Toimivatko toteutetut kontrollit määrittelyn mukaisesti myös niiden rajoja koettelevissa tilanteissa?
- **Näyttö:** Mitä allekirjoitetut havainnot voivat todentaa suorituksesta ja mikä jää epävarmaksi?

## Aloita tästä: kontrollit, arviointi ja näyttö

Nämä kolme julkista referenssitoteutusta käsittelevät eri vastuita. Niiden suhteet ja luottamusrajat kuvataan yhteisessä dokumentissa: [Control, Evaluation & Evidence Architecture](https://github.com/mikko-lab/agent-control-evals/blob/9a624cf0d9972dea65e37713729a455b2d365f51/docs/architecture/control-evaluation-evidence.md).

### ACS Guardrail Demo — Agenttien toimivalta ja ajonaikaiset kontrollit

Deterministisiä kontrolleja agenttien työkalukutsuille: allekirjoitetut ja rajatut toimintavaltuudet, työkalukohtainen ihmisen hyväksyntä, tenant- ja valtuusketjukohtainen valtuuksien peruminen sekä valinnainen hyväksynnän ja kertakäyttöisen suoritusluvan elinkaari.

Ajonaikainen järjestelmä ottaa pyynnöstä muuttumattoman kopion, jotta suoritettava pyyntö vastaa tarkistettua pyyntöä. Yhteistyöhön perustuva keskeyttäminen, tilamuutosten toteutusta rajaavat tarkistukset ja tulosten luovutusrajat rajoittavat hallittua suorituspolkua. Hash-ketjutetun audit-jäljen eheys voidaan tarkistaa erikseen luotettua ketjun päätiivistettä vasten.

**Rajaus:** keskeyttäminen edellyttää työkalun yhteistyötä, eikä hallitun tilamuutosrajan ulkopuolisia vaikutuksia estetä. Valtuuksien perumisen tila on paikallinen ja muistissa. Kyseessä on referenssitoteutus, ei väite täydestä ACS-vaatimustenmukaisuudesta tai tuotantovalmiudesta.

[Lähdekoodi](https://github.com/mikko-lab/acs-guardrail-demo)

### Agent Control Evals — Agenttikontrollien deterministinen arviointi

Toistettavia arviointijärjestelmiä, jotka perustuvat täsmällisiin määrittelyihin, deterministisiin odotettuihin tuloksiin, rajoja koetteleviin skenaarioihin ja mutaatiotestaukseen.

Työ erottaa ilmoitetut sääntöpäätökset havaituista vaikutuksista. Arvioinneissa yksilöidään testattu järjestelmäversio, testiaineisto, ilmoitettu kyvykkyysprofiili ja kattavuusaukot. Ajonaikaisten kontrollien, valtuuksien perumisen ja autoalan agenttien arvioinneilla on omat oletuksensa ja raportointirajansa.

**Rajaus:** tulokset koskevat arvioituja versioita, skenaarioita ja havaintomekanismeja. Synteettinen arviointijärjestelmän testaus erotetaan ulkoisen järjestelmän arvioinnista. Rajatun profiilin läpäisy ei osoita koko arviointisopimuksen täyttymistä, yleistä turvallisuutta tai tuotantovalmiutta.

[Lähdekoodi](https://github.com/mikko-lab/agent-control-evals)

### Execution Evidence Demo — Varmennettavat suorituskuitit ja historia

TypeScript-referenssikirjasto Ed25519-allekirjoitetuille suorituskuiteille ja linkitetyille elinkaarihavainnoille. Kuitit sitovat toimijan ja toiminnon toimitettujen alku-, loppu- ja tuloshavaintojen tiivisteisiin.

Elinkaarinäyttö yhdistää operaatiot, suoritusyritykset ja kuitit säilyttäen epävarmuuden ja ristiriitaiset tulokset. Allekirjoitusten varmennus, historian arviointi ja seuraavan toiminnon valtuutus pysyvät erillisinä vastuina.

**Rajaus:** allekirjoitukset varmentavat näytön määritettyjen luottamussääntöjen puitteissa; ne eivät itsenäisesti todista ulkoisia tapahtumia. Kirjasto ei suorita operaatioita, valtuuta uusintayrityksiä eikä takaa täydellistä historiaa, muuttumatonta tallennusta tai täsmälleen yhtä suoritusta.

[Lähdekoodi](https://github.com/mikko-lab/execution-evidence-demo)

## Soveltavat järjestelmät

### Kopilotti Sales — Myyjäliikkeen hallitsema digitaalinen myynti

Tekoälyavusteista käytettyjen autojen myyntiä myyjäliikkeen määrittämissä kaupallisissa rajoissa. Kielimalli hoitaa keskustelun; deterministiset palvelinpuolen säännöt ohjaavat hinnoittelupäätöksiä ja myyntipolun tilasiirtymiä.

Autokohtainen Magic Link tarjoaa asiakkaalle aloituspisteen, ja myyjäliike määrittää kaupalliset säännöt Adminissa. Erillinen Evaluation & Safety -arviointikerros testaa havaittavaa API-käyttäytymistä paikallista Sales-järjestelmää vasten eristetyssä ympäristössä.

**Rajaus:** järjestelmä on kehitysvaiheessa. Ulkoiset integraatiot ja pilottivalmius arvioidaan erikseen. Kopilotti ei vastaanota, säilytä tai välitä asiakkaan maksuja.

[Projektikuvaus](https://github.com/mikko-lab/kopilotti-sales-demo) · [Live-demo](https://app.kopilotti.online/en/)

### DDN Reference — Varmennettavat deterministiset päätökset

Versioidut liiketoimintasäännöt suoritetaan WebAssemblyna kolmessa eristetyssä validaattoriprosessissa samalla koneella ja saman operaattorin hallinnassa. Päätös hyväksytään, kun vähintään kaksi konfiguroitua validaattoria tuottaa yhtenevät allekirjoitetut attestoinnit.

Päätöskuiteista voidaan tarkistaa allekirjoitukset, pyyntöön sidonnat, tiivisteet ja Merkle-todisteet. Toteutus demonstroi myös EVM-ankkurointia paikallisella Anvil-ketjulla.

**Rajaus:** kyseessä ei ole riippumattomien validaattorien verkko eikä aktiivinen tuotantointegraatio. Kuittivarmennus ei tavallisesti suorita sääntöä uudelleen eikä osoita, onko liiketoimintasääntö itsessään oikea tai reilu.

[Lähdekoodi](https://github.com/mikko-lab/ddn-reference)

### Ruuhkavahti — Kafka-kontrollit kuormituksessa

Deterministinen PASS / ESCALATE / BLOCK -käsittelyputki, jota on testattu paikallisesti simuloidulla 8 000 viestin sekuntipiikillä.

Toteutus yhdistää kuluttajaviiveen seurannan, duplikaattien käsittelyn, erillisen kuluttajapalvelun, allekirjoitetun palveluiden välisen autentikoinnin ja hajautetun jäljityksen. Kojelauta sisältää saavutettavat semanttiset näkymät ja vähennetyn liikkeen tuen.

**Rajaus:** julkaistut mittaukset kuvaavat yksilöityjä paikallisia kokeita, eivät tuotannon suorituskyky- tai saatavuustakuuta.

[Lähdekoodi](https://github.com/mikko-lab/ruuhkavahti)

## Muut työt

- [A11Y Lead Engine](https://github.com/mikko-lab/a11y-lead-engine) — automatisoidut saavutettavuustarkistukset, yritystietojen rikastus ja jäsennellyt yhteydenottoprosessit.
- [Prompt Injection Gate](https://github.com/mikko-lab/prompt-injection-gate) — kokeellinen toteutus, joka erottaa rakenteellisen työkaluvasteen karanteenin parhaan yrityksen kuviotunnistuksesta.
- [refuse-dont-guess](https://github.com/mikko-lab/refuse-dont-guess) — deterministinen ALV-luokittelu ja eskalointi sekä prompt injection -regressiotestit.
- [claude-code-invoice-guard](https://github.com/mikko-lab/claude-code-invoice-guard) — sama kontrolliperiaate toteutettuna Claude Coden ajonaikaisilla mekanismeilla.
- [Kopilotti WebMCP](https://github.com/mikko-lab/kopilotti-webmcp) — selainagenttidemo, jossa on rajatut työkalut, näkyvä tila ja ihmisen hyväksyntäraja.
- [osCommerce Checkout Refactor](https://github.com/mikko-lab/sap-checkout-refactor/tree/poc/checkout-modernization) — tekoälyavusteinen vanhan koodin uudistaminen, jossa liiketoimintasäännöt analysoidaan ja käyttäytyminen säilytetään testeillä.
- [Provenanssi](https://github.com/mikko-lab/provenanssi) — avointa tutkimusta mitatun kuvatiedon erottamisesta mallin generoimasta rekonstruktiosta.
- [Karikko](https://github.com/mikko-lab/karikko) — paikkatietoon perustuva vaarailmoituspalvelu Suomen vesille sekä erillinen [backend](https://github.com/mikko-lab/karikko-api).

## Avoimen lähdekoodin kontribuutiot

- [567-labs/instructor](https://github.com/567-labs/instructor/pull/2434) — kutsujan viestidatan mutaation jäljitys eri providereissa; ehdotetut korjaukset yhdistettiin ylläpitäjän hyväksyttyyn PR:ään alkuperäinen tekijyys säilyttäen.
- [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph/issues/8314) — tilakanavien referenssitransparenssin juurisyyanalyysi.
- [Aiven-Open/karapace](https://github.com/Aiven-Open/karapace/issues/1329) — itseensä viittaavan JSON Scheman yhteensopivuustarkistuksen RecursionError-virheen raportointi ja jäljitys.

## Teknologiat

TypeScript · JavaScript · Node.js · Python · Rust · PostgreSQL · Redis · Kafka · Docker · WebAssembly · Solidity · Playwright · Jest · Vitest · GitHub Actions

## Suunnitteluperiaate

**Flag, don’t hide.**

Järjestelmän tulee kertoa, mitä se päätti, mitä se havaitsi, mitä sen näyttö voi todentaa ja missä sen rajat kulkevat. Toimintavaltuus, arviointitulos ja suoritusnäyttö eivät korvaa toisiaan.

## Yhteystiedot

Avoin ohjelmistokumppanuuksille, arkkitehtuurikonsultoinnille, valikoiduille freelance-toimeksiannoille ja etärooleille.

[Ota yhteyttä →](mailto:hello@kopilotti.online?subject=Software%20partnership%20inquiry)
