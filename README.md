# Intro in Assembly

Assembly is veruit de laatste verstaanbare programmeertaal die er bestaat. Alle programmeertalen worden immers eerst door hun eigen compiler omgezet naar assembly en vervolgens naar machine code. Hoewel het niet noodzakelijk is om volwaardig te kunnen programmeren in assembly binnen de opleiding, is het wel handig om een basiskennis van assembly te hebben. Het analyseren van virusen komt er immers vaak op neer op het analyseren van de assembly code van dat virus om zo te achterhalen hoe het virus in interactie gaat met je systeem. Daarnaast maakt een basiskennis van assembly ook meteen duidelijk hoe een CPU gebruik maakt van registers en ALU.

# Omgeving opzetten
Voor het programmeren van onze assembly oefeningen, zijn er verschillende mogelijkheden. Er zijn vele online omgevingen waar je assembly kan schrijven en testen. Echter deze laten niet toe om gebruik te maken van hulpfuncties dewelke wij aanbieden. Om dit goed te faciliteren, gaan we gebruik maken van leia. Dit is een server die je kan gebruiken om je oefeningen in te programmeren en te testen. Volgende stappen zorgen ervoor dat je assembly omgeving correct is opgezet.
- Log via SSH in op leia.uclllabs.be op poort 22345 met je rnummer.
- Maak een nieuwe directory aan.
- Clone volgende git repo in de net aangemaakte directory: https://github.com/swenr/CompSys_Assembler.git

Dit zal een nieuwe directory `CompSys_Assembler` hebben aangemaakt met volgende bestanden:
```
jeroen@laptop-ucll:~/Documents/UCLL/CompSys/test/CompSys_Assembler$ ls -l
total 40
-rw-rw-r-- 1 jeroen jeroen  1657 Nov  4 22:26 gt.asm
-rw-rw-r-- 1 jeroen jeroen 11015 Nov  4 22:26 gtine.asm
-rw-rw-r-- 1 jeroen jeroen   385 Nov  4 22:26 readme.md
-rw-rw-r-- 1 jeroen jeroen   405 Nov  4 22:26 test.asm
-rw-rw-r-- 1 jeroen jeroen   365 Nov  4 22:26 test.in
-rw-rw-r-- 1 jeroen jeroen   213 Nov  4 22:26 test.uit
-rwxrwxr-x 1 jeroen jeroen    34 Nov  4 22:26 vertaal
-rwxrwxr-x 1 jeroen jeroen    54 Nov  4 22:26 voeruit
```
Zoals je kan zien zijn er reeds enkele x.asm bestanden. Hierover later in het labo meer uitleg.
Het gemakkelijkste gaat zijn, als je al je oefeningen in deze folder maakt.

# Assembleren en uitvoeren
Alvorens we een programma kunnen uitvoeren, moet de geschreven assembly code omgezet worden naar machine code. Doordat wij gebruik mogen maken mnemotechnische functie code en symbolische adressen, moeten deze eerst correct worden omgezet naar hexadecimale code. Dit laatste is immers het enigste wat een CPU verstaat (eigenlijk binair, maar hexadecimaal is gemakkelijker om te lezen). Omzetten van de mnemotechnische functie code naar machine code en symbolische adressen correct berekenen om gebruik te kunnen maken van het geheugen, gebeurt door een assembleerprogramma of assembler.

Om dit vlot te laten verlopen, hebben wij een bash script geschreven dat dit voor jullie zal doen: 
```
$ ./vertaal vraag1
vraag1.asm:4: warning: uninitialized space declared in non-BSS section `.data': zeroing [-w+zeroing]
vraag1.asm:5: warning: uninitialized space declared in non-BSS section `.data': zeroing [-w+zeroing]
```
Het volstaat dus om `vertaal` op te roepen gevolgd door de filename zonder extensie. Dit zal een .o bestand (object bestand) maken van je programma.

Dit bestand kunnen we echter nog niet uitvoeren. Omdat we ook gebruik maken van functie's die in een andere programma staan geschreven (gtine.asm en gt.asm) alsook subroutines van het OS, moeten deze nog op een correcte manier bij elkaar worden samengevoegd en gecompileerd worden tot 1 uitvoerbaar bestand. Ook hier hebben wij een bash script voor geschreven dat dit voor jullie doet:
```
$ ./voeruit vraag1
graag een getal tussen -2147483648 en 2147483647 : 12
48
```
❗ maak gebruik van `vertaal` om object bestanden aan te maken van gtine.asm en gt.asm.

# Invoer en uitvoer
Voor het oplossen van de oefeningen, ga je regelmatig input moeten vragen aan de eindgebruiker. Echter het vragen van input of output generen in assembly is niet gedaan met 1 enkele lijn code. Daarnaast moet je ook al grondige kennis hebben van assembly om dit tot een goed einde te brengen. Omdat dit voorbij het doel van het OP gaat, mag je gebruik maken van functies die wij hebben voorzien.

Voor het vragen vragen van input maak je gebruik van `inv[test]`. Dit zorgt ervoor dat er aan de eindgebruiker een getal gevraagd wordt en opgeslagen wordt in de variabele `test`. Je mag `inv[<variable>]` ook enkel gebruiken met een variabelen. Rechtstreeks invoer naar een register is niet mogelijk.

Voor het tonen van een getal mag je gebruik maken van `uit[test]`. Dit zorgt ervoor dat de waarde van de variabele test aan de eindgebruiker wordt getoond. Je mag `uit[<variable>]` ook enkel gebruiken met een variabelen. Rechtstreeks de inhoud van een register aan de eindgebruiker laten zien is niet mogelijk.

# Oefeningen
Nu je omgeving correct is opgezet en je een programma kan asembleren en compileren, is het tijd om zelf aan de slag te gaan.

Maak volgende programma's in assembly:
- Schrijf een programma dat aan de gebruiker een getal vraagt, dit getal leest en het vierdubbel ervan toont op het scherm.
- Schrijf een programma dat aan de gebruiker 3 getallen vraagt en de som ervan toont op het scherm.
- Schrijf een programma dat aan de gebruiker een getal vraagt, dit getal leest en het 19-voud ervan toont op het scherm. Je kan het getal 18 keer bij zichzef bijtellen met 18 add-bevelen. Even denken, het kan ook met veel minder bevelen!
- Schrijf een programma dat drie getallen vraagt (x, y en z) en dat dan de waarde van 2x + 4y + 8z toont.
- Schrijf een programma dat de waarde van B²-4AC toont. Eerst worden de waarden van A, B, C ingelezen.
- Schrijf een programma dat een getal leest, A, en de waarde van A^7 toont. (Hoe groot kunnen onze getallen zijn? Als A7 kan, hoe groot kan A dan zijn?)
- Definieer constanten met als waarden: 3, 12, 1583, 274, 420, 11. Gebruik voor de optelling en de aftrekking EDX als accumulator. Schrijf een programma dat:
  - 3 + 12 berekent en het resultaat toont;
  - 3 - 12 berekent en het resultaat toont;
  - Quotiënt en rest berekent van de deling 1583 / 274 en deze resultaten toont;
  - 420 * 11 berekent en het resultaat toont.
