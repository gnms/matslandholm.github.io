Vad är en säkerhetsarkitektur?

Säkerhetsarkitektur var länge ett begrepp som jag inte riktigt fick kläm på. Men nu tror jag att jag har fått en bild av vad det faktiskt handlar om.

Vi har tidigare tittat på säkerhetsmekanismer och två principer för att hantera fel: fail-safe och fail-operational.

Men hur hänger allt ihop?

En säkerhetsmekanism kan bestå av en eller flera komponenter som tillsammans bidrar till systemets säkerhet.

En del mekanismer ser till att systemet hamnar i ett säkert tillstånd när något går fel. Andra gör att systemet kan fortsätta fungera trots fel.

Och ett system kan mycket väl behöva båda delarna.

Så vad är då en säkerhetsarkitektur?

Som jag ser det är det helheten av de komponenter och mekanismer som bidrar till systemets säkerhet, och hur dessa samverkar.

Det kan handla om att:

Förhindra att farliga situationer uppstår.

Upptäcka fel innan de leder till något farligt.

Försätta systemet i ett säkert tillstånd när något går fel.

Låta systemet fortsätta fungera trots att en komponent har gått sönder.

Det intressanta är att säkerhetsarkitekturen inte i första hand beskriver vad systemet ska göra, utan hur systemet ska kunna göra det på ett säkert sätt.





<div style="border-left: 4px solid #64748b;
            background-color: #f1f5f9;
            padding: 16px 20px;
            margin: 30px 0;
            border-radius: 6px;
            color: #334155;">

  <strong>Avslutningsvis</strong>

  <p>
Är säkerhetsarkitekturen en separat arkitektur, eller är den egentligen bara ett sätt att betrakta systemarkitekturen utifrån ett säkerhetsperspektiv?
Jag lutar åt det senare.
Säkerhetsarkitekturen kan beskrivas separat, men den är inte frikopplad från systemets övriga arkitektur.
  </p>

</div>