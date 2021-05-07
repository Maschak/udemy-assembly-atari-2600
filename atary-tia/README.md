# NTSC Video Synchronisation

Es wird zwischen zwei Signalformaten unterschieden. Das Signalformat 

## Idee der Scanlines

Als Scanline wird eine Linie bezeichnet, die vom Elektronenstrahl von links nach rechts durchlaufen wird. Der Elektronenstrahl bekommt seine Instruktionen von dem TIA-Chip. Pro Scanline werden 160 sichtbare color clocks (Pixel) durchlaufen.

### TIA-Chip

TIA: [Atari Television Interface Adapter](https://de.wikipedia.org/wiki/Atari_TIA)

Die Besonderheit des TIA-Chips ist, dass er kein Video-RAM besitzt und somit kein Abbild des Frames im Speicher halten kann. Das bedeutet, dass eine Darstellung des Videosignals mit dem Prinzip der Scanlines durchgeführt werden muss. Der TIA-Chip muss für jeden Pixel neu neue Instruktionen bekommen.

Der TIA-Chip arbeitet mit 3,8 GHz. 

## Synchronisation Prozessor und Elektronenstrahl

### Horizontal Blank

Die _Horizontal Blank_ wird als die Zeit betrachtet, die der Elektronenstrahl braucht, um vom rechten Rand bis zum linken Rand zu gehen. Typischerweise wird der _Horizontal Blank_ mit 68 color clocks (pixel) angegeben. Er braucht also 68 color clocks bis er wieder am rechten Rand angekommen ist, um eine neue Scanline zu erzeugen.

      68 color clocks                   160 color clocks
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    <-----------------><----------------------------------------------------------------->
    