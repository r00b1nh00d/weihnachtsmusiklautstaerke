# Die Lautstärke der Weihnachtsmusik testen
## ~avatar avatar @unplugged
![Anzeige](https://github.com/r00b1nh00d/weihnachtsmusiklautstaerke/blob/master/Laust%C3%A4rkeAnzeigen.gif?raw=true) <br>
Wie laut ist deine Weihnachtsmusik? <br>
Du kannst mit dem Calliope die Lautstärke messen und sie dir am Computer oder dem Bildschirm des Calliope anzeigen lassen.

## Schritt 1
Ist der Calliope an deinem Computer via USB angeschlossen, kannst du dir die ``||input:Lautstärke||`` mit dem Block ``||serial: seriell Zeile ausgeben||`` am Computer anzeigen lassen (diesen Block findest du unten im fortgeschrittenen Bereich). 

```blocks
basic.forever(function () {
    serial.writeLine("" + input.soundLevel())
    basic.pause(10)
})
```

## ~@unplugged 
Um dir die Lautstärke am Computer ausgeben zu lassen brauchst, du ein Programm wie [Putty](https://www.putty.org/). <br>
![puttyNutzen](https://github.com/r00b1nh00d/mandarinenklavier/blob/master/Puttynutzen.png?raw=true) <br>
Öffne das Programm Putty. Dort musst du zuerst "Serial" auswählen. Anschließend musst du im Gerätemanager schauen, an welchem COM-Anschluss dein Calliope angeschlossen ist. Bei mir war es der Port COM4. Den Gerätemanager erreichst du z.B. mit Rechtsklick auf das Windows-Symbol (unten links im Bild). Als Übertragungsgeschwindigkeit musst du für den Calliope noch die 115220 einstellen. Nachdem du bei Putty auf Open geklickt hast, öffnet sich ein Fenster mit schwarzem Hintergrund. Dort sollten dir jetzt nach einem Drücken der Taste "A" die Werte angezeigt werden.



## Schritt 2
Wie schon gesagt, kannst du dir die ``||input:Lautstärke||`` auch direkt am Calliope anzeigen lassen. Dafür gibt es im Bereich ``||leds:LED||`` den block ``||leds:zeichne Säulendiagramm||``.    


basic.forever(function () {
     led.plotBarGraph(
   input.soundLevel() * 10,
    255
    )
    basic.pause(10)
})
