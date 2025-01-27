## Decleratie en assignment van variabelen
Een variabele is een stukje geheugen waarin een waarde kan worden opgeslagen. In Java kan een variabele worden gedeclareerd en geïnitialiseerd. De declaratie van een variabele gebeurt door het type van de variabele te specificeren, gevolgd door de naam van de variabele. De initialisatie van een variabele gebeurt door de variabele een waarde toe te kennen.
```java
int a; // declaratie van variabele a
a = 5; // initialisatie van variabele a
```
De declaratie en initialisatie van een variabele kan ook in één regel worden gedaan.
```java
int a = 5; // declaratie en initialisatie van variabele a
```
De waarde van een variabele kan worden aangepast door deze een nieuwe waarde toe te kennen.
```java
a = 10; // variabele a krijgt een nieuwe waarde
```

## Variabele naamgeving
In Java mogen variabel namen alleen beginnen met een letter of een underscore. De overige karakters
mogen letters, cijfers, underscores of dollartekens zijn.
```Java
int _a1$; // is een geldige variabel naam
```
Voor het benoemen van variablen in Java houden we ons aan camelCase notatie. Dit betekent dat de
eerste letter met een kleine letter begint en de eerste letter van elk volgend woord met een hoofdletter begint.
```java
String numberOfStudents; // camelCase notatie
```
Variabelen mogen afgekort worden als er van de initialisatie valt af te leiden wat de variabele betekent.
```java
BufferedReader br = new BufferedReader(new FileReader("file.txt"));
```
Anders is het beter om de variabele een duidelijke naam te geven.
```java
double interestRate = 0.05; // het is van de naam af te leiden waar het voor bedoeld is
```
*Letop: Java is case-sensitive: `numberofstudents` en `numberOfStudents` zijn twee verschillende variabelen.*

### Gereserveerde keywords
De volgende keywords zijn gereserveerd in Java en mogen niet gebruikt worden als variabele naam:

|   |   |   |   |   |   |
|---|---|---|---|---|---|
| abstract | assert | boolean | break | byte | case |
| catch | char | class | const | continue | default |
| do | double | else | enum | exports | extends |
| final | finally | float | for | goto | if |
| implements | import | instanceof | int | interface | long |
| module | native | new | non-sealed | open | opens |
| package | permits | private | protected | provides | public |
| record | requires | return | sealed | short | static |
| strictfp | super | switch | synchronized | this | throw |
| throws | to | transient | transitive | try | uses | var |
| void | volatile | while | with | yield | -