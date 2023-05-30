# Lichtregulering

:::{exercise} Opdracht: bouw de lichtregulering

1. Maak een prototype voor {ref}`lichtregulering`. Ga uit van de voorbeelduitwerking het toestandsdiagram of van je eigen toestandsdiagram. Gebruik de knoppen op de micro:bit. In plaats van de lamp gebruik je de ledjes van de micro:bit. De helderheid van een pixel (LED) in het display wordt gegeven door een getal in het bereik 0..9: 0 is uit, 9 is de maximale sterkte. Onderstaand voorbeeld geedt het "Image" voor alle LEDs op halve sterkte:

```Python
leds_half = Image("55555:"
                  "55555:"
                  "55555:"
                  "55555:"
                  "55555")
```

2. Pas het prototype aan voor opdracht b). Je mag een derde knopje (knop C) toevoegen, zie Aansluiten van de drukknop. In plaats daarvan kun je ook de "shake" event gebruiken: `accelerometer.was_gesture('shake')`

Het is niet mogelijk om de kleur van de ledjes op de micro:bit te veranderen in blauw. In plaats van rood en blauw kun je kiezen om met knop C (of de shake event) te wisselen tussen twee verschillende figuren, bijvoorbeeld een hartje en een mannetje.
:::