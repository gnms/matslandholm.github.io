+++
date = '2026-10-20T19:19:04+02:00'
draft = true
title = 'Fail-operational – när det inte är säkert att stanna'
+++


I artikeln om fail-safe såg vi hur en maskin kunde försättas i ett säkert tillstånd genom att stoppa motorn.
Men tänk om vi inte kan stanna maskinen?


Anta att motorn istället driver en hjärt-lungmaskin som håller en patient vid liv.
Om strömmen försvinner kan vi inte bara slå till bromsen och stanna motorn. Det skulle kunna få betydligt allvarligare konsekvenser än själva strömavbrottet.
<img src="/images/system_safety/fail_operational.png"
     alt="Fail operational"
     style="float: right; width: 300px; margin: 20px 0 15px 20px; border-radius: 8px;">
Här behöver vi istället en lösning som gör att maskinen kan fortsätta fungera trots felet.
Det är grundtanken med fail-operational.

Vi skulle exempelvis kunna ha en reservkraftlösning som tar över när den ordinarie strömförsörjningen försvinner. För att undvika avbrott kan det också behövas batterier som håller utrustningen igång tills reservkraften är tillgänglig.

Men betyder fail-operational att allt måste fortsätta fungera?
Nej, och det är här det blir intressant.
När ett sjukhus går över till reservkraft kanske det inte längre finns tillräckligt med energi för att driva allt.
Då kan man behöva koppla bort mindre viktiga förbrukare, som kaffebryggare och mikrovågsugnar, för att säkerställa att de livsuppehållande systemen fortsätter fungera.
Vi har alltså både stoppat vissa funktioner och låtit andra fortsätta.



<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

  <strong>Avslutningsvis</strong>

  <p>
Fail-operational handlar inte om att allt måste fortsätta fungera, utan om att de funktioner som måste upprätthållas ska kunna fortsätta trots fel.
Det kräver ofta redundans, alltså att alternativa komponenter eller system kan ta över när något går sönder.

  </p>

</div>