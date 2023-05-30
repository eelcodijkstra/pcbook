# Debuggen met een seriële verbinding

Bij het maken van een programma kun je informatie via de ledjes van de micro:bit laten zien. 
Je kunt bijvoorbeeld de waarde van een sensor tonen via de ledjes. 
Een nadeel van deze manier van testen is dat het blokje om de ledjes op de micro:bit aan te passen relatief veel processortijd kost. 
Je ziet daardoor minder goed wat er precies gebeurt.
Ook is de tekst vaak minder goed leesbaar.

Een alternatief is gebruik te maken van een seriële verbinding.
Dit kan eenvoudig via de Python online editor, **als je een recente Chrome of Edge browser gebruikt**.

> Een alternatief is het gebruik van een desktop-editor zoals Mu of Thonny. Voor het installeren daarvan moet je wel voldoende rechten hebben.

* zorg dat je micro:bit via USB is aangesloten op je computer
* zorg dat de Python online editor in de browser geopend is
* je maakt verbinding met je micro:bit door te klikken op de verticale `...` naast de paarse knop "Send to micro:bit"; klik op "Connect" en volg de aanwijzingen.
* als dat gelukt is, zie je onder de programmatekst een zwart venster; dit kun je verbergen met "Hide serial" of tonen met "Show serial". Je kunt dit venster groter maken door de bovenkant naar boven te trekken, en door de zijbalken links en rechts in te klappen.
* als je net nieuwe code op de micro:bit geladen hebt, is de "serial" verbinding nog aanwezig; de "Connect" is dan niet nodig.

In het zwarte "serial" venster krijg je de uitvoer van de `print`-opdrachten in je Python-programma te zien.

:::{figure} figs/microbit-serial-display.png
:width: 700

Print-uitvoer via het "serial" deelvenster

:::


Ook in de micro:bit-simulator van de online editor vind je zo'n serial venster voor de print-uitvoer.