# Timers programmeren voor de Micro:bit

In dit deel laten we zien hoe je een timer kunt programmeren voor de Micro:bit en welke blokken je daarvoor nodig hebt. We laten de volgende onderdelen zien:

* de timer starten
* de timer loopt af
* de timer resetten
* de timer uitzetten

## De timer starten

In het [algemene deel van cyclus 2](timers-theorie) heb je kunnen zien dat je een variable nodig hebt, we noemen deze variabele: `timerEindtijd`.

Het starten van een timer met looptijd 5000 ms doe je als volgt:

```Python
timerEindtijd = ticks_add(time.ticks_ms(), 5000)

```

:::{margin}
Vergelijk met wat er met de kilometerteller van een oude auto gebeurt: deze heeft een vast aantal cijferposities, na het maximum volgt weer 0.
Of kijk wat er met een gewone digitale klok gebeurt: na 23:99 volgt 0:00.
:::

De functie `time.ticks_ms()` geeft aan hoe lang de micro:bit aan staat, in miliseconden.
Daar tel je 5000 milliseconden (= 5 seconden) bij op. De timer loopt dus over 5 seconden af.
Voor het optellen gebruik je de speciale functie `ticks_add`, in plaats van de normale Python optelling (`+`). 
De reden hiervoor is dat de ticks-teller "over de kop kan gaan": 
deze heeft een maximale waarde, daarna telt deze weer vanaf 0.

## De timer loopt af

Om na te gaan of de timer afloopt gebruik je het volgende:


```Python
if ticks_diff(timerEindtijd, time.ticks_ms()) <= 0:
    # timer afgelopen, afhandelen timer event
```

Ook hier gebruiken we weer een speciale functie: `ticks_diff()`, in verband met het rond-tellen van de `ticks`.
Er staat eigenlijk: `timerEindtijd - time.ticks_ms() <= 0` , ofwel: `timerEindtijd <= time.ticks_ms()`.
Je controleert dus of de looptijd van de Micro:bit inmiddels groter of gelijk is aan de eindtijd van de timer.
Als dat zo is, zijn de 5 seconden verstreken en loopt de timer dus af.

Een voorbeeld:

Je start de timer bij de looptijd van 12.000 milliseconden (dat is 12 seconden). De timerEindtijd wordt dan 12.000 + 5.000 = 17.000 milliseconden. Bij een looptijd van 12.500 milliseconden gaat de timer niet af, want de volgende uitdrukking is dan *NIET WAAR*:

```
    17000 - 12500 <= 0
```

Een paar seconden later is de looptijd bijvoorbeeld 17.400 milliseconden. De timer loopt dan wel af, want de volgende uitdrukking is dan *WAAR*:

```
    17000 - 17400 <= 0
```
 
## De timer resetten of herstarten

Het resetten of herstarten van een timer is hetzelfde als het starten van de timer.

## De timer uitzetten

Het uitzetten van een timer kan niet en hoeft ook niet. Als in een bepaalde toestand binnen het toestandsdiagram de timer niet belangrijk is, wordt simpelweg niet gecontroleerd of de timer afloopt. Eigenlijk is de vergelijking met de kookwekker in die zin niet helemaal goed. Een kookwekker geeft namelijk een alarm (hard piepen bijvoorbeeld) waardoor jij weet dat het tijd is om de eieren uit de pan te halen. Als je niet wilt dat het alarm afgaat moet je de kookwekker eerder uitzetten.

Bij een timer werkt dat iets anders. Het programma controleert steeds of de tijd al is verstreken. En als de timer niet meer nodig is, controleer het programma niet meer of de tijd al is verstreken.

:::{shortanswer} Timer-voorwaarde

Waarom staat er <= en niet == bij het controleren of de timer afloopt?

:::

## Meer over timers in microPython

* https://docs.micropython.org/en/latest/library/time.html

