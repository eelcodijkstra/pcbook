# Kwaliteit van systemen

## Tijdigheid en betrouwbaarheid

Je kunt de kwaliteit van een physical computing systeem bepalen aan de hand van allerlei criteria. Functionaliteit is een kenmerk van alle computersystemen: wat kan het wel en wat kan het niet? Hieronder staan naast functionaliteit nog twee criteria die je in deze module moet kunnen gebruiken.

Tijdigheid: reageert het systeem snel genoeg op veranderingen in de omgeving? Met name voor real-time systemen is dat belangrijk.
Betrouwbaarheid: in hoeverre werkt het systeem in alle omstandigheden? Bijvoorbeeld onder verschillende weersomstandigheden, zowel in het licht als het donker, etc.

|             | Tijdigheid | Betrouwbaarheid |
| :--         | :--        | :--             |
| Stofzuigerrobot | De robot moet snel genoeg kunnen reageren zodat de robot niet tegen een obstakel aan rijdt of van de trap valt. In die zin is de stofzuigerrobot een real-time systeem. | Werkt de stofzuigerrobot voor alle soorten tapijt en ondergrond? |
| Anti-inbraaksysteem | Een anti-inbraaksysteem is geen real-time systeem omdat het niet binnen milliseconden hoeft te reageren. Het systeem moet echter wel binnen enkele seconden een signaal kunnen afgeven als een inbraak wordt gedetecteerd. | In hoeverre is het systeem te omzeilen door een inbreker? Werkt het systeem zowel overdag als ‘s nachts? |
| Een zelfrijdende auto | Dit is een hard real-time system. Het systeem moet binnen enkele milliseconden reageren op veranderingen, zoals overstekende mensen, andere auto’s die remmen, etc. | Werkt het systeem onder alle omstandigheden? Overdag en ‘s nachts? In de stad en op de snelweg? Bij regen, sneeuw, mist? Herkent het systeem alle mogelijke obstakels? Mensen in een witte jas tegen een witte achtergrond bijvoorbeeld? Enzovoort. |
 

Er zijn nog veel meer kwaliteitscriteria te bedenken voor een systeem zoals veiligheid, gebruikersgemak, robuustheid, energieverbruik, prijs, etc, maar daar gaan we hier verder niet op in.

:::{exercise} Beschrijf eisen

Kies één van onderstaande systemen en beschrijf de eisen die je er aan zou stellen. Maak in ieder geval gebruik van de criteria functionaliteit, tijdigheid en betrouwbaarheid.

* Een automatisch plantwatergeefsysteem
* Een toegangssluis bestaande uit twee automatische schuifdeuren (de deuren mogen nooit tegelijk open zijn om tocht te voorkomen).
* Een robotchirurg (zie: https://www.1limburg.nl/opereren-met-robots-gaat-grote-vlucht-nemen)

:::

## Kwaliteit van sensoren

De kwaliteit van een systeem hangt mede af van de kwaliteit van de sensoren die worden gebruikt. Voordat je bepaalt welke sensor je gaat gebruiken voor een toepassing doe je er goed aan te kijken naar de kwaliteit van de sensor. Je kunt dan onder meer kijken naar:

* Bereik: hoe ruim meet de sensor? Bijvoorbeeld bij een afstandssensor: op welke afstand en onder welke hoek worden objecten gedetecteerd?
* Nauwkeurigheid: hoe groot is de foutmarge van de sensor?
 

|                  | Bereik | Nauwkeurigheid |
| :--              | :--    | :--            |
|Temperatuursensor | Tot welke minimum- en maximumtemperaturen werkt de sensor? | Hoe nauwkeurig wordt de temperatuur gemeten? |
|Afstandssensor    | Tot hoe ver en hoe dichtbij worden objecten gedetecteerd? En onder welke hoek? | Hoe nauwkeurig is de sensor in het bepalen van de afstand tot het object? |
|Kleurensensor     | Welke verschillende kleuren detecteert de sensor? En hoe bepalend is de lichtinval daarbij? | Hoe nauwkeurig maakt de sensor onderscheid in verschillende kleuren? |
|Geluidssensor     | Vanaf en tot welke geluidsintensiteit registreert de sensor? En welke geluidsfrequenties? | Hoe nauwkeurig geeft de sensor de intensiteit en frequentie van het geluid weer? |
 

Je kunt allerlei andere criteria benoemen voor sensoren zoals energieverbruik, prijs, etc. Die laten we hier echter buiten beschouwing. Informatie over bereik en nauwkeurigheid is vaak te vinden in de datasheet van een sensor, zie ook **Cyclus 2 - {ref}`datasheets-label`**.
