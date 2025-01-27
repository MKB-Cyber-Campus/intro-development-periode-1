## Verschillen tussen Java & Phyton
Er zijn een aantal verschillen tussen het schrijven van code voor Python en Java. Hier vindt je een
vergelijking op basis van de lessen van Martin.

### Compilatie
Het grootste verschil tussen Javan & Python is dat Python een dynamische taal is en Java een statische taal.
Dit betekent dat je in Java vooraf veel meer moet definieren terwijl Python zelf aannames doet in runtime.
Daarnaast is Java een stuk verboser dan Python. In Java moet je veel meer code schrijven om hetzelfde
resultaat te krijgen als in Python.

Neem als voorbeeld Hello World:

**Python**
```Python
print("Hello World")
```
**Java**

Bestand: HelloWorld.java
```Java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```
Omdat Java een object georienteerde taal is kun je niet alleen `System.out.println("Hello World");`
in een bestand zetten en het runnen. Je moet eerst een class aanmaken. En omdat je niet direct
in een class een "expressie" kunt schrijven moet je binnen de class ook een method aanmaken.

*Letop: een bestand waar een class in staat moet een naam hebben die overeenkomt met de naam van de class.*

Wanneer je code runt zal Java als eerste opzoek gaan naar de `main` method, dit is het start
punt van je programma en Java verwacht dat deze method de parameter `String[] args` meekrijgt.

Als je van deze structuur afwijkt zal je code niet draaien.

### Scope & Indentation
Waar Python gebruik maakt van indentation om aan te geven dat een stuk code bij een bepaalde
scope hoort, maakt Java gebruik van `{}`. In Java gebruik je eigenlijk alleen whitespaces voor de
leesbaarheid.

Hoewel het niet netjes is kun je in Java de code ook zo schrijven:
```Java
public class HelloWorld { public static void main(String[] args) { System.out.println("Hello World"); }}
```
In Python is dit niet mogelijk, de code zal niet werken. Omdat Java niet naar whitespaces kijkt
moeten we dus elke regel eidigen met `;` en bepalen we de scope met curly braces `{}`.

### Types
**Python**
```Python
x = 5
```
**Java**
```Java
int x = 5;
```

Phyton snapt meteen dat x een integer is, in Java moet je dit expliciet aangeven. Hoewel dit voelt
als extra werk maakt het je code een stuk leesbaarder en biedt het "type safety", wat betekent dat
je niet zomaar een string in een integer kan stoppen of andersom. Er kunnen dus niet onbedoeld bugs
optreden omdat je perongeluk een verkeerd type aan een variabel hebt meegegeven.

Java kent 8 primitieve types:
- byte : 0
- short : 0 
- int : 0
- long : 0L
- float : 0.0f
- double : 0.0
- char : 'a'
- boolean : false

Hoe deze types gebruikt kunnen worden gaan we nu niet op in, maar het is goed om te weten dat Java
een stuk strikter is in het gebruik van types dan Python.

Meer over de datatypes kun je hier lezen: https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html

### If statements
**Python**
```Python
if x > 5:
    print("x is groter dan 5")
elif x == 5:
    print("x is gelijk aan 5")
else:
    print("x is kleiner dan 5")
```
**Java**
```Java
if (x > 5) {
    System.out.println("x is groter dan 5");
} else if (x == 5) {
    System.out.println("x is gelijk aan 5");
} else {
    System.out.println("x is kleiner dan 5");
}
```
Zoals je kunt zien is de syntax van de if statements in Java en Python bijna hetzelfde. Het enige
verschil is dat je in Java de conditie tussen `()` zet en de code tussen `{}`.

Waar je wel op moet letten is dat de expressie die je binnen de if statement zet een boolean moet
zijn. In Python kun je bijvoorbeeld een string of een int in een if statement zetten en Python zal
kijken of deze waar is. In Java moet je expliciet aangeven dat je een boolean verwacht.

Bijvoorbeeld wanneer je iets wilt printen als de string `hello` niet leeg is:
**Python**
```Python
hello = "Hello"
if hello:
    print("Hello")
```

**Java**
```Java
String hello = "Hello";
if(hello){
    System.out.println("Hello");
}
Error: incompatible types: String cannot be converted to boolean
```
In java moet de expressie dus een boolean zijn en is het een stuk omslachtiger om te controleren:
```Java
String hello = "Hello";
if(hello != null && !hello.isEmpty()){
    System.out.println("Hello");
}
```
Eerst wordt gekeken of de `hello` niet `null` is (de default waarde van een String) en daarna wordt
gekeken of de string geen lege waarde heeft `""`.

Dit voelt wat omslachtig en dat heeft er mee te maken dat in Java een `String` geen primitieve type
is maar een object (ook wel een "referentie type" of "complexe type").

Later zullen we meer in gaan op objecten.

#### Logical operators
Een ander verschil die zowel voor loops als de if statements geldt is dat de logical operators in Java
anders zijn dan in Python.

OR en AND in Python:
```Python
if x > 5 or x < 10:
    print("x is groter dan 5 of kleiner dan 10")
    
while x > 5 and x < 10:
    print(x)
```
```Java
if (x > 5 || x < 10){
    System.out.println("x is groter dan 5 of kleiner dan 10");
}

while(x > 5 && x < 10){
    System.out.println(x);
}
```

### Loops
#### For loop
**Python**
```Python
for i in range(5):
    print(i)
    if i == 2:
        break
```
**Java**
```Java
for(int i = 0; i < 5; i++){
    System.out.println(i);
    if(i == 2){
      break;  
    }
}
```
In Java moet je de variabele `i` eerst definieren, daarna geef je de conditie op waaraan voldaan moet
worden om de loop te blijven draaien en daarna geef je aan wat er moet gebeuren na elke iteratie.
Zoals je kunt zien kun je binnen Java ook `break` en `continue` gebruiken.

Gelukkig is de for loop voor het uitlezen van een array (list in Python) een stuk makkelijker:
**Python**
```Python
arr = [1, 2, 3, 4, 5]
for i in arr:
    print(i)
```
**Java**
```Java
int[] arr = {1, 2, 3, 4, 5};
for(int i : arr){
    System.out.println(i);
}
```
Vrijwel hetzelfde als in Python, alleen moet je bij Java het type van de array en variabel `i` aangeven.

#### While loop
**Python**
```Python
i = 0
while i < 5:
    print(i)
    i += 1
```
**Java**
```Java
int i = 0;
while(i < 5){
    System.out.println(i);
    i++;
}
```
Ook hier is de syntax vrijwel hetzelfde.

### Arrays (Lists in Python)
Zoals we bij de for loop al zagen is de syntax voor het aanmaken van een array in Java en een list in
Python vrijwel hetzelfde met het enige verschil dat je in Java het type van de array moet aangeven.

**Python**
```Python
arr = [1, 2, 3, 4, 5]
print(arr[0]) # 1
```

**Java**
```Java
int[] arr = {1, 2, 3, 4, 5};
System.out.println(arr[0]); // 1
```
In Python kun je een list aanmaken met verschillende types, in Java kan dat dus niet. Als je een array
van integers aanmaakt kun je er geen ander type in stoppen.

### HashMap (Dictionary in Python)
**Python**
```Python
dictionary = {
    "Dier": "Hond",
    "Voertuig": "Auto"
}
print(dictionary["Dier"]) # John
```
**Java**

Bestand: Main.java
```Java
import java.util.HashMap;
public class Main {
  public static void main(String[] args) {
    // HashMap<Key, Value>
    HashMap<String, String> dictionary = new HashMap<String, String>();
    dictionary.put("Dier", "Kat");
    dictionary.put("Voertuig", "Auto");
    System.out.println(dictionary.get("Dier")); // Kat
  }
}
```
In Java moet je het type van de key en value aangeven. Je kunt dus verschillende types als een key
gebruiken, zolang de waarde maar uniek is. Een array kan dus bijvoorbeeld ook een key zijn.

Zoals bij een array kun je in een HashMap geen verschillende types gebruiken. Als je een HashMap aanmaakt
met een value van het type `String` kun je er geen `int` in stoppen.

Als je verschillende types als waarde wilt gebruiken, omdat je bijvoorbeeld alle eigenschappen van een
persoon wilt opslaan, dan kun je beter een nieuw object aanmaken ipv een HashMap te gebruiken. Hierover
later meer.

### Methods (functies)
**Python**
```Python
def add(a, b):
    return a + b
```
**Java**
```Java
int add(int a, int b){
    return a + b;
}
```
In de basis lijk de syntax van een method in Java en Python op elkaar. Het voornaamste verschil is dat
je in Java naast de types van de parameters ook het type van de return value moet aangeve, door het
type voor de method naam te zetten.

Letop: dit is de meest simpele vorm van een method, in de praktijk kunnen de method definities er een
stuk complexer uitzien.

```Java
public static <T> int add(T a, T b) throws Exception {
    return a + b;
}
```

De method decleratie `public static final int add<T>(T a, T b) throws Exception` noemen we ookwel de
method "signature". We gaan op een later moment kijken wat al deze keywords en tekens betekenen.

### Packages & Imports (Modules in Python)
Waar je in Python je code opdeelt in modules, gebruik je in Java packages. Een package is een map waarin
meerdere classes kunnen staan. Een class is een bestand waarin je code staat.

**Python**
```Python
import random
def random_number():
    return random.randint(0, 10)
```
**Java**

Bestand: RandomNumber.java
```Java
import java.util.Random;
public class RandomNumber {
    public static int randomNumber(){
        Random rand = new Random();
        return rand.nextInt(10);
    }
}
```
In de bovenstaande java code is `java.util` de package (de map) waar de class `Random` in staat.
Alle types en objecten in Java staan in classes, en deze staan op hun beurt in packages. Dit geld ook
voor types zoals `int` en `String`. Alleen hebben de ontwerpers van Java er voor gekozen
om dit soort types met standaard methodes onder te brengen in de package `java.lang` en deze package
standaard te importeren in elke class.

### Comments
**Python**
```Python
#Single line comment

"""
Multi line comment
"""
```
**Java**
```Java
// Single line comment

/*
Multi line comment
*/
```
Er is nog een soort comment in Java, namelijk de `javadoc` comment. Dit is een comment die je boven een
class of method zet en die je kunt gebruiken om een website met documentatie te genereren.

Bestand: Main.java
```Java
/**
 * This is the Main class that puts the application together
 */
public class Main {
    /**
     * This is the main method that starts the application
     * @param args The arguments that are passed to the application
     * @throws Exception If something goes wrong
     */
    public static void main(String[] args) throws Exception {
        // does nothing yet
    }
    
    /**
     * This method adds two numbers together
     * @param a The first number
     * @param b The second number
     * @return The sum of a and b
     */
    public static int add(int a, int b){
        return a + b;
    }
}
```

### Quotes
In Python, en andere programeer talen, mag je een String declareren met enkele of dubbele quotes.
In Java maken we een onderscheid tussen "characters" en "strings". Een character is een enkele letter
die we declareren met enkele quotes. Strings declareren we met dubbele quotes.

**Python**
```Python
string = 'Hello'
character = "A"
```
**Java**
```Java
String string = "Hello";
char character = 'A';
```