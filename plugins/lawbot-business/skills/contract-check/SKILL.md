---
name: contract-check
description: Analyseert een aangeleverd contract of algemene voorwaarden voor de MKB-ondernemer — risico's, rode vlaggen en onderhandelpunten in gewone taal. MOET actief worden bij /lawbot-business:contract, een geüpload of geplakt contract/AV, "check dit contract", "kan ik dit tekenen", "wat staat hier eigenlijk", "zijn mijn algemene voorwaarden goed", "is deze clausule normaal".
---

# Contract- & voorwaardencheck

Doel: een ondernemer die een contract of algemene voorwaarden voorgelegd krijgt (of zijn
eigen AV wil laten nakijken) begrijpelijk laten zien **wat er staat, wat het risico is, en
waar hij op moet letten** — zónder dat hij eerst een advocaat hoeft te betalen om het te
begrijpen. Werk in de adaptieve toon van `lawbot-business`.

## Werkwijze

0. **Roep eerst de `werkstroom`-tool aan** (naam: `contract-check`, of `av-check` voor
   algemene voorwaarden, of `onderhandeling` voor het tegenvoorstel) — die levert de
   actuele checklist en diepte-instructies van de server. De stappen hieronder blijven
   de vaste kern.

1. **Lees het volledige document** dat de ondernemer aanlevert (upload, plak of `url_ophalen`
   voor een link/PDF). Vat éérst in twee zinnen samen wat voor document het is en wat het
   in de kern regelt — zodat hij weet dat je het goed hebt.
2. **Loop het gestructureerd na** (zie checklist). Signaleer per punt: *wat staat er*,
   *is dit normaal of afwijkend*, en *wat betekent het risico voor jou*.
3. **Markeer met kleuren** voor snel overzicht:
   - 🟢 gebruikelijk / geen bezwaar
   - 🟠 let op / onderhandelpunt
   - 🔴 risicovol / laat hier een advocaat naar kijken
4. **Onderbouw waar het telt** met de wet (verifieer via de tools; artikelen alleen uit
   tool-output + `bron_url`) — bijvoorbeeld bij bepalingen die wettelijk begrensd of
   vernietigbaar zijn.
5. **Geef een helder eindoordeel**: kun je dit zo tekenen (🟢), zijn er punten om eerst
   over te onderhandelen (🟠), of hoort hier een advocaat naar te kijken (🔴)?

## Checklist (kies wat relevant is voor het documenttype)

- **Partijen en looptijd** — wie, hoe lang, stilzwijgende verlenging?
- **Verplichtingen over en weer** — wat moet je leveren/betalen, wat de ander?
- **Prijs, indexering, meerwerk** — kan de prijs eenzijdig omhoog?
- **Betaaltermijnen en rente** — redelijk? incassokosten geregeld?
- **Opzegging en ontbinding** — opzegtermijn, boetes, tussentijds eruit kunnen?
- **Aansprakelijkheid** — uitsluitingen en beperkingen; is jouw risico onbeperkt?
- **Boetebeding** — hoogte, cumulatie; onredelijk hoog?
- **Garanties en klachttermijnen** — hoe lang kun je klagen?
- **Toepasselijk recht en geschillen** — Nederlands recht? welke rechter/arbitrage?
- **Algemene voorwaarden** — van welke partij gelden ze, en zijn ze wel op tijd ter hand
  gesteld (informatieplicht)?
- **Overig** — geheimhouding, concurrentiebeding, intellectueel eigendom, overmacht.

## Bij eigen algemene voorwaarden van de ondernemer

Als de ondernemer zíjn eigen AV wil verbeteren: check bovenstaande punten vanuit zíjn
belang, wijs op wat ontbreekt (bijv. eigendomsvoorbehoud, betaaltermijn, aansprakelijkheids-
beperking, klachttermijn) en op de **informatieplicht** (AV tijdig ter hand stellen, anders
vernietigbaar). Bied aan de zwakke punten concreet te herformuleren.

## Vangrails

- Je duidt en signaleert; je geeft **geen sluitend juridisch oordeel** dat een advocaat
  toekomt. Bij een groot belang, een ongebruikelijke constructie of een 🔴-punt: adviseer
  een advocaat en bied aan het als **dossier** klaar te zetten (skill `dossier`).
- Bij een contract dat onderdeel is van een lopend conflict/procedure: dat is 🔴 — verwijs
  door.

## Afsluiting

Sluit af met het eindoordeel, een korte lijst concrete actiepunten (wat te vragen/wijzigen),
en de standaarddisclaimer uit `lawbot-business`.
