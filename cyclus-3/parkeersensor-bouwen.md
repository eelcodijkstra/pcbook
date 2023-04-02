# Parkeersensor bouwen

## Inleiding

De eindopdracht voor deze derde cyclus is het maken van een parkeersensor voor een auto. Je gebruikt daarvoor een ultrasoonsensor en een zoemer (bijvoorbeeld een piezo buzzer).

Zodra de parkeersensor merkt dat er een object binnen een bepaalde afstand (afstand_A) is hoor je een zoemer aan en uit gaan. Als het object nog dichterbij is (afstand_B) dan gaat de zoemer sneller aan en uit.

## Opdelen in deelproblemen

Bij het maken van zo’n systeem is het handig om probleem op te delen in kleinere stukjes. Dat heeft allerlei voordelen:

* Het probleem wordt overzichtelijker en makkelijk, je probeert steeds een klein deel van het probleem op te lossen in plaats van het hele probleem in één keer aan te pakken.
* Door steeds een deelprobleem op te lossen ervaar je regelmatig een succeservaring.
* Je kunt elke deeloplossing apart testen. Als iets niet werkt, wordt het duidelijker waar het probleem precies zit.
* Je kunt het werk makkelijker verdelen binnen het team waarin je werkt.

Je kunt het probleem van de parkeersensor bijvoorbeeld opdelen in twee deelproblemen:

1. Zorg dat het systeem detecteert dat een object binnen afstand_A of afstand_B is.
2. Zorg dat het systeem een zoemer aan en uit kan zetten, met twee verschillende frequenties (langzaam piepen en snel piepen).

Vervolgens kun je die deelproblemen ook weer opdelen. Het eerste deelprobleem kun je als volgt opdelen:

1a. Zorg dat het systeem detecteert dat een object binnen afstand_A is. <br>
1b. Zorg dat het systeem detecteert dat een object binnen afstand_A of afstand_B is.

Het tweede deelprobleem:

2a. Zorg dat het systeem een zoemer aan en uit kan zetten (bijvoorbeeld met 1 seconde pauze) <br>
2b. Zorg dat het systeem een zoemer aan en uit kan zetten (bijvoorbeeld met 1 seconde pauze, maar ook met 0,5 seconde pauze).

In de rest van dit hoofdstuk ga je de toestandsdiagrammen ontwerpen voor deze deelproblemen. Het daadwerkelijke bouwen van de parkeersensor staat beschreven in het platformafhankelijke deel (Micro:bit, Arduino, Lego Mindstorms). Toch is het verstandig om eerst een deelprobleem helemaal uit te werken en te testen, en pas daarna verder te gaan het volgende toestandsdiagram. Het is dus goed om na het maken van een eerste toestandsdiagram (bijvoorbeeld voor deelprobleem 1a) dit uit te werken op bijvoorbeeld de Micro:bit. Als dat lukt, ga je verder met het toestandsdiagram voor deelprobleem 1b.

## Samenwerkingsopdracht

Verdeel de taken in je team. De ene taak is om deelprobleem 1 aan te pakken, de andere taak is om deelprobleem 2 aan te pakken. In de volgende paragraaf [](samenvoegen-label) geven we aanwijzingen voor het samenvoegen van de twee systemen.

:::{exercise} Deelprobleem 1

De uitdaging is:

Zorg dat het systeem detecteert dat een object binnen afstand_A of afstand_B is.

a. Zorg dat het systeem detecteert dat een object binnen afstand_A is. <br>
b. Zorg dat het systeem detecteert dat een object binnen afstand_A of afstand_B is.

Maak eerst een toestandsdiagram voor deelprobleem a en bouw dit systeem. Maak gebruik van een ultrasoonsensor (zie voor meer informatie hierover het platformafhankelijke deel: Micro:bit, Arduino of Lego Mindstorms). Breid het systeem daarna uit voor deelprobleem b.

Voor het toestandsdiagram heb je de volgende toestandsovergangen:

* geen object
* object binnen afstand_A (bijvoorbeeld binnen 30 cm)
* object binnen afstand_B (bijvoorbeeld binnen 20 cm)

Als acties kun je voorlopig gebruiken:

* geef melding A
* geef melding B
 
:::

:::{exercise} Deelprobleem 2

De uitdaging is:

Zorg dat het systeem een zoemer aan en uit kan zetten, met twee verschillende frequenties (langzaam piepen en snel piepen).

a. Zorg dat het systeem een zoemer aan en uit kan zetten (bijvoorbeeld met 1 seconde pauze) <br>
b. Zorg dat het systeem een zoemer aan en uit kan zetten (bijvoorbeeld met 1 seconde pauze, maar ook met 0,5 seconde pauze).

Maak eerst een toestandsdiagram voor deelprobleem a en bouw dit systeem. Maak gebruik van een piezo buzzer (zie voor meer informatie hierover het platformafhankelijke deel: Micro:bit, Arduino of Lego Mindstorms). Breid het systeem daarna uit voor deelprobleem b.

Voor het toestandsdiagram heb je de volgende toestandsovergangen:

* object binnen afstand_A (gesimuleerd met knop A die wordt ingedrukt)
* object binnen afstand_B (gesimuleerd met knop B die wordt ingedrukt)
* geen object (gesimuleerd met geen van de knoppen ingedrukt)
* de timer loopt af

Als acties kun je voorlopig gebruiken:

* zet zoemer aan
* zet zoemer uit
* start de timer / reset de timer

:::

(samenvoegen-label)=
## Samenvoegen van de toestandsdiagrammen

Voor de parkeersensor zijn de twee deelproblemen apart opgelost. Dat is mooi, het werk kon binnen het team worden verdeeld, daardoor gaat het twee keer zo snel. Nu moet je echter nog de twee systemen samenvoegen tot één systeem. Daarvoor moet je eerst de toestandsdiagrammen samenvoegen, daarvoor zijn grofweg twee manieren:

Maak een nieuw toestandsdiagram waarin de beide toestandsdiagrammen worden samengevoegd. Het kan zijn dat je veel meer toestanden nodig hebt dan daarvoor omdat ze worden gecombineerd. Het is helaas vaak niet mogelijk om ze simpelweg aan aan elkaar te plakken.
Je kunt de toestandsdiagrammen ook gescheiden houden en werken met signalen. Dat gaat als volgt.
Vanuit het ene toestandsdiagram voeg je één of meerdere acties toe, zoals:

`verstuur signaal 'zoemerAan'`

In het andere toestandsdiagram kan dit een toestandsovergang zijn

`ontvang signaal 'zoemerAan'`

Door te werken met signalen hoef je vaak niet zo veel te veranderen aan de beide toestandsdiagrammen (behalve de signalen toevoegen natuurlijk). Het hangt van de situatie af welke van de twee bovenstaande oplossingen het makkelijkste is. Het belangrijkste is dat je het nieuw toestandsdiagram goed controleert voordat je gaat programmeren.

 

:::{exercise} Samenvoegen van de toestandsdiagrammen

Voeg nu beide toestandsdiagrammen samen. Je mag zelf kiezen of je werkt met signalen of niet. Controleer het nieuwe toestandsdiagram goed.

:::