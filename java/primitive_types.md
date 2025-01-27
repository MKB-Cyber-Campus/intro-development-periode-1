## Primitive Types
Java kent 8 "primitieve" types, alle 8 hebben een "default" waarde:
- byte : 0
- short : 0
- int : 0
- long : 0L
- float : 0.0f
- double : 0.0
- char : '\u0000'
- boolean : false

Default waarde wil zeggen dat als je een variabel declareert, maar geen waarde toekent,
autmatisch een standaard waarde krijgt.
```java
int i; //i heeft nu de waarde 0
```
Deze types zijn "primitief" omdat ze geen methodes hebben, en geen "null" waarde kunnen hebben, in
tegenstelling tot "referentie" types (objecten).

### Numeric Types
De eerste 6 types zijn numeriek, en kunnen dus rekenkundige operaties uitvoeren.
```java
int i = 5;
int j = 3;
int k = i + j; //k = 8
```
De grootte van de numerieke types is als volgt:
- byte : 8 bits
- short : 16 bits
- int : 32 bits
- long : 64 bits
- float : 32 bits
- double : 64 bits

#### Integer types
De eerste 4 van de 6 (`byte`, `short`, `int`, `long`) kunnen geen decimale getallen bevatten en worden
daarom "integer" types genoemd.

`byte` wordt voornamelijk voor binaire data gebruikt, `short` voor kleine getallen, `int` voor de meeste
getallen, en `long` voor grote getallen. Het verschil tussen deze types zit hem dus voornamelijk in
hoeveel geheugen ze in gebruik nemen, en hoe groot de getallen kunnen zijn die ze kunnen bevatten.

Voor geheugen optimalisatie zou je dus geen `long` gebruiken wanneer je variabele alleen een "0" of een
"1" kan bevatten.

#### Floating Point Types
De laatste 2 van de 6 (`float`, `double`) kunnen wel decimale getallen bevatten en worden daarom
"floating point" types genoemd. `double` is de standaard keuze voor decimale getallen, omdat het
meer precisie biedt dan `float` en grotere getallen kan bevatten.

Als je wilt rekenen met decimale getallen moet je dus gebruik maken van `double`.
```java
double d = 3.14;
double e = 2.71;
double f = d * e; //f = 8.5094
```
### Char Type
`char` is een 16-bit type en kan dus een Unicode karakter bevatten. Unicode is een internationale
standaard voor het representeren van tekens in verschillende schriften. Een char kan dus een
letter, cijfer, leesteken, of een speciaal karakter bevatten.
```java
char c = 'a';
char d = '1';
char e = '!';
char f = '\u0000'; //null character
```
Omdat `char` een 16-bit type is kun je er ook mee rekenen. Bijvoorbeeld om een grid te generen voor
een spelletje.
```java
int boardSize = 5;
char maxChar = (char)('A' + boardSize - 1);

Map<String, String> board = new HashMap<>();
for(int y=1; y <= boardSize; y++){
    for(char x = 'A'; x < maxChar; x++){
      board.put(x + "" + y, "empty");
    }
}
System.out.println(board);

output: {D1=empty, C1=empty, D2=empty, B1=empty, C2=empty, D3=empty, A1=empty, B2=empty, C3=empty, D4=empty, A2=empty, B3=empty, C4=empty, D5=empty, A3=empty, B4=empty, C5=empty, A4=empty, B5=empty, A5=empty}
```