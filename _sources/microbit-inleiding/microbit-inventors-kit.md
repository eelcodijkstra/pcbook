# Uitvinderskit

Als je externe sensoren gaat aansluiten raden we aan dat je een breadboard en breakout board gebruikt. Die zijn onderdeel van de uitvinderskit van Kitronik. Zonder te solderen kan je alles aansluiten op de Micro:Bit. In de uitvinderskit zit een handleiding, waarin stap voor stap wordt uitgelegd (in het Engels) hoe de Micro:Bit gebruikt kan worden. In het onderstaande filmpje wordt een introductie gegeven van de uitvinderskit en de Micro:bit.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lmdzM74XyHw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

:::{figure} figs/kitronik-inventors-kit.jpg
:width: 600

Kitronic Breadboard en Breakoutboard

:::


Op de eerste pagina van de handleiding die bij de uitvinderskit wordt meegeleverd staat beschreven hoe je deze onderdelen aan elkaar koppelt. Zie ook: https://www.kitronik.co.uk/pdf/5609_prototyping_system_for_the_bbc_micro_bit_assembly_instructions.pdf.

## Breakoutboard

Met behulp van het breakoutboard kun je makkelijk verbindingen maken met alle pinnen van de Micro:bit. Hieronder vind je een filmpje waarin de presentator uitlegt waarom het handig is om het breakout board te gebruiken.

<iframe width="560" height="315" src="https://www.youtube.com/embed/bzm4zepbGAc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Het overzicht van de pinnen helpt bij het aansluiten van sensoren via het breakout board. Dit overzicht is ook te vinden op de achterkant van de handleiding van de uitvinderskit.

## Breadboard

Ondanks dat de Micro:Bit al allerlei sensoren heeft, zal je waarschijnlijk ook andere dingen op de Micro:Bit willen aansluiten. Die dingen kunnen van alles zijn: extra lampjes, extra knoppen, sensoren, etc. Zeker als we het hebben over een proefopstelling is het erg gemakkelijk om daar een zogenaamd breadboard voor te gebruiken.

Een breadboard is een bordje met gaatjes waar je draadjes en andere onderdelen in kunt steken en zo verbindingen kunt maken.

:::{figure} figs/breadboard.jpg
:width: 300

Breadboard

:::



De 5 horizontale gaatjes zijn steeds met elkaar verbonden. Bijvoorbeeld: de gaatjes van rij 5 met de letters F G H I J zijn met elkaar verbonden. Steek je dus een draadje in J5 en een pootje van een led in G5 dan zijn die twee met elkaar verbonden. Maar dus niet met een ander onderdeel dat je in D5 hebt gestoken.

De rode en blauwe lijnen zijn bedoeld om daar 3V (de rode lijn, de +) en GND (de blauwe lijn, de -) op aan te sluiten. In de voorbeelden verderop in de module zul je zien hoe je gebruikt kunt maken van het breadboard.

Meer achtergrond over het breadboard vind je op de [site van Sparkfun](https://learn.sparkfun.com/tutorials/how-to-use-a-breadboard).

## Aansluiten met krokodillebekken

Je hoeft niet per se gebruik te maken van het breakoutboard en het breadboard. Je kunt ook werken met draden met zogenaamde krokodillebekjes. Hieronder zie je een voorbeeld van het gebruik daarvan in een opstelling voor het meten van de vochtigheid van aarde. Zie ook: https://makecode.microbit.org/projects/soil-moisture.

:::{figure} figs/microbit-krokodillenklemmen.jpg
:width: 400

Gebruik van krokodillebekjes 

:::


Het nadeel van het gebruik van deze krokodillebekjes is dat je alleen maar de pinnen 0, 1 en 2 kunt gebruiken, naast 3V en GND. Als je meerdere sensoren en/of actuatoren wilt aansluiten kom je dan wellicht tekort.