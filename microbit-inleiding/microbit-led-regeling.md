# Voorbeeld: sterkte van een LED aanpassen

## Inleiding

In deze paragraaf leer je hoe je de sterkte, oftewel de lichtintensiteit, van een led kunt aanpassen. Het doel is om de lichtintensiteit van een LED aan te passen met behulp van de A-knop en de B-knop. Als de A-knop wordt ingedrukt gaat de LED feller branden. Als de B-knop wordt ingedrukt gaat de LED minder fel branden. Dat werkt op basis van pulsbreedtemodulatie (Pulse Width Modulation: PWM), ook dat zullen we toelichten.

We doorlopen de volgende stappen:

1. Aansluiten van de LED en het testen daarvan
2. Maken van een toestandsdiagram
3. Omzetten naar een programma

## Stap 1 Aansluiten van de LED

Maak de onderstaande opstelling (die is gelijk aan Voorbeeld: aansluiten LED en drukknop). Je ziet:

* De LED is aangesloten op pin 1.
* We gebruiken een weerstand van 47 Ohm om te voorkomen dat de LED (of de microbit) doorbrandt.
* De platte kant van de LED sluiten we aan op de min (0V). Je kunt ook kijken naar de pootjes van de LED: het korte pootje sluiten we aan op de min (0V).

:::{figure} figs/breadboard-led.png
:width: 600

Breadboard met LED-schakeling

:::

Test of de LED werkt, bijvoorbeeld met onderstaande programma. Dit programma laat de LED steeds met een andere sterkte branden. Daarbij is 1023 de maximale waarde.

```Python

```

:::{warning}
Let op: we gebruiken hier ‘pauzeer’ puur voor het testen. In de module leer je hoe je hiervoor een timer kunt gebruiken, zie cyclus 2 - timers.
:::

## Over PWM: Pulse With Modulation

In het voorbeeld bij stap 1 zie je al een toepassing van Pulse With Modulation (PWM). De Micro:bit kan namelijk alleen maar een spanning van 3 volt of 0 volt op de pinnen zetten. Het is niet mogelijk om bijvoorbeeld 1,5 volt op de pin te zetten en daarmee de led minder fel te laten branden. De led is dus aan (3V) of uit (0V).

Toch is er een oplossing om de LED minder fel te laten branden. De Micro:bit wisselt de spanning op de pin heel snel tussen 0V en 3V. Als de spanning voor 50% van de tijd 0 volt is, dan zal de LED maar half zo sterk branden. Als de spanning 25% van de tijd 0 volt is, en dus 75% van de tijd 3 volt, dan zal de LED op 75% sterkte branden. Je ziet niet dat de LED steeds aan en uit gaat omdat het heel snel achter elkaar gaat. Dit noemen we Pulse Width Modulation.

De figuur hieronder laat drie situaties zien. Het gemiddelde geeft aan hoe sterk de LED zal branden.

:::{figure} figs/pwm.gif
:width: 400

Pulsbreedtemodulatie (PWM) - Bron: [Wikipedia](https://nl.wikipedia.org/wiki/Pulsbreedtemodulatie)

:::

Je hoeft maar weinig te doen om PWM te gebruiken. Je gebruikt ‘schrijf analoog pin … naar …’ en de Micro:bit handelt het verder af. Als je de led op 50% gebruik je bijvoorbeeld het onderstaande blokje. De waarde is 512, omdat dat de helft is van 1023, wat het maximum is.

```Python

```

## Stap 2 Maken van een toestandsdiagram

We maken een programma met 4 toestanden.

* Toestand 1: de led is uit
* Toestand 2: de led is aan op 33% sterkte
* Toestand 3: de led is aan op 66% sterkte
* Toestand 4: de led is aan op 100% sterkte

Het toestandsdiagram ziet er dan zo uit:

:::{figure} figs/led-pwm-automaat.png
:width: 500

Toestandsdiagram voor LED sterkteregeling

:::

## Stap 3 Omzetten naar een programma

Dit was de bedoeling van ons systeem: als de A-knop op de micro:bit wordt ingedrukt gaat de LED feller branden. Als de B-knop wordt ingedrukt gaat de LED minder fel branden.

Als je met de micro:bit wilt nagaan of een knopje is gedrukt en weer losgelaten kun je het volgende commando gebruiken:

```Python

```


Daarom hebben het programma als volgt opgebouwd:

```Python

```



Test het programma. *Werkt het?*