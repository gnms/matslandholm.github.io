
+++
date = '2026-10-22T20:50:00+02:00'
draft = true
title = 'Redundans – varför räcker det inte alltid med två?'
+++

I artiklarna om [fail-safe](/system_safety/fail_safe/) och [fail-operational](/system_safety/fail_operational/) har vi sett hur system kan upptäcka fel och reagera på dem.
Men hur upptäcker vi egentligen att något har gått fel?
Här kommer redundans in i bilden.
Redundans handlar förenklat om att ha flera komponenter eller funktioner som kan utföra samma uppgift, eller kontrollera varandra.
Det finns många olika sätt att bygga redundanta system, men vi ska bara skrapa lite på ytan.

## COM, MON och VOTER

Tänk dig att vi har en dator som utför en beräkning och lämnar ett resultat. Vi kallar den **COM (Command)**.
Vi lägger sedan till en annan dator som gör motsvarande beräkning och kontrollerar resultatet. Den kallar vi **MON (Monitor)**.
Men vem avgör om resultaten är tillräckligt lika?
Vi behöver något som jämför resultaten och bestämmer vad systemet ska göra. Det kallar vi här för **VOTER**.
<img src="/images/system_safety/com_mon.png"
     alt="Recept"
     style="float: right; width: 400px; margin: 15px 0 15px 20px; border-radius: 8px;">
Om COM och MON lämnar olika resultat kan VOTER upptäcka att något inte stämmer.
Men vilken av dem har rätt?
Det vet vi inte enbart genom att jämföra resultaten.
Om vi inte kan avgöra vilken vi ska lita på kan lösningen vara att försätta systemet i ett säkert tillstånd.
Det är ett exempel på hur redundans kan användas i ett [fail-safe-system](/system_safety/fail_safe/).

## Men om vi måste fortsätta?

I ett [fail-operational-system](/system_safety/fail_operational/) kanske vi inte har möjlighet att stanna.
Då behöver vi kunna hantera felet och ändå fortsätta fungera.
Ett sätt är att använda tre datorer som utför samma beräkning.
Om två datorer lämnar samma resultat och den tredje ett annat, kan VOTER använda majoritetsbeslut för att välja det resultat som två datorer är överens om.
Vi kan alltså fortsätta trots att en dator lämnar ett avvikande resultat.
<img src="/images/system_safety/trippel-channel.png"
     alt="Recept"
     style="float: right; width: 400px; margin: 15px 0 15px 20px; border-radius: 8px;">
Detta brukar kallas **Triple Modular Redundancy (TMR)**.
Men det bygger på att våra antaganden håller, bland annat att inte flera datorer drabbas av samma fel.

## Men vem övervakar VOTER?

Nu har vi tre datorer som kan kontrollera varandra.
Men vi har också skapat en ny fråga.
Vad händer om det är VOTER som går sönder?
Då riskerar hela säkerhetsmekanismen att sluta fungera som vi tänkt oss.
Det finns lösningar även på detta, exempelvis redundanta väljare, men då börjar vi komma djupare in i ämnet.

<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

  <strong>Avslutningsvis</strong>

  <p>
    Redundans kan hjälpa oss att upptäcka fel och låta systemet fortsätta fungera trots att något går sönder.
    Men bara för att vi har flera datorer betyder det inte automatiskt att vi har ett säkert system.
    Vad händer exempelvis om alla tre datorerna kör samma programvara och drabbas av samma programfel?
    Då kanske alla tre lämnar samma felaktiga resultat, och VOTER upptäcker ingenting.
    Det är just sådana beroenden vi behöver undersöka med
    <a href="/system_safety/common_cause_analysis/">Common Cause Analysis</a>.
  </p>

</div>
