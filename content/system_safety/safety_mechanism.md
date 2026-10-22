+++
date = '2026-10-20T19:19:04+02:00'
draft = true
title = 'Vad är en säkerhetsmekanism?'
+++ 

En säkerhetsmekanism är något som bidrar till att förhindra att ett system orsakar skada.
Det kan vara en enda komponent eller flera komponenter som tillsammans utför en säkerhetsfunktion.

Det var ju lagom flummigt. 😃

Men vi kan förenkla det.
Tänk dig ett system där något kan gå fel och leda till en farlig situation.
Vi vill kunna upptäcka att något är på väg att hända och göra något åt det innan någon skadas.

En säkerhetsmekanism kan då bestå av tre delar:
<img src="/images/system_safety/safety_mechanism.png"
     alt="safety mechanism">

Det kan exempelvis vara två datorer som övervakar varandras resultat. Om resultaten skiljer sig åt upptäcks en avvikelse och systemet måste bestämma hur den ska hanteras.
Men alla säkerhetsmekanismer behöver inte innehålla dessa tre steg. Vissa fungerar helt passivt, utan vare sig sensorer eller beslutslogik.
Det viktiga är inte hur mekanismen är uppbyggd, utan att den hanterar en identifierad risk.


<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

  <strong>Avslutningsvis</strong>

  <p>
Vi har alltså en mekanism som ska förhindra att ett fel leder till en farlig konsekvens.
Men vad ska egentligen hända när vi upptäcker ett fel?
Ska vi stoppa systemet, eller ska vi försöka fortsätta?
Det leder oss till två viktiga principer: <a href="/system_safety/fail_safe/">fail-safe</a> och <a href="/system_safety/fail_operational/">fail-operational.</a>
  </p>

</div>