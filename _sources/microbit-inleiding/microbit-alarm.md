# Voorbeeld: alarm

## Samenwerkingsopdracht

Je kunt deze opdracht als een samenwerkingsopdracht doorlopen, gebaseerd op de expert-methode. Dit staat hieronder beschreven. Je kunt er ook voor kiezen om de opdracht zelfstandig of op een andere manier te maken, sla dan deze paragraaf over. Overleg met je docent.

**Opdracht: alarm maken**

Je werkt voor deze opdracht in groepjes van 3 leerlingen. Samen gaan jullie het alarm maken zoals in de volgende paragraaf staat beschreven (zie: Opdrachtomschrijving). Voordat jullie dat samen gaan doen gaat ieder van jullie zich verdiepen in een apart onderdeel. Daarna komen jullie weer samen om gezamenlijk het systeem te bouwen.

:::{exercise} Opdracht leerling 1: sluit een externe drukknop aan

Zoek één of meerdere leerlingen van andere groepjes op en zorg dat je leert hoe je een externe drukknop kunt aansluiten en gebruiken. Meer informatie vind je hier:

Stap 1: Aansluiten van de drukknop

Tip: kijk goed of je de drukknop aansluit op de 0V of 3V.

Zorg dat je:

* weet hoe je een externe drukknop kunt aansluiten
* weet hoe je een externe drukknop in een programma kunt gebruiken

:::

:::{exercise} Opdracht leerling 2: sluit een piezo-buzzer aan

Zoek één of meerdere leerlingen van andere groepjes op en zoek samen uit hoe je een piezo-buzzer kunt aansluiten en gebruiken (zie ook de Opdrachtomschrijving). Zoek hierover zelf informatie op internet. Bijvoorbeeld via: https://www.kitronik.co.uk/blog/inventors-kit-experiment-6-help

Zorg dat je weet:

* hoe je een piezo-buzzer kunt aansluiten
* hoe je een piezo-buzzer geluid kunt laten genereren.
:::

:::{exercise} Opdracht leerling 3: maak een toestandsdiagram

Zoek één of meerdere leerlingen van een andere groepjes op en maak een toestandsdiagram voor het systeem. Zie ook de opdrachtomschrijving.

:::

:::{exercise} Gezamenlijke opdracht

Leg elkaar uit wat je hebt geleerd. Bouw en programmeer vervolgens samen het alarm, zie ook de Opdrachtomschrijving hieronder.

:::

## Opdrachtomschrijving

Je docent beschikt over een uitgebreide uitwerking van deze opdracht. Samen met je docent kun je er ook voor kiezen om deze opdracht als voorbeeld te bekijken en na te maken.

Let op: dit is een uitgebreide opdracht waarbij je onder meer een timer moet gebruiken. Dit wordt uitgelegd in cyclus 2.

:::{figure} figs/microbit-alarm.jpg
:width: 250
:align: right

Smartphone alarm-app

:::

Maak een alarm, zoals dat ook op je mobiele telefoon zit, zie het plaatje hiernaast. Het systeem heeft 3 knoppen:

* Plus-knop, waarmee je het aantal seconden ophoogt.
* Min-knop, waarmee je het aantal seconden verlaagt.
* Start/reset knop, waarmee je de timer kunt starten en resetten.

Daarnaast heeft het systeem een zoemer, dat is de piezo-buzzer, zie het plaatje hieronder.

In het begin kan de gebruiker de tijd instellen met de plus-knop en de min-knop. De tijd kan natuurlijk niet lager zijn dan nul. Vervolgens wordt het alarm gestart met de start/reset-knop. De seconden tikken dan weg, bijv: 8, 7, 6, 5, enzovoort. Als het aantal seconden nul is gaat het alarm af: de zoemer gaat aan. Als de gebruiker dan weer op de start/reset-knop drukt gaat het alarm uit. De gebruiker kan tijdens het wegtikken van de seconden het alarm resetten met de start/reset-knop.

Benodigde materialen

Naast de micro:bit heb je nodig:

* een extra drukknop
* een piezo-buzzer
* een breadboard
* een breakoutboard
* draadjes om de onderdelen te verbinden


Mocht je niet over alle materialen beschikken:

Je kunt ook werken zonder breadboard en breakoutboard, in dat geval heb je draden met krokodillenbekjes nodig.
In plaats van de piezo-buzzer kun je ook een koptelefoon of oortjes gebruiken (zie afbeelding hieronder).
In plaats van een extra drukknop kun je de start/reset-knop ook nabootsen door knop A en knop B tegelijk in te drukken.



