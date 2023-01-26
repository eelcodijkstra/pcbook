# Correcte toestandsdiagrammen

## Tabel met alle toestandsovergangen

Voor het overzicht laten we de toestandsovergangen die naar dezelfde toestand verwijzen ook wel eens weg, zoals hieronder.

:::{figure} figs/toestandsdiagram-output.png
:width: 600

:::

Het is echter wel verstandig om goed na te denken over wat er in alle gevallen gebeurt. Bijvoorbeeld, wat gebeurt er in toestand ‘1 euro’ als de gebruiker een frisdrank selecteert? Door over alle mogelijkheden na te denken voorkom je fouten die je later veel tijd kosten om te herstellen. Je kunt dat ook in een tabel weergeven door alle toestanden te combineren met alle mogelijke toestandsovergangen. Daarbij geef je voor alle mogelijkheden aan wat de nieuwe toestand wordt.

| **Toestand**   |                |               |          |
| :--            | :--            | :--           | :--      |
|                | Inworp 50 cent | Inworp 1 euro | Selectie |
| Start: 0 euro  | 0,5 euro       |1 euro         | 0 euro   |
| 0,5 euro       | 1 euro         |               |          |
| 1 euro         |                |               |          | 
| 1,5 euro       |                |               |          | 
| 2 euro         |                |               |          | 

In de bovenstaande tabel zie je alle toestanden in de linker kolom. Je ziet ook alle mogelijke gebeurtenissen in de bovenste rij. Voor iedere combinatie moet de tabel beschrijven wat de nieuwe toestand wordt. Dit kan dus ook dezelfde toestand blijven. De tabel hierboven is nog niet volledig ingevuld.

:::{exercise} Tabel met toestanden en overgangen

Maak de tabel hierboven af.

:::


## Regels voor een toestandsdiagram

Een toestandsdiagram is gebonden aan strenge regels:

* Een toestandsdiagram bestaat uit toestanden (bollen) en toestandsovergangen (pijlen)
* Alle toestanden worden weergegeven als bollen. In de bol staat een korte beschrijving van de toestand.
* Er is altijd precies één starttoestand, die herken je aan de pijl die niet verbonden is aan een andere toestand.
* Alle toestandsovergangen worden weergegeven als een pijl, die één kant op wijst. Bij de pijl staat een korte beschrijving van de toestandsovergang.
* Een toestand kan nooit twee of meer keer dezelfde toestandsovergang hebben.
* Een toestandsovergang mag dezelfde toestand als begin en eind hebben.
* Bij een toestandsovergang mogen één of meerdere acties staan. In deze module gebruiken we steeds een dubbele punt om het onderscheid te maken tussen toestandsovergang en actie.

Je kunt toestandsdiagrammen prima op papier tekenen. Dat gaat vaak het snelst, maar pas op dat het wel leesbaar blijft. Een handige tool om toestandsdiagrammen mee te maken vind je via de volgende site:

[Finite State Machine Designer](http://madebyevan.com/fsm/)