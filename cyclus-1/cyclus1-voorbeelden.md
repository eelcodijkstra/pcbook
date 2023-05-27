# Voorbeelden

## Inleiding

In dit deel vind je enkele voorbeelden, deels uitgewerkt, en deels zijn het opdrachten. Deze helpen om toestandsdiagrammen te begrijpen en te oefenen met het maken van toestandsdiagrammen. Kies zelf welke je interessant vindt.

(lichtregulering)=
## Voorbeeld: lichtregulering

In dit voorbeeld gaat het om een systeem waarmee je de intensiteit van een lamp kunt reguleren. Het systeem bestaat uit een lamp en twee knoppen.

De lamp kan in drie standen worden gezet:

* Uit (geen licht)
* Half aan (zacht licht)
* Helemaal aan (fel licht)

Het systeem heeft twee knoppen zonder toggle-functie (A en B). Met knop A gaat de lamp feller branden. Bijvoorbeeld: als de lamp half aan is en knop A wordt ingedrukt, dan gaat de lamp helemaal aan. Met knop B gaat de lamp minder fel branden. De lamp is altijd in één van de drie bovengenoemde standen.

:::{exercise} Maak toestandsdiagram lichtregulering

(a) Maak een toestandsdiagram voor dit systeem. In de volgende paragraaf wordt dit uitgewerkt, probeer het echter eerst zelf.

(b) Het systeem wordt verder uitgebreid. De lamp heeft twee kleuren (rood en blauw). Er wordt een derde knop (C) toegevoegd waarmee kan worden gewisseld tussen de kleur rood en de kleur blauw. Pas het toestandsdiagram hierop aan.

:::

## Uitwerking opdracht (a)

Hieronder volgt een mogelijke uitwerking van opdracht (a) over de lichtregulering.

Het begint met het proberen te bepalen welke toestanden er zijn. In de opdrachtomschrijving staat dat de lamp in drie standen kan staan. Het ligt voor de hand dat we die gebruiken voor de toestanden:

* Lamp is uit
* Lamp is half aan
* Lamp is helemaal aan

Die toestanden kunnen we vast tekenen, als drie bollen

:::{figure} figs/toestandsdiagram-1-stap1.png
:width: 600

:::

Belangrijk om te weten is welke gebeurtenissen (events) er zijn, op basis daarvan kun je de toestandsovergangen bepalen. Als je de tekst van de opdracht leest blijkt dat er twee knoppen zijn. Dat zijn de gebeurtenissen, er zijn er dus twee:

* knop A wordt ingedrukt (en weer losgelaten)
* knop B wordt ingedrukt (en weer losgelaten)

Voor elke toestand (dat zijn er drie) en elke gebeurtenis (dat zijn er twee) kunnen we bepalen wat de toestandsovergang wordt (3 x 2 = 6). Elke toestandsovergang teken je als een pijl. Dan krijg je zoiets als hieronder.

:::{figure} figs/toestandsdiagram-1-stap2.png
:width: 600

:::

A betekent: knop A wordt ingedrukt, B betekent: knop B wordt ingedrukt.

Nu moeten de (uitvoer)acties er nog bij. Bijvoorbeeld, wat moet er gebeuren als de lamp in toestand 2 is en op knop B wordt gedrukt? Dan moet de lamp uit gaan. Een actie zet je altijd bij een toestands*overgang* (dus niet bij een toestand). Je krijgt dan dit:

:::{figure} figs/toestandsdiagram-1-stap3.png
:width: 600

:::

Je ziet, niet bij iedere toestandsovergang hoeft een actie te staan.

We zijn nog niet helemaal klaar, begintoestand moet er bij. Dat is de initiele toestand waar het systeem in begint. Het lijkt logisch dat de lamp eerst uit is, we kiezen daarom toestand 1 als begintoestand. En om het toestandsdiagram overzichtelijk te houden, laten we de toestandsovergangen die naar zichzelf verwijzen en geen actie hebben weg. Dan krijg je dit.

:::{figure} figs/toestandsdiagram-1-stap4.png
:width: 600

:::

We houden de teksten kort in het diagram om het overzichtelijk te houden. Het nadeel is dat misschien niet helemaal helder is wat er wordt bedoeld. Bijvoorbeeld, de pijl van toestand 1 naar toestand 2 waar bij staat A: lamp half aan zou beter kunnen zeggen:

    (gebeurtenis) knop A wordt ingedrukt -> (actie) zet de lamp met halve intensiteit aan.

Je kunt het toestandsdiagram voor jezelf testen en daarmee controleren of het klopt. Bijvoorbeeld, wat gebeurt er is als ik op A, B en dan weer B druk? Klopt dit met wat het systeem zou moeten doen?

Probeer nu eerst zelf opdracht 2) te doen voordat je de uitwerking bekijkt.

## Uitwerking opdracht (b)

Hieronder volgt een mogelijke uitwerking van opdracht b) over de lichtregulering.

De eerste vraag die je jezelf moet stellen is: welke toestanden herken ik? De lamp kent nu naast de drie standen (uit, half aan, fel) ook nog de mogelijkheid voor twee kleuren (rood en blauw). Hoeveel toestanden zijn er dan? Het lijkt er op dat dat er zes zijn, namelijk 3 standen x 2 kleuren:

* Lamp is uit / rood
* Lamp is half aan / rood
* Lamp is helemaal aan / rood
* Lamp is uit / blauw
* Lamp is half aan / blauw
* Lamp is helemaal aan / blauw

Laten we proberen het toestandsdiagram uit a) uit te breiden. We laten de acties nog even weg.

:::{figure} figs/toestandsdiagram-b-stap1.png
:width: 600

:::

Wat zijn de mogelijke gebeurtenissen? Er zijn nu drie knoppen, dus drie gebeurtenissen:

* knop A wordt ingedrukt
* knop B wordt ingedrukt
* knop C wordt ingedrukt

Dat betekent dat er mogelijk 6 (toestanden) x 3 (gebeurtenissen) = 18 mogelijke toestandsovergangen zijn. Nu kun je gaan kijken wat die toestandsovergangen precies zijn en ze als een pijl gaan tekenen. Eerst maar eens kijken wat er moet gebeuren als knop C wordt ingedrukt voor ieder van de toestanden.

:::{figure} figs/toestandsdiagram-b-stap2.png
:width: 600

:::

Dan zijn we er nog niet, want we moeten ook duidelijk maken wat er gebeurt als knop A of B wordt ingedrukt als het systeem in toestand 4, 5 of 6 is.

:::{figure} figs/toestandsdiagram-b-stap3.png
:width: 600

:::

Vervolgens moeten de acties erbij, dat doen we hieronder, weliswaar in het kort, anders wordt het onoverzichtelijk.

:::{figure} figs/toestandsdiagram-b-stap4.png
:width: 600

:::

Het nadeel van korte teksten is dat het misschien niet helemaal helder is wat er moet gebeuren. Bijvoorbeeld, de pijl van toestand 2 naar toestand 5 waar bij staat C: blauw, zou beter kunnen zeggen:

(gebeurtenis) knop C wordt ingedrukt : (actie) zet het rode licht uit en zet het blauw licht half aan

 

Nog een voorbeeld: de pijl van toestand 1 naar toestand 2 waar bij staat A: 50% rood, zou beter kunnen zeggen:

(gebeurtenis) knop A wordt ingedrukt : (actie) zet het rode licht half aan

 

Een begintoestand hadden we al, dus dit zou het moeten zijn. Test je toestandsdiagram vervolgens voor jezelf. Wat gebeurt er bijvoorbeeld als je de knoppen C, dan A, dan C, dan A indrukt? En klopt dat met wat je verwacht dat het zou moeten doen?

:::{shortanswer} Geen acties bij toestandsovergangen

Aan de linkerkant van het toestandsdiagram staan twee toestandsovergangen zonder actie:

* van toestand 1 naar 4 (knop C wordt ingedrukt)
* van toestand 4 naar 1 (knop C wordt ingedrukt)

Waarom staat hier geen actie bij?

:::

## Voorbeeld: Tamagotchi

*Dit is gebaseerd op Micro:bit Challenge opdrachten en materiaal van Renske Weeda.*

Een virtueel huisdier is elektronisch apparaatje dat je kunt ‘opvoeden’. Kijk maar eens naar het artikel over Tamagotchi’s.


(zie bijvoorbeeld: https://www.ad.nl/economie/huisdier-in-een-ei-de-tamagotchi-is-terug~a168289a/)
 

Het doel is nu om zo’n virtueel huisdier te maken. Eerst maak je één of meerdere toestandsdiagrammen. Daarna kun je het ook zelf gaan implementeren, bijvoorbeeld met behulp van de Micro:bit.

We beginnen met een eenvoudig variant.

:::{figure} figs/toestandsdiagram-tamagotchi-1.png
:width: 600

:::

Ons huisdier is in eerste instantie blij, dat is de begintoestand. Als hij wordt geknepen, wordt ie verdrietig. Als je ‘m daarna weer aait, wordt ie weer blij. Dit toestandsdiagram kent de volgende toestandsovergangen:

* Wordt geknepen
* Wordt geaaid

::::{exercise} Tamagotchi

(a) We gaan de tamagotchi verder uitbreiden. Het virutele huisdier kan boos worden als je hem duwt. Als je ‘m dan weer aait wordt ie weer blij. Of als je ‘m knijpt wordt ie verdrietig. We hebben vast een start gemaakt met het toestandsdiagram. Vul de juiste woorden in op de stippellijnen. Er ontbreken ook nog twee toestandsovergangen (twee pijlen dus), voeg die toe.

:::{figure} figs/toestandsdiagram-tamagotchi-2.png
:width: 600

:::

(b) Maak een geheel nieuw toestandsdiagram voor het volgende virtuele huisdier. Standaard is het huisdier blij. Door te duwen wordt hij boos, door de aaien wordt hij blij. Als het donker is gaat hij slapen. Als het licht is wordt hij (blij) wakker. Als hij slaapt heeft duwen en aaien geen effect.

(c) Pas het vorige huisdier aan: het huisdier wordt wakker in dezelfde toestand als hij ging slapen. Dus als hij boos was en ging slapen omdat het donker werd, wordt hij ook weer boos wakker.

::::

(voorbeeld-valdetectie)=
## Voorbeeld: valdetectie

Helaas komt het wel eens voor. Een oudere man of vrouw, alleen thuis, valt van de trap, breekt iets en kan niet meer opstaan of bewegen. De man of vrouw moet blijven liggen en hopen dat er iemand langskomt om te helpen.

Het doel is om een horloge te ontwikkelen dat kan detecteren of iemand valt. Als degene die het horloge draagt valt, wordt dat geregistreerd met behulp van een versnellingssensor (zie ook cyclus 4 van deze module). Vervolgens kan het horloge een bericht versturen naar iemand die in de buurt woon, misschien een zoon of dochter. De houder van het horloge kan ook op de reset-knop drukken om te laten weten dat alles ok is.

De gebeurtenissen zijn:

* gevallen
* reset-knop ingedrukt

:::{figure} figs/toestandsdiagram-valdetectie-1.png
:width: 600

:::

* Toestand 1 betekent: niks aan de hand
* Toestand 2 betekent: persoon is gevallen

Voor de ontvanger van het signaal kun je ook een toestandsdiagram maken. Dit kan bijvoorbeeld op een mobiele telefoon of op een horloge. De gebeurtenissen daar zijn:

* signaal "gevallen" ontvangen
* signaal "ok" ontvangen
* reset-knop ingedrukt
 
:::{figure} figs/toestandsdiagram-valdetectie-2.png
:width: 600

:::


* Toestand 1 betekent: geen alarm
* Toestand 2 betekent: alarm aan

In het deel over de Micro:bit laten we zien hoe je hiervoor een prototype kunt maken met behulp van radiosignalen.