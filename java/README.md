## Tools
### Intellij
Tijdens deze lessen maken we gebruik van de community editie van Intellij IDEA. Intellij kun je hier
downloaden: [https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download/)

Essentiele know hows van Intellij vind je hier: [Intellij - Deel 1](intellij.md)

### Git
De huiswerkopdrachten of eigen projecten die je in Java schrijft plaats je op Git. Git is een versiebeheersysteem
waar je je code kunt bergen en delen met anderen. Één van de belangrijskte features van Git, is dat je
altijd terug kan naar een vorig versie. Met de integratie van Git in Intellij kun je dus ook vrij
makkelijk een bestand terug halen die perongeluk is verwijderd, of een stuk code die je perongeluk hebt
veranderd.

Mocht je nog geen Github account hebben en Git nog niet geinstalleerd, dan kun je dat nu doen.
- https://github.com/
- https://git-scm.com/download/win

Het volgende artikel legt uit hoe je Git kunt gebruiken in Intellij:
[https://medium.com/swlh/intellij-idea-git-features-7fff92ffa6b5](https://medium.com/swlh/intellij-idea-git-features-7fff92ffa6b5)

### JDK
Om Java te kunnen draaien heb je de Java Development Kit (JDK) nodig. De JDK bevat de JVM
(Java Virtual Machine) en de JRE (Java Runtime Environment). De JVM is de machine die de Java
bytecode kan uitvoeren. De JRE is de machine die de JVM kan draaien. De JDK kun je automatisch 
downloaden bij het aanmaken van een nieuw project in Intellij.

### Maven
Apache Maven is een built- en dependency management tool. Stapsgewijs gaan we Maven gebruiken en
verkennen. Voor nu hoef je alleen te weten hoe je binnen intellij een Maven project kunt aanmaken.

### Je eerste Java project
In het menu van Intellij kies je voor `File > New > Project`. In het venster dat opent kies je bij `Build system` voor `Maven`.


Vul de volgende velden in:
- Name: les-1
- Location: kies een map waar jij al je java projecten onder wilt brengen
- Create Git Repository -> Uitvinken
- JDK: -> Download JDK -> Oracle OpenJDK 22
- Advanced Settings:
    - GroupId: nl.jouwgebruikersnaam
    - ArtifactId: les-1

Wanneer je op create klikt zal Intellij het Maven build process opstarten en een project voor je aanmaken
met alvast wat voorbeeld code.

### Code draaien
Je kunt op twee manieren de gegenereerde "Hello World" code draaien:
- Via Intellij door `src/main/java/[organisatie]/App.java` te openen en op de groene pijl te drukken.
- Via de terminal: Click aan de linkerkant in Intellij op de terminal knop ">_".
  - Ga naar de map `src/main/java`
  - Voer het volgende commando uit om je code te compilen: `javac nl/jouwgebruikersnaam/App.java`
  - Voer het volgende commando uit om je code te draaien: `java nl.jouwgebruikersnaam.App`

## Java Basics
- [Verschillen Phyton & Java](differences.md)
- [Variabelen](variables.md)
- [Primitive Types](primitive_types.md)
- [Scopes](scopes.md)

## Opdracht
Maak een klein programma dat uit een lijst van getallen telt hoeveel er even of oneven zijn.

1. Maak een array (int[]) met de volgende getallen: 42, 67, 35, 89, 24, 76, 58, 93, 7, 30, 83, 46, 13, 25, 98, 53, 17, 79, 57, 8.
2. Gebruik een for-loop om door de array te itereren.
3. Controleer voor elk getal of het even of oneven is met behulp van een if-else-statement.
4. Tel daarbij zowel de even en oneven getallen en sla deze op in een HashMap waarbij de key de string "even" of "oneven" is en de waarde de het toaal of "even" of "oneven" getallen is.

Letop: de HasMap heeft dus een "key" van het type String en een "value" van het type int.

### Checklist
- Variabelen zijn in het engels geschreven.
- Variabelen zijn in camelCase.
- Naamgeving van de variabelen zijn duidelijk en beschrijvend.
- Elk code block (begint met `{` en eindigt met `}`) wordt voorgegaan door een regel commentaar.
- Comments zijn in het engels geschreven.
- De code is geformateerd aan de hand van de Google Java Style Guide.
- Een loop bevat alleen code dat ook echt herhaalt hoort te worden. Berekeningen of andere zware
  operaties die voor elke iteratie hetzelfde blijven, horen niet in een loop te staan.
- Declareer variabelen zo dicht mogelijk waar het gebruikt word.
- De code bevat geen/tot zeer weinig code duplicatie. (DRY: Don't Repeat Yourself)