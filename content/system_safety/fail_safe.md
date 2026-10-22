+++
date = '2026-10-20T19:19:04+02:00'
draft = true
title = 'Fail-safe - när något går fel ska det inte bli farligt'
+++

Vi har tidigare beskrivit hur en säkerhetsmekanism kan upptäcka och hantera fel.
Men vad ska systemet göra när något går fel?

En möjlighet är att försätta systemet i ett säkert tillstånd. Det är grundtanken med fail-safe.
Tänk dig en maskin med rörliga delar. Rörelser innebär energi, och energi kan orsaka skador om den inte kontrolleras.

Ett enkelt exempel är ett nödstopp.
Här är det människan som övervakar maskinen. Om personen upptäcker något farligt kan denne trycka på nödstoppet, som gör att maskinens farliga rörelser stoppas.

Men vi kan också låta tekniken sköta övervakningen.
Vi kan exempelvis montera sensorer som upptäcker om någon kommer för nära en farlig rörelse. Om det händer reagerar säkerhetssystemet och stoppar rörelsen innan någon skadas.

Men måste vi alltid övervaka något?
Nej. Tänk dig en broms som hålls öppen med hjälp av elektricitet. Om strömmen försvinner aktiveras bromsen automatiskt och stoppar rörelsen.
Här behövs ingen sensor som upptäcker strömavbrottet. Konstruktionen gör att maskinen går till ett säkert tillstånd när strömmen försvinner.

Det är också fail-safe.


<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

  <strong>Avslutningsvis</strong>

  <p>
Fail-safe handlar alltså om att systemet ska hamna i ett säkert tillstånd när något går fel.
I vårt exempel innebär det att stoppa maskinens farliga rörelser.
Men tänk om det istället är farligt att stanna?
Då behöver vi en annan lösning.
Läs vidare: Fail-operational – när det inte är säkert att stanna.
  </p>

</div>


<img src="/images/system_safety/fail_safe.png"
     alt="Fail safe">