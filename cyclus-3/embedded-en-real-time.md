# Embedded en real-time systemen

Bij physical computing spreken we vaak over *embedded systemen* en *real-time systemen*. 
Een embedded systeem is een computersysteem met een beperkte hoeveelheid functies, gemaakt voor een specifiek doel. Het computersysteem in de wasmachine is een typisch embedded systeem. Een automatisch watergeefsysteem voor planten ook. Net als het computersysteem in een zelfrijdende auto. In een magnetron zit ook een embedded systeem. En zo kunnen we nog wel even doorgaan. Kijk maar eens om je heen, grote kans dat je meerdere embedded systemen ziet.

Real-time systemen zijn systemen waarbij de correcte werking niet alleen afhangt van de functionele werking van het systeem, maar ook van de snelheid waarmee dat gebeurt. Neem bijvoorbeeld de zelfrijdende auto: als het systeem niet snel genoeg reageert op de omgeving (bijvoorbeeld een overstekend kind), dan gaat het grondig mis. Een computersysteem voor de monitoring in een kerncentrale is ook een real-time systeem: als het systeem niet snel genoeg reageert kan de nucleaire reactie uit de hand lopen en dat kan rampzalig zijn. We noemen dat ook wel hard real-time systemen. Dat zijn systemen waarbij het absoluut noodzakelijk is dat er snel genoeg wordt gereageerd. Daarnaast heb je ook soft real-time systemen. Daarbij is het belangrijk dat het systeem op tijd reageert, maar als er af- en toe vertraging is, dan leidt dat niet tot (grote) problemen. Een voorbeeld daarvan is je routenavigatiesysteem. Als het traag reageert is dat vervelend, maar als het een keer gebeurt leidt dat niet tot een groot probleem.

Hieronder zie je een indeling met enkele voorbeelden.

|          | Embedded | Niet embedded |
| :---     | :--      | :--           |
| **Hard real-time** | Systeem in een zelfrijdende auto | Systeem voor het verhandelen van aandelen op de beurs |
| **Soft real-time** | Routenavigatiesysteem | Systeem voor video-conferencing zoals Skype, geïnstalleerd op een PC |
|                    | | Programma om Netflix video’s te bekijken |
| **Niet real-time** | Plantwatergeef-systeem | Back-up programma op je PC |
|                    | Systeem voor de verwarming thuis | |
|                    | e-Reader | |
 

Je zou kunnen zeggen: een back-up programma moet toch ook niet dagen de tijd nemen en is dus real-time?! En als je uren moet wachten voordat je verwarming thuis een keer aangaat zeg je ook dat het niet goed werkt. Dat is waar, maar het geeft niet als het wat langer duurt om de backup te maken of de verwarming aanslaat. Het gaat dan om enkele minuten of zelfs uren. Bij real-time systemen gaat het echter om milliseconden, zowel bij de hard- als de soft real-time systemen.

:::{exercise} Embedded en real-time systemen

Verzin voor elke categorie nog een voorbeeld van een systeem en geef daarbij een toelichting waarom dat systeem in die categorie thuishoort.
:::