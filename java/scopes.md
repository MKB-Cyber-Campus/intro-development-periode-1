## Scopes
In Java bevindt code zich altijd binnen code blocks. Code blocks beginnen met een `{` en eindigen
**altijd** met een `}`. Zo'n code block noemen we ook wel een "scope".

**Voor het gemak is de class decleratie uit de voorbeelden gelaten. Uiteraard moet je deze wel altijd
hebben in je code.**

```Java
public static void main(String[] args){ // method scope
  ...
}
```
### Out of scope
Alle variabelen die je binnen een scope declareert bestaan alleen maar binnen die scope. Als we aan
de main method een `if` scope toevoegen en binnen deze nieuwe scope een variabele declareren, dan
bestaat deze variabele niet buiten deze if scope.
```Java
public static void main(String[] args){ // method scope
  if(!"Hello World".isEmpty()){ // if scope
    int x = 5;
  }
  System.out.println(x);
}

output: cannot find symbol
        symbol:   variable x
```
Wanneer Java de code compileert en de `}` tegenkomt van de `if` statement, dan houdt de variabele `x` op
met bestaan. We zeggen ook wel dat hij "out of scope" is gegaan.

### Nesting
Zoals je in het voorgaande code snippet kon zien kun je dus ook scopes "nesten"; je kunt meerdere scopes binnen
elkaar hebben. Een variabel die in een buitenste scope (outer scope) is gedeclareerd, is ook beschikbaar
voor de scope daar binnen (inner scope).
```Java
public static void main(String[] args){ // method scope
  int x = 5;
  if(!"Hello World".isEmpty()){ // if scope
    x += 5; // "+=" is kort voor x = x + 5 
  }
  System.out.println(x);
}

output: 10
```
Een variabele die binnen een "inner" scope bestaat noemen we een "locale variable".

Je mag meerdere niveaus van nesting aanbrengen:
```Java
public static void main(String[] args){ // method scope
  int x = 5;
  if(!"Hello World".isEmpty()){ // if scope
    for(;x<10;x++){ // for loop scope
      if(x == 5){
        System.out.println("Wohoooo we are half way there!");
      }
    }
  }
  System.out.println(x);
}

output: Wohoooo we are half way there!
        10
```
In theorie kun je zo diep nesten als je wilt, maar in de praktijk leidt dat tot slecht leesbare code.
We streven er altijd naar om waar dat kan niet meer dan 2 scopes binnen een method te hebben; niet
meer dan twee "indentions". Wanneer er meer dan 2 indentions nodig zijn, dan is het beter om de code
op te splitsen in meerdere methoden.

Methods zullen we later behandelen.

### Variabelen met dezelfde naam
Je mag een variabel die je in een buitenste scope van een method hebt gedeclareert, niet nogmaals
declareren binnen een inner scope. Dit zal een compile error opleveren.
```Java
public static void main(String[] args){ // method scope
  int x = 5;
  if(!"Hello World".isEmpty()){ // if scope
    int x = 10;
  }
  System.out.println(x);
}

output: variable x is already defined in method main(java.lang.String[])
```
Je kunt wel een variabel opnieuw declareren die out of scope is gegaan van een "inner" scope.
```Java
public static void main(String[] args){ // method scope
  if(!"Hello World".isEmpty()){ // if scope
    int x = 10;
  }
  int x = 5;
  System.out.println(x);
}
```
`int x` is out of scope gegaan aan het einde van de `if` scope. Hij bestaat dus niet binnen de "outer"
scope. De variabel `x` die we in de "outer" scope declareren is dus een nieuwe variabel.
### Code blocken kunnen niet buiten een method scope
Je kunt geen code blocken buiten een method scope plaatsen. Code blocken dienen altijd binnen een method
te worden geplaatst. Als je bijvoorbeeld een `if` statement probeert te plaatsen buiten een method,
dan zal de compileren allemaal fouten geven.
```Java
if(true){
    System.out.println("Is altijd waar");
}
public static void main(String[] args){ // method scope
  ...
}

output: verscheidene compile errors
```
