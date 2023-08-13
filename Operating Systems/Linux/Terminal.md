view [[Linux_Cheat_Sheet]] for examples
## Root-Rechte

Für bestimmte Befehle bzw. Aktionen im Terminal sind eventuell Root-Rechte notwendig. Verschiedene Wege, um diese zu erlangen bzw. einen Root-Terminal zu öffnen, sind im Artikel [mit Root-Rechten arbeiten](https://wiki.ubuntuusers.de/mit_Root-Rechten_arbeiten/) beschrieben.


## Bedienung

Um dieselben Befehle nicht immer mühsam aufs Neue eintippen zu müssen kann man mit ↑ in den letzten Befehlseingaben rückwärtsblättern. Den jeweils erscheinenden Befehl kann man auf die eigenen Gegebenheiten abstellen/ändern, bevor er mit ⏎ zur Ausführung gebracht wird. Mit ↓ blättert man vor.

Befehle (Kommandos/Programme) und Befehlsausgaben können über die Zwischenablage bequem ausgetauscht werden (copy&paste). Dazu kann man das Kontextmenü (Kopieren/Einfügen) benutzen, oder unter Ubuntu die schnelle Variante mit ![linke Maustaste](https://media-cdn.ubuntu-de.org/wiki/attachments/31/38/mouse_left.png) und ![mittlere Maustaste](https://media-cdn.ubuntu-de.org/wiki/attachments/31/38/mouse_midd.png) (Mittelklick).

Um z.B. Befehlsvorgaben ins Terminal zu übernehmen, markiert man die Vorgabe mit gedrückter ![linke Maustaste](https://media-cdn.ubuntu-de.org/wiki/attachments/31/38/mouse_left.png) und fügt dies im Terminal mit einem ![mittlere Maustaste](https://media-cdn.ubuntu-de.org/wiki/attachments/31/38/mouse_midd.png) wieder ein (für die mittlere Maustaste ersatzweise linke und rechte Maustaste gleichzeitig drücken). Dabei gilt es die folgenden Punkte zu beachten:

1. Wenn man Befehle von dritten (z.B. übernommen von einer Webseite oder einem Forum) übernimmt sollte man wissen, was dieser Befehl bewirkt, um nicht ungewollt Schaden oder auch Datenverlust zu generieren.
    
2. Der Befehl muss u.U. auf die eigenen Gegebenheiten abgestellt/geändert werden, bevor er ausgeführt wird.
    
3. Der Befehl sollte nicht über mehrere Zeilen gehen, da ein Zeilenwechsel nicht mitkopiert werden darf und dieser wie eine "Eingabetaste auf halbem Weg des Befehls" wirkt.
    

### Tastenkombinationen

Manchmal will man Befehle ein weiteres Mal ausführen, muss nur eine Option dabei ändern oder sucht nach einem bestimmten, bereits ausgeführten Befehl. Um all diese Aufgaben effektiv erledigen zu können, gibt es eine Reihe von Tastenkombinationen, die mittels [GNU_Readline](https://en.wikipedia.org/wiki/GNU_Readline) implementiert werden.

#### Vervollständigen lassen, nicht tippen

Befehle und Dateinamen werden durch die Tabulatortaste Tab ⇆ automatisch ergänzt. Wenn dies nicht eindeutig möglich ist, werden bei einem weiteren Tab ⇆ alle Möglichkeiten zur Auswahl aufgelistet. Nun gibt man den eindeutigen Anfangsteil des entsprechenden Vorschlags ein und betätigt erneut die Tab ⇆ . Dies macht man solange bis der Befehl komplett ist und mit ⏎ zur Ausführung gebracht werden kann. Damit erspart man sich z.B. die fehlerträchtige Handeingabe sehr langer Dateinamen, siehe dazu [Autovervollständigung](https://wiki.ubuntuusers.de/Bash/#Autovervollstaendigung).

#### Suchfunktionen

- Mit Strg + R sucht man in den letzten Befehlseingaben ( ← bricht Suche ab, ⏎ führt Kommando erneut aus).
    
- Die Bildschirmanzeige lässt sich mithilfe der Tastenkombination Strg + ⇧ + F durchsuchen. Diese Suche erreicht man bei den meisten Terminals außerdem über deren Menüleiste, sie heißt dort etwa "Suchen" bzw. "Gehe zu".
    



#### Bereits erwähnte und Auswahl weiterer Tastenkürzel

|   |   |
|---|---|
|Bereits erwähnte und Auswahl weiterer Tastenkürzel|   |
|Öffnen|   |
|Tasten|Aktion|
|Strg + Alt + T|Standard zum Öffnen der meisten Terminalprogramme. Muss bei [KDE](https://wiki.ubuntuusers.de/Terminal/#KDE) erst aktiviert werden.|
|Strg + Alt + F3 bis F6|Öffnen der [Virtuellen Konsolen](https://wiki.ubuntuusers.de/Terminal/#Virtuelle-Konsole) 3 bis 6 (2 bis 6 bei KDE, bei MATE 1 bis 6)|
|Strg + Alt + F2|Von der [Virtuellen Konsole](https://wiki.ubuntuusers.de/Terminal/#Virtuelle-Konsole) zurück zur grafischen Oberfläche (bei KDE Strg + Alt + F1 )|
|Strg + Alt + F1|Von der [Virtuellen Konsole](https://wiki.ubuntuusers.de/Terminal/#Virtuelle-Konsole) zurück zum Login-Bildschirm (zur grafischen Oberfläche bei KDE)|
|Bearbeiten|   |
|Tasten|Aktion|
|Strg + A|Cursor an den Anfang der Eingabezeile bewegen.|
|Strg + E|Cursor an das Ende der Eingabezeile bewegen.|
|Alt + .|Einfügen der letzten Option (Wort) der letzten Eingabe – mehrmaliges Betätigen möglich.|
|Strg + H|Löscht letztes Zeichen vor Cursorposition, analog zu ⌫ .|
|Strg + D|Löscht nächstes Zeichen ab Cursorposition, analog zu Entf , auf einer leeren Zeile entspricht dies der Eingabe von `exit`.|
|Strg + W|Löscht letzten Begriff vor der Cursorposition.|
|Strg + U|Löscht alles ab der Cursorposition bis Anfang der Eingabezeile.|
|Strg + K|Löscht alles ab der Cursorposition bis Ende der Eingabezeile.|
|Strg + ⇧ + X|Löschen des Bildschirms vor aktueller Zeile.|
|Strg + ⇧ + C|Kopieren des markierten Texts in die Zwischenablage.|
|Strg + ⇧ + V|Einfügen der Zwischenablage an der Cursorposition.|
|Strg + C|Bricht laufenden Befehl/Prozess ab.|
|Suchen und Blättern|   |
|Tasten|Aktion|
|↑|Rückwärtsblättern in den letzten Befehlseingaben.|
|↓|Vorwärtsblättern in den letzten Befehlseingaben.|
|Tab ⇆|[Autovervollständigung](https://wiki.ubuntuusers.de/Terminal/#Vervollstaendigen-lassen-nicht-tippen) von Befehlen und Dateinamen.|
|Strg + R|Suchen in den letzten Eingaben ( ← bricht Suche ab, ⏎ führt Kommando erneut aus) – mehrmaliges Betätigen möglich.|
|Strg + ⇧ + F|Suchen in der Bildschirmanzeige.|
|Strg + ⇧ + ↑|Zeilenweises Rückwärtsblättern der Bildschirmanzeige.|
|Strg + ⇧ + ↓|Zeilenweises Vorwärtsblättern der Bildschirmanzeige.|
|⇧ + Bild ↑|Seitenweises Rückwärtsblättern der Bildschirmanzeige.|
|⇧ + Bild ↓|Seitenweises Vorwärtsblättern der Bildschirmanzeige.|

### Ergebnis/Ausgabe eines Befehls in Datei schreiben

Ausgaben können mittels [Shell/Umleitungen](https://wiki.ubuntuusers.de/Shell/Umleitungen/) in einer Textdatei zwischengespeichert werden, um diese später mit einem [Editor](https://wiki.ubuntuusers.de/Editor/) zu öffnen und auszuwerten. Dazu legt man zuerst eine Datei an, hier z.B. **~/ergebnis.txt** und befüllt diese, indem man an jedes Kommando Folgendes anfügt:

BEFEHL 2>&1 >> ergebnis.txt 

### Hinweis:

Unbedingt auf das Leerzeichen als Trenner zwischen Befehl und der Umleitungsanweisung achten!

Mit Hilfe der Programme [script](https://wiki.ubuntuusers.de/bsdutils/#script) oder [ttyrec](https://wiki.ubuntuusers.de/ttyrec/) lassen sich ganze Sitzungen im Terminal aufzeichnen, optional auch als Pseudovideo.

### Befehl mittels Skript öffnen

Wird ein Befehl öfter benötigt, kann dies mit einem Skript bewerkstelligt werden. Im folgenden Beispiel wird der Kernlog ausgegeben:

|   |   |
|---|---|
|1<br>2|#!/bin/bash<br>gnome-terminal -e "less /var/log/kern.log"|

Dieses speichert man z.B. unter **kernlog**. Nun muss es noch ausführbar gemacht werden, z.B. über _"Eigenschaften → Zugriffsrechte → Datei als Programm ausführen"_. Wird es gestartet, öffnet sich ein Terminal und die Logdatei wird mit dem Pager [less](https://wiki.ubuntuusers.de/less/) ausgegeben.

### Anwendungen in anderer Sprache starten

Nutzt man bspw. als Systemsprache Englisch und will ab und zu im Terminal ein Programm in Deutsch starten, dann geht dies folgendermaßen (hier am Beispiel von [Inkscape](https://wiki.ubuntuusers.de/Inkscape/)):

LANGUAGE=de inkscape 

Statt `de` kann man auch jede andere Sprache nehmen, z.B. `fr` für Französisch. Voraussetzung sind natürlich die jeweils separat zu installierenden [Sprachpakete](https://wiki.ubuntuusers.de/Spracheinstellungen/) (Lokalisierung).

[[Linux]]