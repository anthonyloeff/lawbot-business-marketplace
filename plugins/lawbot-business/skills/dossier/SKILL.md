---
name: dossier
description: Bouwt het "advocaat-klare" dossier van de ondernemer op en exporteert het in twee lagen (leesbaar voorblad + machineleesbare bundel die LawBot Pro direct inleest). MOET actief worden bij /lawbot-business:dossier, "maak mijn dossier", "klaarmaken voor mijn advocaat", "alles op een rij zetten", "wat moet ik mijn advocaat sturen", of als vervolg op een oranje/rode triage.
---

# Dossier opbouwen & exporteren (het advocaat-haakje)

Doel: de zaak van de ondernemer zó vastleggen dat een advocaat **direct kan beginnen** —
geen rommelig mailbestand, maar een geordend dossier. Dit bespaart de ondernemer het
duurste dat er is: de tijd waarin een advocaat zijn zaak nog moet uitpluizen.

## Waar het dossier leeft (privacy)

Het dossier is een **map bij de ondernemer zelf** (zijn werkmap in Cowork of eigen schijf).
De LawBot-server slaat niets van de inhoud op. Standaardlocatie: een map `dossier-<zaak>/`
in de werkmap. Werk het dossier bij over meerdere sessies door dezelfde map te lezen en
aan te vullen.

## Structuur van de dossiermap

```
dossier-<zaaknaam>/
  dossier.json        ← manifest (machineleesbaar; zie templates/dossier.schema.json)
  voorblad.md         ← leesbare samenvatting (bron voor Word/PDF-export)
  stukken/            ← de originele bestanden (contract, facturen, mails, …)
```

## Werkwijze

1. **Verzamel de kern** (uit de intake, of vraag kort na als er iets ontbreekt):
   partijen, korte omschrijving, chronologische **tijdlijn**, wat de ondernemer wil
   bereiken, de **rechtsvraag** in één zin, de aanwezige stukken, en de triage-kleur.
2. **Onderbouw met bronnen.** De relevante wetsartikelen en eventuele richtinggevende
   uitspraken zoek je op via de tools en neem je op mét `bron_url`. Nooit een vindplaats
   verzinnen — liever `[nog opzoeken]`.
3. **Schrijf het `voorblad.md`** met het template `templates/voorblad.md` — dit is wat een
   advocaat als eerste leest: samenvatting, partijen, tijdlijn, rechtsvraag, gewenste
   uitkomst, overzicht stukken, geraadpleegde bronnen.
4. **Schrijf `dossier.json`** volgens `templates/dossier.schema.json` — dezelfde inhoud
   machineleesbaar, met `"formaat": "lawbot-dossier/1.0"`. Dit is de laag die **LawBot Pro
   herkent en direct inleest** (de advocaat hoeft niets over te typen).
5. **Kopieer de stukken** naar `stukken/` (of noteer waar ze staan als de ondernemer ze
   niet wil verplaatsen) en zet ze in `dossier.json` onder `stukken` met een korte duiding.
6. **Exporteer het voorblad** desgevraagd naar Word of PDF (docx-/pdf-skill) in de
   outputs-map, zodat de ondernemer het kan mailen. Buiten Cowork: lever nette markdown +
   meld dat export in Cowork kan.

## Oplevering aan de ondernemer

Sluit af met een korte, geruststellende samenvatting:
- wat er in het dossier zit,
- de losse export die hij naar zijn advocaat kan sturen,
- de zin: *"Dit werkt bij elke advocaat. Werkt jouw advocaat met LawBot Pro, dan leest hij
  het dossier in één keer in."*
- de standaarddisclaimer.

Bewaar-belofte herhalen: het dossier staat alleen bij hem; wij bewaren niets.

## Kwaliteitseisen

- Feiten en meningen strikt scheiden; de tijdlijn is puur feitelijk met data.
- De rechtsvraag scherp en in één zin ("Mag leverancier X de overeenkomst eenzijdig
  opzeggen zonder opzegtermijn?").
- Elke juridische verwijzing verifieerbaar (artikel/ECLI uit tool-output + `bron_url`).
- Nooit conclusies trekken die de advocaat toekomen; het dossier bereidt vóór, het beslist
  niet.
