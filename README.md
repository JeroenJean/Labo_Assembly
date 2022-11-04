<details>
<summary>Click me</summary>
dit is een test
</details>

# Intro in Assembly

Assembly is een veruit de laatste verstaanbare programmeertaal die er bestaat.

# Omgeving opzetten
Voor het programmeren van onze assembly oefeningen, 

# Eerste programma

# Compileren

# Invoer en uitvoer
Voor het oplossen van de oefeningen, ga je regelmatig input moeten vragen aan de eindgebruiker. Echter het vragen van input of output generen in assembly is niet gedaan met 1 enkele lijn code. Daarnaast moet je ook al grondige kennis hebben van assembly om dit tot een goed einde te brengen. Omdat dit voorbij het doel van onderdeel gaat, mag gebruik maken van functies die wij voorzien.

Voor het vragen vragen van input maak je gebruik van `inv[test]`. Dit zorgt ervoor dat er aan de eindgebruiker een getal gevraagd wordt en opgeslagen wordt in de variabele `test`. Je mag `inv[<variable>]` ook enkel gebruiken met een variabelen. Rechtstreeks invoer naar een register is niet mogelijk.

Voor het tonen van een getal mag je gebruik maken van `uit[test]`. Dit zorgt ervoor dat de waarde van de variabele test aan de eindgebruiker wordt getoond. Je mag `uit[<variable>]` ook enkel gebruiken met een variabelen. Rechtstreeks de inhoude van een register aan de eindgebruiker laten zien is niet mogelijk.

# Oefeningen

Maak volgende programma's in assembly:
- Schrijf een programma dat aan de gebruiker een getal vraagt, dit getal leest en het vierdubbel ervan toont op het scherm.
- Schrijf een programma dat aan de gebruiker 3 getallen vraagt en de som ervan toont op het scherm.
- Schrijf een programma dat aan de gebruiker een getal vraagt, dit getal leest en het 19-voud ervan toont op het scherm. Je kan het getal 18 keer bij zichzef bijtellen met 18 add-bevelen. Even denken, het kan ook met veel minder bevelen!
- Schrijf een programma dat drie getallen vraagt (x, y en z) en dat dan de waarde van 2x + 4y + 8z toont. Om het programma wat efficiënter te maken:
- Schrijf een programma dat de waarde van B²-4AC toont. Eerst worden de waarden van A, B, C ingelezen.
- Schrijf een programma dat een getal leest, A, en de waarde van A^7 toont. (Hoe groot kunnen onze getallen zijn? Als A7 kan, hoe groot kan A dan zijn?)
- Definieer constanten met als waarden: 3, 12, 1583, 274, 420, 11. Gebruik voor de optelling en de aftrekking EDX als accumulator. Schrijf een programma dat:
  - 3 + 12 berekent en het resultaat toont;
  - 3 - 12 berekent en het resultaat toont;
  - Quotiënt en rest berekent van de deling 1583 / 274 en deze resultaten toont;
  - 420 * 11 berekent en het resultaat toont.
