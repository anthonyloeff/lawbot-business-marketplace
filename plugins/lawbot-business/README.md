# LawBot Business

Juridische assistent voor de **MKB-ondernemer**. Bespaart advocaatkosten door eerlijke
triage — *wanneer heb je écht een advocaat nodig?* — en door je zaak advocaat-klaar voor te
bereiden, zodat je advocaat direct kan beginnen en jij goedkoper uit bent.

## Wat het doet

- **Zaak-intake & triage** — korte vragen, daarna een eerlijk oordeel: 🟢 zelf doen,
  🟠 voorbereiden + advocaat erbij, 🔴 nu een advocaat.
- **Dossier opbouwen & exporteren** — je zaak geordend als advocaat-klaar dossier (leesbaar
  voorblad + machineleesbare bundel die advocaten met LawBot Pro direct inlezen).
- **Brieven & sommaties** — aanmaning, ingebrekestelling, reactie op een claim, in gewone taal.
- **Contract- & voorwaardencheck** — risico's, rode vlaggen en onderhandelpunten uitgelegd.

Alles op **officiële Nederlandse bronnen** (rechtspraak.nl, wetten.overheid.nl e.a.) met
verifieerbare links. Je dossier blijft van jou: de server slaat geen inhoud op.

## Installeren

In Claude: **Customize → Plugins** → **+** → *Add marketplace* → *Add from a repository* →
`anthonyloeff/lawbot-business-marketplace`, en installeer **LawBot Business**.

Daarna:

1. Start je gratis proef van 14 dagen op **https://lawbot.nl/business** en kopieer je
   licentiesleutel (`lbb_…`).
2. **Connector verbinden:** in Claude → *Customize → Connectors* → **+** →
   *Add custom connector*, met als naam `lawbot-business` en als URL (exact overnemen, de
   plugin herkent de connector aan dit adres):

   ```
   https://fyzocmfqaatpivqjtphh.supabase.co/functions/v1/business-mcp/mcp
   ```

   Klik op **Connect**, plak op de inlogpagina van LawBot je sleutel (of vraag een
   inlogcode per e-mail aan) en keer terug naar Claude. In de plugin staat de connector
   daarna op *Connected*.
   *Zie je geen "Add custom connector" (Team- of Enterprise-omgeving)? Vraag dan je
   beheerder de connector met deze URL toe te voegen; daarna klik je zelf op Connect.*
3. Test met: *"Ik heb een klant die een factuur niet betaalt."*

**Claude Code (terminal):** plak je `lbb_`-sleutel in de plugin-instellingen; een custom
connector is daar niet nodig.

## Voor wie dit niet is

LawBot Business is voor **ondernemers**, niet voor advocaten. Ben je advocaat? Dan is
**[LawBot Pro](https://lawbot.nl)** de juiste tool. De twee sluiten op elkaar aan.

---
*LawBot Business geeft juridische informatie en voorbereiding, geen juridisch advies. — Litic.ai*
