# Bij de inleiding

De huidige voorbeelden zijn allemaal nogal "geavanceerd", zoals domotica.
Er zijn ook veel voorbeelden van traditionele embedded systems: apparaten die bestuurd worden door een computer. Niet alles hoeft een "robot" te zijn, of een "slim systeem".

Robots en "slimme systemen" zijn wel belangrijke ontwikkelingen, en verdienen zeker om aan bod te komen. In het geval van slimme systemen speelt de communicatie via het internet ook een belangrijke (essentiële) rol: "internet of things". Die relatie mag zeker belicht worden.

(Als voorbeeld van een robot moet je dan wel een autonome robot gebruiken, geen chirurgische "robot" die op afstand bediend wordt; vgl. robot wars.) Leerlingen moeten het verschil weten tussen een autonome robot en één die bediend wordt.

Bij de voorbeelden:

* in het algemeen zijn de voorbeelden "ver van mijn bed". Ik pleit voor eenvoudiger voorbeelden die dichter bij de wereld van de leerling liggen. Hooguit een enkel geavanceerd voorbeeld - zoals een zelfrijdende auto?
* de robotchirurg lijkt mij geen goed voorbeeld (van een robot); het gaat hier niet om een autonome robot, maar om een apparaat dat op afstand bediend wordt. (In die zin is het wel OK, maar: geen "robot".)
* het weerstation lijkt mij een goed voorbeeld (maar, alleen met sensoren)

Enkele eenvoudige, klassieke voorbeelden:

* CV; wasautomaat; magnetron
* "slimme verlichting" en "slimme verwarming" (energiebesparing!)
* (zie ook het voorbeeld van de slimme bewatering)
* 

Een aantal termen/concepten moeten de leerlingen wel kennen; deze moeten we uitleggen in de inleiding, en in de glossary.

* embedded system
* real-time system

Het verhaal over sensoren en actuatoren kan compacter en meer to-the-point. Je kunt de vergelijking met zintuigen in de biologie wel maken - maar je hoeft dat niet zo uitgebreid te doen.

Belangrijke ontwikkelingen waarin physical computing een rol speelt:

* robotica (en dan in het bijzonder: autonome systemen; maar ook systemen waarin mens en machine samenwerken, vgl. de auto)
* internet of things; "slimme systemen".
    * bijzonder hieraan is dat ook dingen die gewoonlijk geen computer of besturing vereisen, ook met een computer (microcontroller) uitgerust worden; bijvoorbeeld om meer waar te kunnen nemen in de omgeving van mens (dier, plant, enz.).
    
De inleiding bevat een aantal algemene vragen; het is wellicht handig om bij elke cyclus een "reflectie-fase" te hebben.
    
## Toestandsdiagrammen

In het inleiding worden op sommige plaatsen toestandsdiagrammen gebruikt, terwijl deze pas in Cyclus 1 uitgelegd worden.


## Inleiding micro:bit

In deze inleiding komen al veel concepten aan de orde, zoals: eindige automaten (toestandsdiagrammen), PWM, servo's, motoren, enz.
Ik zou verwachten dat deze geleidelijk in Cyclus 1 aan bod komen.

Wat is het doel van de (algemen) inleiding? Mijn suggestie zou zijn: een kennismaking met Physical Computing, met het gebruikte platform, met de onderdelen (sensoren, processor, actuatoren), met de manier van werken - zonder teveel met de concepten aan de slag te gaan. Vooral: na-bouwen van (kleine) voorbeeld-projecten.
En wat is het doel van de microbit-inleiding? Kennismaking met de microbit, programmeerplatform, enkele sensoren en actuatoren (en de manier van verbinden); voornamelijk door kleine nabouw-projecten.
*Debugging*, in het bijzonder het gebruik van de seriële console, hoort ook in de inleiding thuis.

Voor het aansluiten van de verschillende onderdelen zou ik eerder een Grove-systeem gebruiken, om de drempel laag te houden. En het gebruik van servo's zonder aparte (5V?) voeding gaat vrijwel altijd mis; als het al beweegt, kun je er geen kracht mee uitoefenen.

(Een alternatief voor het Grove-systeem is het Octopus-systeem van Elecfreaks: https://www.elecfreaks.com/octopus.html; of, vergelijkbaar, het Gravity-systeem van DFRobot: https://www.dfrobot.com/gravity.html.)

In de huidige browsers kun je de microbit direct aansluiten op de editor, je hoeft dan geen code meer als bestand te laden.

In deze versie gebruiken we als programmeertaal Python, in plaats van de micro:bit blokjestaal.

## Cyclus 1

Als je als eerste context "rondom het huis" neemt, dan zijn bijvoorbeeld ook de wasautomaat, de CV, en de magnetron geschikte voorbeelden. (Dit is voor Cyclus 1?)

Eigenlijk is een "contactsensor" een betere naam dan de "aanraaksensor". (Deze laatste wordt meestal gebruikt voor "touch" sensoren.)

Een geschikt eerste voorbeeld is een schakeling met een schakelaar en een lamp. Wat is het voordeel van het gebruik van een computer tussen de schakelaar en de lamp?

* je kunt een eenvoudiger mechanische schakelaar gebruiken - zonder geheugen.
* je kunt een complexere besturing gebruiken; bijvoorbeeld met een tijds-effect (5 min. aan)
* je kunt de lamp ook op afstand bedienen.
* je kunt de lamp met een algoritme bedienen, bijvoorbeeld afhankelijk van de tijd, van de zonsondergang enz. ("slimme systemen", met een verbinding naar het internet.)
* je kunt op afstand zien of de lamp aan- of uitgezet is.
* je kunt meerdere lampen bedienen met 1 schakelaar.

## Concepten en contexten

De verschillende cycli stellen een bepaalde context centraal:

* cyclus 1: domotica, rondom het huis (mogelijk ook IoT?)
* cyclus 2: smart city (daar heb je eigenlijk ook IoT nodig?)
* cyclus 3: zelfrijdende auto's (??? of robotica, in bredere zin?) - voorbeeld: parkeersensor... dat is dan wel een slap aftreksel van de eigenlijke context.
* cyclus 4: wearables, rond het lichaam

(vooral "smart city" kan wel eens lastig worden voor leerlingen; wat zijn de voorbeelden?)

In de inleiding worden ook al veel concepten geïntroduceerd, op een wat onduidelijke manier.

Als je een context gebruikt, dan moet je die ook serieus nemen: wat zijn de uitdagingen die die context stelt? Wat zijn de randvoorwaarden? Kun je daar passende voorbeelden bij bedenken?

