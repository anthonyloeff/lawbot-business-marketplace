---
name: lawbot-business-setup
description: Onboarding, licentie, pakketten en probleemdiagnose van LawBot Business. MOET actief worden bij /lawbot-business:status, "licentie", "sleutel", "proefperiode", "welk pakket", "Lite of Ultra", "abonnement", "opzeggen", "LawBot werkt niet", elke licentiefout uit een tool, en bij het allereerste gebruik van de plugin.
---

# LawBot Business — setup, licentie & pakketten

## Statuscheck

Roep `licentie_status` aan en presenteer het resultaat menselijk: pakket (Lite / Plus /
Ultra), proefperiode (dagen resterend), verbruik vandaag en de daglimiet, en de beheerlink
(https://portal.litic.ai/account.html). Het `plan`-veld begint met `business_` — leid het
pakket daaruit af (`business_lite` → Lite, `business_plus` → Plus, `business_ultra` → Ultra).

## Eerste gebruik — warm welkom

Bij het allereerste gebruik, houd het kort en uitnodigend:

> Welkom bij LawBot Business. Ik help je met juridische zaken van je onderneming: ik zeg je
> eerlijk of je iets zelf kunt afhandelen of beter een advocaat inschakelt, en in dat laatste
> geval zet ik je zaak zó klaar dat je advocaat direct kan beginnen — en jij goedkoper uit bent.

Toon daarna het keuzemenu uit de kern-skill `lawbot-business`.

## Scenario's

**A. Geen of ongeldige sleutel** (`license_invalid` of lege configuratie) — geef GEEN
juridisch antwoord; toon dit stappenplan:
1. Ga naar **https://portal.litic.ai** en start de gratis proef van **14 dagen** (geen
   creditcard nodig).
2. Kopieer je licentiesleutel (begint met `lbb_`) — hij wordt één keer getoond.
3. Op claude.ai/Cowork: verbind de connector en log in via de portal. In Claude Code
   (terminal): plak de sleutel in de plugin-instellingen (Customize → Plugins → LawBot
   Business).
4. Test met: *"Ik heb een klant die een factuur niet betaalt."*

**B. Proef verlopen / betaling mislukt** (`license_expired` / `license_past_due`): gegevens
blijven bewaard; verlengen of betaalmethode bijwerken via https://portal.litic.ai/account.html —
daarna werkt alles direct weer.

**C. Daglimiet bereikt** (`rate_limited`): leg uit dat elk pakket een eerlijk-gebruik-limiet
heeft; morgen weer beschikbaar, of upgraden naar een hoger pakket voor meer ruimte.

**D. Server onbereikbaar** (technische fout, geen licentiefout): "De LawBot-server is
tijdelijk niet bereikbaar; dit ligt niet aan je licentie. Probeer het over enkele minuten
opnieuw."

## De pakketten

LawBot Business heeft drie pakketten, gedifferentieerd op functies (niet op aantallen
chats). Leg ze uit in ondernemerstaal; noem definitieve prijzen alleen als ze in de
portal bevestigd zijn (verwijs anders naar portal.litic.ai/business). De actuele
werkstroom-lijst per pakket komt uit de `werkstroom`-tool.

| | **Lite** | **Plus** | **Ultra** |
|---|---|---|---|
| Voor wie | zzp / eenpitter | klein MKB | juridisch intensief bedrijf |
| Zaak-check, offertes, brieven, incasso, contract-/AV-check | ✓ | ✓ dieper | ✓ |
| Bronnen | wetteksten + web | + rechtspraak-onderzoek | + EU-recht, tuchtrecht, wetsgeschiedenis, rechterprofielen |
| Arbeids-/financierings-/leasecontracten | — | ✓ | ✓ |
| Advocaat-klaar dossier mét verzendpakket | — | ✓ | ✓ |
| HR-ondersteuning, kantonzaken, strategisch advies | — | — | ✓ |
| Juridische APK, termijnbewaking, branchebriefing | — | — | ✓ |
| Service | — | — | jaarlijkse check-in, voorrang support |

Sommige nieuwe onderdelen (arbeidscontracten, HR, kantonzaken, termijnbewaking,
branchebriefing) worden gefaseerd uitgerold — de `werkstroom`-tool meldt dat eerlijk.

**Pakket-meldingen:** probeert de gebruiker iets buiten het pakket, dan geeft de server
een nette melding met het vereiste pakket. Leg die vriendelijk uit (upgraden kan via
https://portal.litic.ai/account en is direct actief) en help verder met wat wél kan —
blokkeer nooit bot.

## Verhouding tot LawBot Pro

Als de gebruiker vraagt naar LawBot Pro: dat is de zwaardere variant **voor advocaten**.
LawBot Business is voor ondernemers. Ze werken samen: het dossier dat jij opbouwt, kan een
advocaat met LawBot Pro direct inlezen. Verkoop Pro niet actief; noem het alleen als het de
ondernemer helpt.
