# Grillige data

## Piekdetectie

Sommige sensoren geven duidelijke informatie. Een aanraaksensor geeft aan of de sensor wordt aangeraakt/ingedrukt (het resultaat is 1) of niet (het resultaat is 0). De versnellingssensor geeft echter niet direct zulke duidelijke informatie. Stel je wilt de versnellingssensor gebruiken om het aantal stappen te tellen dat iemand zet. De versnellingssensor zal echter niet het aantal stappen als output geven. De output van een versnellingssensor ziet er eerder uit zoals hieronder. De data komt van een versnellingssensor die is gebruikt bij het (hard)lopen. De data is grillig.

:::{figure} figs/grillig-signaal.png
:width: 550
:align: center

Bron: https://www.youtube.com/watch?v=wluRtoi3S9Q
:::

Je zult nu op basis van deze data moeten bepalen wanneer er een stap is gezet. Daarvoor moet je het aantal pieken in de grafiek tellen. Of beter gezegd, je moet een programma maken dat bepaalt wanneer een piek is bereikt. Dat heet ook wel ‘peak detection’. Je kunt daarvoor een threshold (drempelwaarde) gebruiken. Elke keer als de waarde van de sensor boven de threshold uitkomt wordt het aantal stappen verhoogd. Je ziet dat weergegeven in de onderstaande figuur.

:::{figure} figs/sensor-change-detection-1.png
:width: 350
:align: center

Bron: https://itp.nyu.edu/physcomp/labs/labs-arduino-digital-and-analog/lab-sensor-change-detection/
:::

:::{exercise} Toestandsdiagram om het aantal pieken te tellen

Maak een toestandsdiagram waarmee het aantal pieken wordt geteld. Op basis van zo'n toestandsdiagram kun je een stappenteller maken.

De mogelijke gebeurtenissen zijn:

* Versnelling is onder de drempel (threshold)
* Versnelling is boven de drempel (threshold)

Er is maar één mogelijke actie:

* aantal stappen += 1
:::


## Ruisdetectie

Helaas is de output die een versnellingssensor geeft niet een nette grafiek. De grafiek bevat veel ruis (engels: noise), er zitten allerlei kleine, lokale pieken tussen die niet moeten worden meegeteld. Het herkennen van de ruis wordt wel ‘noise detection’ genoemd.

:::{figure} figs/sensor-change-detection-2.png
:width: 350
:align: center

Bron: https://itp.nyu.edu/physcomp/labs/labs-arduino-digital-and-analog/lab-sensor-change-detection/
::: 


Bron: https://itp.nyu.edu/physcomp/labs/labs-arduino-digital-and-analog/lab-sensor-change-detection/

 

:::{exercise} Teken een grafiek

Teken een voorbeeld van een grafiek met een lokale piek en een threshold, waarbij het toestandsdiagram dat je eerder maakte niet goed werkt: er worden te veel pieken geteld.
:::
 
Er zijn allerlei technieken en algoritmen om zinvolle en betrouwbare informatie te kunnen halen uit dit soort data dat vol met ruis zit. Zie ook: https://itp.nyu.edu/physcomp/labs/labs-arduino-digital-and-analog/lab-sensor-change-detection/

## Toestandsdiagram met twee drempelwaarden

Om het probleem van een lokale piek op te lossen kun je werken met twee thresholds (drempelwaarden) in plaats van één. Je gebruikt dan een bovengrens en een ondergrens, zoals hieronder.

:::{figure} figs/sensor-change-detection-3.png
:width: 350
:align: center

Bron: https://itp.nyu.edu/physcomp/labs/labs-arduino-digital-and-analog/lab-sensor-change-detection/
::: 

:::{exercise} Toestandsdiagram voor twee drempelwaarden

Maak een toestandsdiagram waarmee het aantal pieken wordt geteld op basis van twee drempelwaarden.

De mogelijke gebeurtenissen zijn (je hoeft ze niet per se allemaal te gebruiken):

* Versnelling is onder de onderste drempel
* Versnelling is boven de onderste drempel
* Versnelling is onder de bovenste drempel
* Versnelling is boven de bovenste drempel

Er is maar één mogelijke actie:

* aantal stappen += 1

:::

## Oefenopdracht: stilzitalarm

:::{exercise} toestandsdiagram voor stilzitalarm

Mensen die veel achter de computer zitten bewegen tussendoor soms te weinig, en dat is slecht voor hun nek en schouders. Maak een toestandsdiagram voor een systeem met een versnellingssensor dat een signaal (bijvoorbeeld een zoemer) geeft zodra iemand te lang stil zit. Zodra die persoon in beweging komt gaat het signaal uit.

De mogelijke toestandsovergangen zijn:

* Beweging gedetecteerd (versnelling > drempelwaarde)
* Geen beweging gedetecteerd (versnelling < drempelwaarde)
* Timer loopt af

De mogelijke acties zijn:

* Start de timer 
* Zet signaal aan (zoemer)
* Zet signaal uit
:::