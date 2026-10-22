
+++
date = '2026-10-22T20:50:00+02:00'
draft = true
title = 'Common Cause Analysis – varför räcker det inte med två datorer?'
+++

När man arbetar med säkerhetskritiska system får man ibland höra att man måste ha dubblerad hårdvara. Två separata datorer, och dessutom ska hårdvaran vara utvecklad enligt någon särskild standard.
Men varför?

Det är en fråga jag har ställt flera gånger genom åren, utan att alltid få något riktigt bra svar.
Om problemet exempelvis är att två program kan skriva över varandras minne, borde man inte kunna lösa det genom att separera deras minnesområden?
Man skulle kanske kunna använda olika delar av minnet eller låta hårdvaran skydda programmen från varandra.
Men svaret har ofta varit detsamma:

*Nej, det måste vara två separata datorer.*

Fortfarande utan någon riktigt bra förklaring till varför.

## Två datorer – men är de verkligen oberoende?
Tänk dig att vi har ett säkerhetskritiskt system med två datorer som utför samma beräkning.
Tanken är att om den ena datorn går sönder ska den andra kunna fortsätta fungera.
Det låter ju bra.
Men vad händer om båda datorerna kör samma programvara och det finns ett fel i programmet?
Om samma förutsättningar uppstår kan båda datorerna drabbas av samma fel.
Eller om båda datorerna läser information från samma givare och givaren börjar lämna felaktiga värden?
Då hjälper det kanske inte att vi har två datorer. Båda kan fatta samma felaktiga beslut.
Vi har byggt [redundans](/system_safety/redundans/), men inte nödvändigtvis oberoende.

## Common Cause Analysis
Det var när jag kom i kontakt med begreppet *Common Cause Analysis*, CCA, som jag började förstå varför det inte alltid räcker med redundans.
Enkelt uttryckt handlar analysen om att identifiera gemensamma orsaker och beroenden som kan göra att flera delar av ett system fallerar.
Vi tittar på våra redundanta system och ställer frågor som:
- Använder de samma programvara?
- Läser de från samma givare?
- Delar de strömförsörjning?
- Kan ett fel i en komponent påverka båda systemen?
- Finns det yttre händelser som kan slå ut båda samtidigt?

Det viktiga är att vi inte bara tittar på vad som kan gå fel i varje enskild komponent, utan också vad som kan göra att flera komponenter fallerar tillsammans.

## Måste vi då alltid ha två separata datorer?
Nej, inte nödvändigtvis.
Det beror på vilka fel vi behöver skydda oss mot och vilka säkerhetskrav systemet ska uppfylla.
Om vi kan visa att två funktioner på samma dator är tillräckligt oberoende för de fel vi behöver hantera, kanske vi inte behöver två fysiska datorer.
Men om analysen visar att ett fel i exempelvis processorn, minnet eller strömförsörjningen kan slå ut båda funktionerna, då kanske fysisk separation är nödvändig.
Och även om vi använder två datorer kan vi behöva separera andra saker, exempelvis givare eller strömförsörjning.
**Det är alltså inte antalet datorer som avgör om lösningen är säker, utan vilka fel arkitekturen faktiskt kan hantera.**

## Hur säker är tillräckligt säker?
Mycket inom systemsäkerhet handlar om att kunna visa att de [säkerhetsmekanismer](/system_safety/safety_mechanism/) vi inför verkligen ger det skydd vi förväntar oss.
Det innebär bland annat att vi måste bedöma sannolikheten för olika fel och vilka konsekvenser de kan få.
I vissa sammanhang arbetar man med mycket låga sannolikheter, exempelvis 10⁻⁶ eller 10⁻⁹ per timme för vissa typer av farliga fel eller händelser.
Vilka nivåer som är acceptabla beror på systemet, riskerna och de krav som gäller.
En Common Cause Analysis hjälper oss att identifiera beroenden som annars kan göra våra beräkningar alltför optimistiska.
Om vi exempelvis antar att två datorer fallerar oberoende av varandra, men båda kan slås ut av samma fel, då håller inte längre vårt antagande.

## Analysera istället för att bara följa en regel
Det är egentligen detta som jag tycker är det intressanta.
Istället för att kategoriskt säga att ett säkerhetskritiskt system måste ha två separata datorer borde vi börja med att fråga:
**Vilka fel måste systemet kunna hantera, och hur kan vi visa att vår arkitektur klarar dem?**
Ibland blir svaret två separata datorer. Ibland krävs ännu mer separation. Och ibland kan vi visa att en enklare lösning är tillräcklig.

<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

  <strong>Avslutningsvis</strong>

  <p>
    För mig är det just det som är poängen med säkerhetsanalyser.
    Att förstå varför vi inför en säkerhetsmekanism, istället för att bara göra som vi alltid har gjort.
  </p>

</div>
