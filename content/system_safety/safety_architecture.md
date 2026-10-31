+++
date = '2026-10-22T20:50:00+02:00'
draft = true
title = 'Vad är en säkerhetsarkitektur?'
+++

Säkerhetsarkitektur var länge ett begrepp som jag inte riktigt fick kläm på. Men nu tror jag att jag har fått en bild av vad det faktiskt handlar om.
För mig handlar arkitektur om hur något är uppbyggt, vilka delar som ingår och hur de samverkar.
Ta exempelvis vårt styrsystem för en bil.

<img src="/images/system_safety/car_system_1.png"
     alt="Bilens styrsystem med rattgivare, dator, motor och vinkelgivare"
     style="float: right; width: 300px; max-width: 100%; margin: 15px 0 15px 20px; border-radius: 8px;">

Systemet består av:

- En ratt med givare.
- En dator som beräknar styrsignalen.
- En motor som styr hjulen.
- En vinkelgivare som återkopplar hjulens verkliga läge.

Detta är delar av systemets tekniska arkitektur. Den beskriver vilka komponenter som finns och hur de samverkar för att styra bilen.
Men hur säkerställer vi att bilen inte svänger fel?

## Från systemarkitektur till säkerhetsarkitektur

Genom <a href="/system_safety/fault_tree/">felträdsanalys</a> har vi identifierat vad som kan gå fel. Med <a href="/system_safety/common_cause_analysis/">Common Cause Analysis</a> har vi undersökt vilka gemensamma fel som kan påverka både styrning och övervakning.
Utifrån analyserna har vi förändrat arkitekturen.

<img src="/images/system_safety/car_system_3.png"
     alt="Bilens styrsystem med separat övervakning och redundanta givare"
     style="display: block; width: 500px; max-width: 100%; margin: 20px auto; border-radius: 8px;">

Vi har bland annat lagt till en separat övervakare och ytterligare givare för att minska risken att samma fel påverkar både styrningen och övervakningen.
Övervakningen är ett exempel på en <a href="/system_safety/safety_mechanism/">säkerhetsmekanism</a>.
Men säkerhetsarkitekturen handlar inte bara om vilka säkerhetsmekanismer vi använder, utan också om hur de är uppbyggda, vilka beroenden de har och hur de samverkar med resten av systemet.
Vi kan exempelvis använda olika säkerhetsprinciper:

- <a href="/system_safety/fail_safe/">Fail-safe</a> – systemet går till ett säkert tillstånd när något går fel.
- <a href="/system_safety/fail_operational/">Fail-operational</a> – systemet kan fortsätta utföra nödvändiga funktioner trots vissa fel.

Vilken lösning vi väljer beror på systemets säkerhetskrav.

## Så vad är en säkerhetsarkitektur?

Som jag ser det är säkerhetsarkitekturen **hur systemet är uppbyggt för att uppfylla sina säkerhetskrav**.
Det kan handla om att:

- Förhindra att farliga situationer uppstår.
- Upptäcka fel innan de leder till något farligt.
- Försätta systemet i ett säkert tillstånd när något går fel.
- Låta systemet fortsätta fungera trots att en komponent har gått sönder.

Det intressanta är att säkerhetsarkitekturen inte i första hand beskriver vad systemet ska göra, utan **hur systemet ska kunna göra det på ett säkert sätt**.

<div style="clear: both;"></div>

<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

<strong>Avslutningsvis</strong>

<p>
Är säkerhetsarkitekturen en separat arkitektur, eller är den egentligen bara ett sätt att betrakta systemarkitekturen ur ett säkerhetsperspektiv?
Jag lutar åt det senare.
Säkerhetsarkitekturen kan beskrivas separat, men den är inte frikopplad från systemets övriga arkitektur.
</p>

</div>