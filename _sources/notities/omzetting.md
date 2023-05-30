# Omzetting naar JB

## Meerdere figuren naast elkaar

De eenvoudigste oplossing hiervoor is het gebruik van een grid, zie: https://sphinx-design.readthedocs.io/en/sbt-theme/

In het voorbeeld hieronder (voor 4 kolommen) hebben de onderdelen een extra `:` zodat je een figuur met `:::` zo in dit frame kunt plaatsen. Als de plaatsing uiteindelijk goed is, kun je de `:outline:` weglaten (de lijn om het blok).

```
:::::{grid} 1 2 3 4
:outline:

::::{grid-item}
A
::::
::::{grid-item}
B
::::
::::{grid-item}
C
::::
::::{grid-item}
D
::::
:::::
```

Je kunt per grid-item een figuur (figure) plaatsen of een afbeelding; bij deze laatste kun je de afmetingen niet opgeven in Markdown.

## Open punten

* hoe kan ik in JB de taal aanpassen, voor bijv. Inhoud in plaats van Contents?