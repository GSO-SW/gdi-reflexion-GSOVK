# GDI+
Eine Sammlung von Tipps und Tricks zum Thema Grafikprogrammierung mit GDI+.

## Klassen / Ereignisse
### Timer
Ein Timer führt in regelmäßigen `Intervalen` ein `Tick`-Event aus. Der [`System.Windows.Forms.Timer`](https://learn.microsoft.com/de-de/dotnet/api/system.windows.forms.timer?view=windowsdesktop-8.0&viewFallbackFrom=net-6.0) kann über die Toolbox auf die GUI gezogen werden. 

Anschließend können wir 
- die Zeit zwischen jedem `Tick`-Event einstellen (`+ Interval { get; set; }: int`) und
- den Timer starten (`+ Start():void`) oder
- stoppen (`+ Stop():void`) oder
- den Zustand abfragen. (`+ Enabled{ get; set; }: bool`) (Standard ist ausgeschaltet: `enabled = false`)

```c#
// change tick event
tmrGameTick.Tick += new System.EventHandler(this.tmrGameTick_Tick);

// change interval (in ms)
tmrGameTick.Interval = 10;

// enable or disable timer
tmrGameTick.Start();
tmrGameTick.Stop();
// is the same as
tmrGameTick.Enabled = true;
tmrGameTick.Enabled = false;
```

## Tipps und Tricks
Ergänzen Sie hier die notwendigen Code-Ausschnitte, um zu zeigen, wie man es macht. 
- Sie können [CodeBlöcke mit Syntax-Highlighting](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) einsetzen
- Wird es zu unübersichtlich? Sie können auch Unterordner mit Beispiel-Code anlegen und auf die entsprechenden Dateien verlinken. [Inspiration](https://github.com/gsoTH/flaskShowcase/tree/master/datenbanken).
- Die folgende Liste kann gerne ergänzt werden :)

### Bewegung animieren
Bewegung oder Animation ist nur die Änderung der Figur/Position in bestimmten Zeitabständen.

d.h. einfach in bestimmten Zeitabständen (z.B. im Tick Event) die Position ändern.
```c#
// example:
// every 0.1 seconds, the object moves to the left, making it appear to move.
while (this.Position.X > 0) {
    this.Position.X -= 100;
    Thread.Sleep(100);
    this.Refresh();
}
```
### Objekte mit Tasten steuern
Es ist möglich Objekte mit Tasten zu steuern
- Zuerst müssen wir ein `Ereigniss` ausführen, wenn eine Taste gedrückt wird. Dies ist mit dem `KeyDown` Event möglich, das unter den `Ereignissen` zu finden ist.
- In der generierten Methode wird dann abgefragt, ob die gewünschte Taste gedrückt wurde.
```c#
// check that the up arrow key has been pressed and move up
if (e.KeyCode == Keys.Up ) {
    this.Position.Y += 100;
}
// Check that the down arrow key has been pressed and move down
if (e.KeyCode == Keys.Down ) {
    this.Position.Y -= 100;
}
```
### Verhindern, dass ein Spieler aus dem Bild läuft


### Spiel pausieren

### Ihr schönstes Ergebnis





