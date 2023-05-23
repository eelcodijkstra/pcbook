# Stappenteller bouwen (MB)

## Inleiding

De Micro:Bit heeft een ingebouwde versnellingssensor (zie  ook: https://microbit.org/nl/guide/features/#accel). Met zo’n versnellingssensor kun je bijvoorbeeld meten of de Micro:bit wordt geschud. Je kunt de versnelling in drie dimensies meten: de x-richting, de y-richting en de z-richting.

De eindopdracht voor deze cyclus houdt in dat je zelf een stappenteller gaat ontwikkelen. We laten zien hoe je de gegevens van de versnellingssensor kunt gebruiken. Vervolgens kun je zelf op basis van het toestandsdiagram dat je eerder maakte een stappenteller bouwen.

## Versnellingsensor in de Micro:bit

De onderstaande aanpak is gebaseerd op: https://microbit-challenges.readthedocs.io/en/latest/tutorials/accelerometer.html.

Je kunt met het volgende blokje de waarde van de versnellingssensor opvragen voor richting x, y of z ($a_x, a_y, a_z$).

De waarde van de sensor varieert tussen -2048 en 2048. Je kunt de gecombineerde versnelling van de drie assen (x, y en z) als volgt berekenen:
  
:::{math}
  a = \sqrt{ {a_x}^2 + {a_y}^2 + {a_z}^2 }
:::

De waarde van de versnelling varieert dan tussen 0 en 3547. Je kunt het volgende Micro:bit programma gebruiken om de gecombineerde versnelling te berekenen. Je ziet daarin 4 variabelen: x, y, z en versnelling. Het blokje 'square root' betekent 'wortel'.



Mocht je de seriele verbinding gebruiken om te debuggen kun je ook dit gebruiken.



Beter is nog om een aparte functie te maken voor het berekenen van de gecombineerde versnelling.



Als je Micro:bit stilhoudt, zal de versnelling rond de 1024 zijn. Dat is namelijk de zwaartekracht die wordt gemeten

## Opdracht: bouw stappenteller

:::{exercise} Bouw de stappenteller

Maak met behulp van het toestandsdiagram op basis van de twee drempelwaarden die je eerder maakte een prototype voor een stappenteller.

Bepaal zelf wat de goede waarden zijn voor de twee drempelwaarden (tresholds) door zelf te experimenteren. Bij welke waarden houdt het systeem het aantal stappen correct bij?

Je kunt het aantal stappen weergeven met de ledjes op de Micro:bit. Maak daarbij gebruik van een apart blokje, als volgt.

????

Als je het programma uitgebreider wilt testen en wilt ontkoppelen van de computer, kun je een batterijhouder met 2 AAA batterijen gebruiken, zie: Micro:bit aansluiten op een batterij.
:::


## Opdracht: bouw stilzitalarm

:::{exercise} Bouw een stilzitalarm

Maak een prototype voor een stilzitalarm op basis van het toestandsdiagram dat je eerder maakte, zie: Oefenopdracht toestandsdiagram stilzitalarm. Het systeem geeft een signaal zodra je een bepaalde tijd niet in beweging bent gekomen. Kies zelf wat je als signaal gebruikt (bijvoorbeeld een zoemer of de LED's van de Micro:bit). Zodra het systeem in beweging wordt gebracht stopt het signaal weer.

:::