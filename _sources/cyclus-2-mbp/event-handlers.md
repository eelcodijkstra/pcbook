# Verdieping: events en event-handlers

(In micro:bit Python zijn er geen ingebouwde event-handlers, zoals bij de MakeCode blokjes. Dit betekent dat we de code voor het detecteren van de events zelf moeten programmeren, als onderdeel van de hoofdlus.)

Voor de input van een button bestaan er in micro:bit Python twee functies:

* `button.was_pressed()`
* `button.is_pressed()`

De functie `button.is_pressed()` geeft de actuele toestand van de button aan op het moment van deze test.
Deze functie geeft op elk moment weer wat de toestand van de button is:
dit is het *signaal* van de button.

De functie `button.was_pressed()` geeft aan of de button sinds de vorige aanroep van deze functie ingedrukt is geweest. Deze functie detecteert de *event* van het indrukken van een button.

De "trigger" voor een toestandsovergang is altijd een *event*.
Bij het omzetten van een toestandsdiagram naar een programma gebruiken we dan ook altijd de event-detectie-functies, zoals `button.was_pressed()`, of `accelerometer.was_gesture('shake')`.


De hoofdlus van een Python-programma voor de microbit heeft de volgende structuur:

```Python
while True:
    if "event A detected":
        handle_event_a()
    elif "event B detected":
        handle_event_b()
    elif "event C detected":
        handle_event_c()
    ...    
       
```

Met andere woorden: in de hoofdlus staat vooral code voor het detecteren van events, zoals het indrukken van een knop (`button.was_pressed()`), of het aflopen van een timer.
De code voor het afhandelen van een event kun je in de hoofdlus uitschrijven, als deze kort is.
Vaak is het handiger om de code voor het afhandelen van een event in een aparte functie onder te brengen.


