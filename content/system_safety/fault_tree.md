+++
date = '2026-10-27T10:00:00+01:00'
draft = true
title = 'Felträd - ett sätt att analysera fel'
+++

När man arbetar med systemsäkerhet behöver man kunna förstå vad som kan gå fel, men också hur olika fel kan påverka varandra.

En av flera metoder för detta är **Fault Tree Analysis (FTA)**.
Hur ska man tänka med felträd, ju man ska tänka **vad kan orsaka en olycka?**

Ett felträd börjar med en oönskad händelse, exempelvis att en bil svänger utan att föraren har begärt det.
<img src="/images/system_safety/car_system_1.png"
  alt="Styrsystem med styrning och övervakning i samma dator"
  style="float: right; width: 400px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">
Sedan arbetar vi oss bakåt och försöker identifiera vad som skulle kunna orsaka händelsen.
Det kan exempelvis vara att:
<img src="/images/system_safety/fta_1.png"
  alt="Styrsystem med styrning och övervakning i samma dator"
  style="float: right; width: 300px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">
- Fel på givaren i ratten.
- Styrningen beräknar fel vinkel.
- Vinkelgivaren är fel.


Med hjälp av logiska grindar, framför allt **AND** och **OR**, beskriver vi vilka fel som var för sig eller tillsammans kan orsaka den oönskade händelsen.
En OR-grind innebär att det räcker med ett av felen, medan en AND-grind innebär att flera fel måste inträffa tillsammans.
Genom att tillföra sannolikheter för de olika felen kan vi också beräkna sannolikheten för den oönskade händelsen, förutsatt att vi har en korrekt modell och hanterar beroenden mellan felen.

<img src="/images/system_safety/car_system_2.png"
  alt="Styrsystem med styrning och övervakning i samma dator"
  style="float: right; width: 400px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">
Utifrån felträdet ser man svagheterna i systemet, man ser att det räcker att en del i systemet fallerar så kan händelsen inträffa. systemet bygg på med redundans, ett övervakningsystem som ska säkerställa att föraen blir varnad och kan kontrollerat bromas om något händer.
I det nya felträdet ser man att det tillkommit en **AND** grind och det visar att båda system ska fallera i den nya säkerhetsarkitekturen.

<img src="/images/system_safety/fta_2.png"
  alt="Styrsystem med styrning och övervakning i samma dator"
  style="float: center; width: 600px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">




<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">
<strong>Avslutningsvis</strong>
<p>
Det intressanta med dessa analyser är att vi inte bara behöver gissa oss till om en konstruktion är säker.
Vi kan bryta ner systemet, identifiera hur fel kan uppstå och analysera vilka konsekvenser de får.

<strong>Men är systemet riktigt säkert ändå?</strong> 
det reder vi ut med hjälp av <a href="/system_safety/common_cause_analysis/">Common Cause Analysis</a>.
</p>
</div>