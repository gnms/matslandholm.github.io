+++
date = '2026-10-22T20:50:00+02:00'
draft = true
title = 'Common Cause Analysis – behövs två datorer?'
+++

Vi har tidigare pratat om <a href="/system_safety/fault_tree/">felträd</a> och <a href="/system_safety/redundans/">redundans</a>, men hur säkert är egentligen ett system med dubblerade funktioner? Tänk om övervakaren drabbas av samma fel som den som ska övervakas?

I vår <a href="/system_safety/fault_tree/">felträdsanalys</a> kom vi fram till en säkerhetsarkitektur där vi förbättrade säkerheten genom att lägga till en övervakare.

<img src="/images/system_safety/car_system_2.png"
  alt="Styrsystem med styrning och övervakning"
  style="float: right; width: 400px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">

Men tänk om det finns ett konstruktionsfel i en komponent som gör att den under vissa förutsättningar lämnar felaktiga värden?

Om både styrningen och övervakaren använder samma information kan ett enda fel påverka båda funktionerna.

I felträdet har vi kanske antagit att styrningen och övervakaren fallerar oberoende av varandra. Men om ett enda fel kan påverka båda, blir vår beräknade säkerhet alltför optimistisk.

**Common Cause Analysis**

Det är här Common Cause Analysis (CCA) kommer in, CCA handlar om att identifiera gemensamma felorsaker och beroenden som kan påverka flera funktioner samtidigt.
Om vi analyserar vårt styrsystem upptäcker vi att styrningen och övervakaren delar flera komponenter:
- Samma givare i ratten.
- Samma vinkelgivare vid hjulen.
- Samma dator och därmed hårdvara och operativsystem.

Om exempelvis vinkelgivaren lämnar ett felaktigt värde kan både styrningen och övervakaren använda samma felaktiga information. Då finns risken att övervakaren inte upptäcker felet.
Vi har alltså en övervakare, men den är inte tillräckligt oberoende för att upptäcka alla fel vi kanske vill skydda oss mot.
Vad gör vi åt det?

Efter analysen kanske vi kommer fram till att systemet behöver förändras.

Vi skulle exempelvis kunna:
- Använda en annan typ av givare för övervakningen av rattens vinkel.
- Montera övervakarens vinkelgivare vid hjulen spegelvänt, så att givarna arbetar i motsatta riktningar.
- Flytta övervakningen till en egen dator, exempelvis en PLC med annan hårdvara och programvara.

<img src="/images/system_safety/car_system_3.png"
  alt="Styrsystem med separat övervakning och olika typer av givare"
  style="float: right; width: 400px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">
På så sätt kan vi minska risken för vissa gemensamma fel. Men även olika givare kan påverkas av samma mekaniska fel eller yttre störningar.
Men är systemet säkert nu?

Inte nödvändigtvis. Vi behöver fortfarande analysera exempelvis strömförsörjningen och hur ett fel i styrningen faktiskt ska hanteras.
Och kanske visar analysen att vi inte behöver separera allt. Det beror på vilka fel vi måste kunna hantera och vilka säkerhetskrav som gäller.

<div style="clear: both;"></div>

<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

<strong>Avslutningsvis</strong>

<p>
Vilka fel måste systemet kunna hantera, och hur kan vi visa att vår <a href="/system_safety/safety_architecture/">säkerhetsarkitektur</a> klarar dem?
</p>

<p>
Ibland krävs separata datorer, ibland ännu mer separation och ibland kan en enklare lösning vara tillräcklig.
</p>

<p>
För mig handlar säkerhetsanalyser om att förstå varför vi inför en <a href="/system_safety/safety_mechanism/">säkerhetsmekanism</a>, istället för att bara göra som vi alltid har gjort.
</p>

</div>