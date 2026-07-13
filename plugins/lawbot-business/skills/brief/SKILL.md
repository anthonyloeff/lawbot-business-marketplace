---
name: brief
description: Stelt zakelijke juridische brieven op voor de MKB-ondernemer in gewone taal — aanmaning, sommatie/ingebrekestelling, en een reactie op een claim. MOET actief worden bij /lawbot-business:brief, "stuur een aanmaning", "maak een sommatie", "ze betalen niet, wat nu", "hoe reageer ik op deze claim", "ik wil een brief sturen naar".
---

# Brieven & sommaties

Voor de 🟢 (en soms 🟠) zaken waarin de ondernemer zelf een stap kan zetten. Werk in de
adaptieve toon van de kern-skill `lawbot-business` en houd de vangrails aan.

## Werkwijze

0. **Roep eerst de `werkstroom`-tool aan** (naam: `brief-aanmaning`, `brief-sommatie` of
   `brief-reactie-claim`, of `incasso` voor de hele ladder) — die levert het actuele
   sjabloon en de vangrails van de server. De stappen hieronder blijven de vaste kern.

1. **Bepaal het brieftype** en gebruik het bijbehorende template uit `templates/`:
   - `aanmaning.md` — vriendelijk-zakelijk betalingsverzoek (eerste stap bij een onbetaalde
     factuur).
   - `sommatie.md` — formele ingebrekestelling met termijn en aangekondigd rechtsgevolg
     (als de aanmaning niet werkte, of bij wanprestatie).
   - `reactie-claim.md` — een gestructureerde, feitelijke reactie op een claim of
     aansprakelijkstelling van de wederpartij.
2. **Vraag kort de ontbrekende gegevens**: afzender (bedrijf, contactpersoon), geadresseerde,
   waar het om gaat, bedrag/verplichting, relevante data, en de gewenste termijn.
3. **Onderbouw waar nodig met bronnen** (verifieer via de tools; artikelen alleen uit
   tool-output + `bron_url`). Een aanmaning hoeft niet juridisch dichtgetimmerd; een
   sommatie/ingebrekestelling wél zorgvuldig (juiste termijn, correcte rechtsgevolgen —
   bijv. verzuim en wettelijke handelsrente).
4. **Schrijf in gewone, nette zakentaal.** Geen onnodig jargon; wél juridisch correct waar
   het telt. Concreet, beleefd, zakelijk stevig.
5. **Export**: lever in Cowork als Word of PDF (docx-/pdf-skill) in de outputs-map; buiten
   Cowork nette markdown + melding dat export in Cowork kan.

## Vangrail — verplichte waarschuwing bij rechtsgevolg

Een sommatie/ingebrekestelling, opzegging of ontslagbrief heeft **rechtsgevolgen**. Herhaal
vóór oplevering expliciet:

> *Let op: dit is een formele brief met juridische gevolgen. Ik ben geen advocaat — bij een
> groter belang of twijfel loont het om deze brief eerst door een advocaat te laten checken.
> Wil je dat ik je zaak daarvoor vast als dossier klaarzet?* (→ skill `dossier`)

Bij een 🔴-situatie (lopende procedure, dreigend kort geding, strafrechtelijk): schrijf de
brief **niet** zelf, maar verwijs naar een advocaat en bied het dossier aan.

## Kwaliteitseisen per type

- **Aanmaning:** duidelijk bedrag, factuurnummer(s), redelijke betaaltermijn, vriendelijke
  maar duidelijke toon, aankondiging van een vervolgstap zonder te dreigen.
- **Sommatie/ingebrekestelling:** concrete verplichting, **redelijke termijn met een
  concrete datum**, expliciet het rechtsgevolg (verzuim, ontbinding, incasso, rente en
  kosten), en de juiste juridische grondslag met bron.
- **Reactie op claim:** erken feiten waar terecht, betwist gemotiveerd waar nodig, houd de
  toon zakelijk, en trek geen conclusies die je positie schaden — verwijs bij een reëel
  belang door naar een advocaat.

## Verplichte concept-markering (onderaan het document)

> *Concept — opgesteld met LawBot Business (Litic.ai). Controleer de gegevens en laat bij
> een groter belang een advocaat meekijken vóór verzending.*
