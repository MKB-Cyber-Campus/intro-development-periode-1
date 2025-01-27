# Intellij - Deel 1
Tijdens de lessen maken we gebruik van Intellij. Dit is de meeste gebruikte IDE (Integrated Development Environment) voor Java. Intellij heeft een betaalde versie, maar er is ook een gratis versie beschikbaar (De community editie). Deze versie is voldoende voor de lessen.

Je kunt Intellij hier downloaden: https://www.jetbrains.com/idea/download/

## Code Style
Zoals veel programmeertalen kent Java meerdere code stylen. De twee voornaamste zijn die van Oracle en Google. Gezien de voorgeschreven code style van Oracle uit de jaren negentig dateert, en dus achterloop op de JDK versies, wil ik tijdens de lessen de code style van Google hanteren.

In Intellij kun je afdwingen dat code aan een code style voldoet door een style guide in te stellen.

Hoe je dat kunt doen lees je hier: https://medium.com/swlh/configuring-google-style-guide-for-java-for-intellij-c727af4ef248

## Auto Format On Save
We hebben allemaal wel eens gezien hoe onduidelijk code kan worden als het niet of incorrect geformatteerd is. Je kunt in Intellij instellen dat je code automatisch wordt geformatteerd wanneer je een bestand opslaat. Hoe je dit doet lees je hier:
https://www.jetbrains.com/help/idea/reformat-and-rearrange-code.html#reformat-on-save

## Code Completion
Intellij zal tijdens het typen suggesties laten zien van packages, classes of methods. Dit wordt Code Completion genoemd.
Code Completion kun je ook zelf oproepen door `alt + spatie` in te drukken. 

Standaard wordt er geen documentatie getoond wanneer je door de suggesties navigeert. Dit kun je aanpassen door naar `File > Settings > Editor > General > Code Completion` te gaan en daar `Show the documentation popup in` aan te vinken.

## Local History
Voor het programmeren is versiebeheer onmisbaar. Het helpt om productie code en code dat nog in ontwikkeling
is te scheiden en stelt je instaat om terug te gaan naar een vorige versie van je code. Vooral dat laatste
is erg handig. Helaas werkt dat alleen als je je code ook daadwerkelijk commit naar je versiebeheer systeem (git).

Gelukkig onthoudt IntelliJ ook de wijzigingen die je maakt in je code. Dit wordt Local History genoemd. Mocht
je perongeluk een stuk code verwijderen, en werkt `ctrl + z` niet, of heb je een bestand perongeluk verwijderd,
dan kun je via Local History je code terug halen.

Meer hierover lees je hier: https://www.jetbrains.com/help/idea/local-history.html