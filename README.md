<!--
author:   Sebastian Zug

email:    sebastian.zug@informatik.tu-freiberg.de

version:  3.0.0

language: de

narrator: Deutsch Female

comment:  Demonstrator für den Schulunterricht: Was ein LiaScript-Kurs im
          Fach Mathematik kann – Quizze, Formeln mit automatischer Prüfung,
          bewegliche Grafiken, ausführbarer Code in JavaScript und Python
          und eingebettete Web-Apps. Thema: quadratische Funktionen (Klasse 9/10).

tags:     Mathematik, Schule, Quadratische Funktionen, Parabel, LiaScript, Demonstrator

import:   https://raw.githubusercontent.com/LiaTemplates/algebrite/0.7.1/README.md

import:   https://raw.githubusercontent.com/LiaTemplates/JSXGraph/0.0.3/README.md

import:   https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://LiaScript.github.io/course/?https://github.com/LiaPlayground/LiaScript-Mathe-Schule/blob/main/README.md)

# LiaScript im Mathematikunterricht

                        --{{0}}--
Willkommen! Dieser kurze Kurs zeigt an einem einzigen Thema, den Parabeln,
was mit LiaScript im Mathematikunterricht möglich ist.

> **Ein Demonstrator für Lehrkräfte** – und gleichzeitig ein kleines
> Arbeitsblatt für Schülerinnen und Schüler der Klasse 9/10 zum Thema
> **quadratische Funktionen**.

Der ganze Kurs ist eine einzige Markdown-Textdatei. Es gibt keinen Server, kein
Login und keine Installation – alles läuft im Browser, auch auf dem Tablet.

| Kapitel                  | Was gezeigt wird                                   |
| :----------------------- | :------------------------------------------------- |
| 1. Quizze                | sieben Quiztypen mit Hinweisen und Lösungen        |
| 2. Formeln und CAS       | LaTeX, Eingaben werden *mathematisch* geprüft      |
| 3. Bewegliche Grafik     | Parabel mit Schiebereglern (JSXGraph)              |
| 4. Ausführbarer Code     | JavaScript und Python direkt im Kurs               |
| 5. Web-App               | eine fertige Simulation eingebettet (PhET)         |
| 6. Für Lehrkräfte        | Wie baue ich so etwas selbst?                      |

<!-- style="border-left: 4px solid #1971c2; padding-left: 1rem" -->
> **Tipp:** Oben rechts lässt sich zwischen *Lehrbuch*, *Präsentation* (mit
> Vorlesestimme) und *Folien* umschalten. Probieren Sie den
> Präsentationsmodus – der Kurs spricht dann mit Ihnen.

## 1. Quizze

                        --{{0}}--
LiaScript kennt viele Quiztypen. Alle werden mit wenigen Zeichen im Text
geschrieben, zum Beispiel eckige Klammern mit einem X für die richtige Antwort.

Die Funktion $f(x) = x^2$ heißt **Normalparabel**. Ihr Graph ist
achsensymmetrisch zur $y$-Achse und hat den Scheitelpunkt $S(0|0)$.

**Einfachauswahl:** Welche Funktion ist eine quadratische Funktion?

[( )] $f(x) = 3x + 2$
[(X)] $f(x) = -2x^2 + 5$
[( )] $f(x) = \dfrac{1}{x}$
[( )] $f(x) = 2^x$
[[?]] Suche nach dem Term, in dem $x$ **im Quadrat** vorkommt.

**Mehrfachauswahl:** Welche Punkte liegen auf der Normalparabel $y = x^2$?

[[X]] $A(2|4)$
[[ ]] $B(3|6)$
[[X]] $C(-1|1)$
[[X]] $D(0|0)$
[[ ]] $E(-2\,|\,{-4})$
[[?]] Setze den $x$-Wert ein und vergleiche mit dem $y$-Wert.
[[?]] Ein Quadrat ist nie negativ.

**Texteingabe:** Wie heißt der höchste oder tiefste Punkt einer Parabel?

[[Scheitelpunkt]]
[[?]] Man sagt auch kurz „Scheitel“.

**Auswahlliste im Text:** Die Parabel $y = -x^2$ ist nach
[[ oben | (unten) ]] geöffnet, ihr Scheitelpunkt ist ein
[[ Tiefpunkt | (Hochpunkt) | Wendepunkt ]].

**Zuordnung (Matrix):** Was bewirkt der Parameter in
$f(x) = a\,(x-d)^2 + e$?

[ [Streckung / Spiegelung] [Verschiebung nach links/rechts] [Verschiebung nach oben/unten] ]
[           (X)                         ( )                              ( )               ] $a$
[           ( )                         (X)                              ( )               ] $d$
[           ( )                         ( )                              (X)               ] $e$
*********************************************************************

* $a$ streckt ($|a|>1$), staucht ($|a|<1$) oder spiegelt ($a<0$) die Parabel.
* $d$ verschiebt sie nach rechts ($d>0$) oder links ($d<0$).
* $e$ verschiebt sie nach oben ($e>0$) oder unten ($e<0$).

Der Scheitelpunkt ist also $S(d\,|\,e)$. Im Kapitel *Bewegliche Grafik*
können Sie das ausprobieren.

*********************************************************************

**Lückentext zum Ziehen:** Ziehe die Wörter in die Lücken.

Die Lösungen der Gleichung $f(x) = 0$ heißen
[->[ Scheitelpunkte | (Nullstellen) | Steigungen ]]. Eine Parabel kann
[->[ (höchstens zwei) | genau drei | unendlich viele ]] davon haben.

**Umfrage (ohne richtig oder falsch):** Wie gut kennst du dich mit Parabeln aus?

[(gut)] Kenne ich, kann ich.
[(mittel)] Habe ich schon mal gesehen.
[(neu)] Ist neu für mich.

## 2. Formeln und Computer-Algebra

                        --{{0}}--
Formeln werden in LaTeX geschrieben. Das Besondere: Ein eingebautes
Computer-Algebra-System prüft die Eingaben mathematisch. Es ist also egal, in
welcher Form die richtige Antwort eingegeben wird.

Formeln schreibt man wie in LaTeX, zum Beispiel die **Lösungsformel** für
$x^2 + px + q = 0$:

$$
x_{1,2} = -\frac{p}{2} \pm \sqrt{\left(\frac{p}{2}\right)^2 - q}
$$

<!-- style="border-left: 4px solid #2f9e44; padding-left: 1rem" -->
> **Mathematisch statt buchstabengenau:** Die Eingabefelder unten werden von
> einem Computer-Algebra-System geprüft. `x^2+6x+9`, `9+6*x+x^2` und
> `(x+3)*(x+3)` gelten als *dieselbe* Antwort. Nur vor einer Klammer braucht
> es ein `*`, also `2*(x+1)` und nicht `2(x+1)`.

**a)** Multipliziere mit der binomischen Formel aus:
$(x+3)^2 = $

[[x^2 + 6x + 9]]
[[?]] Erste binomische Formel: $(a+b)^2 = a^2 + 2ab + b^2$
@Algebrite.check(`x^2+6*x+9`)

**b)** Bringe $f(x) = x^2 - 4x + 1$ in die Scheitelpunktform
$f(x) = (x-d)^2 + e$:

$d = $ [[2]] $\quad e = $ [[-3]]
[[?]] Quadratische Ergänzung: $x^2 - 4x = (x-2)^2 - 4$
@Algebrite.check(`[ 2 ; -3 ]`)

**c)** Bestimme die Nullstellen von $f(x) = x^2 - 2x - 3$ (kleinere zuerst):

$x_1 = $ [[-1]] $\quad x_2 = $ [[3]]
[[?]] Hier ist $p = -2$ und $q = -3$.
[[?]] $x_{1,2} = 1 \pm \sqrt{1 + 3} = 1 \pm 2$
@Algebrite.check(`[ -1 ; 3 ]`)
*********************************************************************

$$
x_{1,2} = -\frac{-2}{2} \pm \sqrt{\left(\frac{-2}{2}\right)^2 - (-3)}
        = 1 \pm \sqrt{4} = 1 \pm 2
$$

Also $x_1 = -1$ und $x_2 = 3$. Probe: $(-1)^2 - 2\cdot(-1) - 3 = 0$ ✓

*********************************************************************

🧮 **Selbst rechnen:** Der folgende Block ist ein kleiner Taschenrechner für
Terme. Ändere die Zeilen und klicke auf den Ausführen-Knopf unten.

``` Maxima
f(x) = x^2 - 2*x - 3

factor(f(x))           -- in Linearfaktoren zerlegen
roots(f(x))            -- Nullstellen
f(5)                   -- Funktionswert an der Stelle 5

draw(f(x), x, -3, 5)
```
@Algebrite.pretty

## 3. Bewegliche Grafik

                        --{{0}}--
Hier ist eine dynamische Grafik. Mit den drei Schiebereglern verändern Sie die
Parameter a, d und e. Beobachten Sie, wie sich die Parabel und ihr
Scheitelpunkt bewegen.

🔍 Bewege die Regler $a$, $d$ und $e$. Die blaue Parabel ist
$f(x) = a\,(x-d)^2 + e$, grau gestrichelt die Normalparabel.

``` javascript @JSX.Graph.withParams(`boundingbox="[-6, 8, 6, -6]" showNavigation="false" grid="true"`)
var a = board.create('slider', [[-5.5, -3.6], [-2, -3.6], [-3, 1, 3]],
  { name: 'a', snapWidth: 0.1, size: 5, strokeColor: '#1971c2', fillColor: 'white' });
var d = board.create('slider', [[-5.5, -4.5], [-2, -4.5], [-4, 0, 4]],
  { name: 'd', snapWidth: 0.5, size: 5, strokeColor: '#e8590c', fillColor: 'white' });
var e = board.create('slider', [[-5.5, -5.4], [-2, -5.4], [-4, 0, 4]],
  { name: 'e', snapWidth: 0.5, size: 5, strokeColor: '#2f9e44', fillColor: 'white' });

// Zahl mit Vorzeichen für die Termanzeige: "+ 2.0" bzw. "− 2.0"
function sgn(v) { return (v < 0 ? '− ' : '+ ') + Math.abs(v).toFixed(1); }

var f = function (x) {
  return a.Value() * (x - d.Value()) * (x - d.Value()) + e.Value();
};

// Normalparabel zum Vergleich
board.create('functiongraph', [function (x) { return x * x; }],
  { strokeColor: '#adb5bd', strokeWidth: 1, dash: 2, fixed: true, highlight: false });

board.create('functiongraph', [f], { strokeColor: '#1971c2', strokeWidth: 3 });

// Scheitelpunkt
board.create('point', [function () { return d.Value(); }, function () { return e.Value(); }],
  { name: 'S', size: 5, fixed: true, strokeColor: '#c92a2a', fillColor: '#c92a2a',
    label: { offset: [10, -10], fontSize: 16 } });

board.create('text', [0.5, -3.6, function () {
  return 'f(x) = ' + a.Value().toFixed(1) + '·(x ' + sgn(-d.Value()) + ')² ' + sgn(e.Value());
}], { fontSize: 16, cssStyle: 'font-family: monospace' });

board.create('text', [0.5, -4.5, function () {
  return 'S(' + d.Value().toFixed(1) + ' | ' + e.Value().toFixed(1) + ')';
}], { fontSize: 16, cssStyle: 'font-family: monospace; color: #c92a2a' });

board.create('text', [0.5, -5.4, function () {
  var A = a.Value(), E = e.Value();
  if (A === 0) { return 'a = 0: keine Parabel!'; }
  var r = -E / A;
  if (r > 0)  { return 'zwei Nullstellen'; }
  if (r === 0) { return 'eine Nullstelle'; }
  return 'keine Nullstelle';
}], { fontSize: 16, cssStyle: 'color: #2f9e44' });
```

**Aufgabe:** Stelle mit den Reglern die Parabel
$f(x) = -\tfrac{1}{2}(x-2)^2 + 3$ ein. Welche Aussagen stimmen?

[[X]] Die Parabel ist nach unten geöffnet.
[[ ]] Der Scheitelpunkt ist $S(-2\,|\,3)$.
[[X]] Die Parabel ist breiter als die Normalparabel.
[[X]] Die Parabel hat zwei Nullstellen.
[[?]] Lies den Scheitelpunkt in der roten Zeile ab.
[[?]] Wo liegt ein Hochpunkt *über* der $x$-Achse – und wohin zeigen die Äste?

## 4. Ausführbarer Code

                        --{{0}}--
Programmcode kann direkt im Kurs ausgeführt und verändert werden. JavaScript
läuft ohne weitere Einbindung, Python wird beim ersten Start in den Browser
geladen.

### JavaScript: Wertetabelle

Klicke auf den Ausführen-Knopf unter dem Code. Ändere dann die Funktion
`f` oder den Bereich der Schleife und führe den Code erneut aus.

``` javascript
function f(x) {
  return x * x - 2 * x - 3;
}

for (let x = -2; x <= 4; x++) {
  console.log("f(" + x + ") = " + f(x));
}

"Wertetabelle fertig"
```
<script>@input</script>

Bei welchen $x$-Werten zeigt die Tabelle den Funktionswert $0$? Und passt
das zur Aufgabe **c)** im Kapitel 2?

### Python: Nullstellen berechnen und zeichnen

Python ist die Programmiersprache, die im Informatikunterricht am häufigsten
verwendet wird. Das Programm berechnet die Nullstellen mit der
$pq$-Formel und zeichnet die Parabel. *Der erste Start dauert einige Sekunden.*

``` python
import math
import matplotlib.pyplot as plt

p, q = -2, -3            # f(x) = x^2 + p*x + q

D = (p / 2) ** 2 - q     # Diskriminante
print("Diskriminante:", D)

if D > 0:
    x1 = -p / 2 - math.sqrt(D)
    x2 = -p / 2 + math.sqrt(D)
    print("Zwei Nullstellen:", x1, "und", x2)
elif D == 0:
    print("Eine Nullstelle:", -p / 2)
else:
    print("Keine Nullstelle")

xs = [x / 10 for x in range(-40, 61)]
ys = [x ** 2 + p * x + q for x in xs]

plt.plot(xs, ys)
plt.axhline(0, color="gray")
plt.grid(True)
plt.title("f(x) = x² + (%g)·x + (%g)" % (p, q))
plt.show()
```
@Pyodide.eval

**Aufgabe:** Ändere `p` und `q` so, dass die Parabel **keine** Nullstelle hat.
Welche Bedingung muss für die Diskriminante gelten?

$D$ [[ > | = | (<) ]] $0$

## 5. Web-App einbetten

                        --{{0}}--
Fertige Web-Anwendungen wie die Simulationen von PhET oder GeoGebra-Applets
lassen sich mit einer einzigen Zeile in den Kurs einbetten.

Hier die PhET-Simulation *Quadratische Kurven* der University of Colorado.
Im Quelltext steht dafür nur `??[Beschreibung](Adresse)`:

??[PhET: Graphing Quadratics](https://phet.colorado.edu/sims/html/graphing-quadratics/latest/graphing-quadratics_all.html?locale=de)

**Aufgabe:** Öffne in der Simulation die Ansicht *Scheitelpunktform*. Stelle
eine Parabel mit dem Scheitelpunkt $S(1\,|\,{-4})$ und $a = 1$ ein. Bei welchen
$x$-Werten schneidet sie die $x$-Achse? (kleinere zuerst)

$x_1 = $ [[-1]] $\quad x_2 = $ [[3]]
[[?]] Das ist wieder unsere Parabel $f(x) = x^2 - 2x - 3$ – nur anders geschrieben.
@Algebrite.check(`[ -1 ; 3 ]`)

## 6. Für Lehrkräfte

                        --{{0}}--
Zum Schluss: Wie entsteht ein solcher Kurs, und wie kommt er zu den
Schülerinnen und Schülern?

**So entsteht ein Kurs**

* Der Kurs ist eine Textdatei in Markdown. Ein Quiz ist zum Beispiel nur
  `[(X)] richtig` und `[( )] falsch`.
* Bearbeiten lässt er sich im [LiveEditor](https://liascript.github.io/LiveEditor/)
  oder in VS Code mit der LiaScript-Erweiterung.
* Zusatzfunktionen wie der Formelprüfer, die Grafiken oder Python werden mit
  einer Zeile `import:` im Kopf der Datei eingebunden.

**So kommt er zu den Lernenden**

* Datei auf GitHub, in eine Cloud oder auf einen Webserver legen und den
  Link `https://liascript.github.io/course/?<Adresse der Datei>` verteilen.
* Eingaben werden nur lokal im Browser gespeichert. Es werden keine Daten
  der Schülerinnen und Schüler an einen Server übertragen.
* Für Moodle, OPAL und andere Lernplattformen kann der Kurs als SCORM-Paket
  exportiert werden.

**Mehr Beispiele**

* [LiaScript-Dokumentation](https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md)
* [Aufgabensammlung von MINT-the-GAP](https://mint-the-gap.github.io/Aufgabensammlung/)
  mit vielen Beispielen aus dem Schulalltag in allen Fächern

Wie hilfreich war dieser Demonstrator für Sie?

[(1)] Sehr hilfreich – ich probiere es aus.
[(2)] Interessant, aber ich brauche noch Unterstützung.
[(3)] Für meinen Unterricht eher nicht geeignet.

Was würden Sie gern noch sehen? Die Antwort bleibt lokal in Ihrem Browser.

[[___ ___ ___]]

---

Gebaut aus einer einzigen Markdown-Datei:
[LiaScript](https://liascript.github.io) als Kursformat,
[Algebrite](http://algebrite.org) für Rechenblöcke und Antwortprüfung,
[JSXGraph](https://jsxgraph.org) für die bewegliche Grafik,
[Pyodide](https://pyodide.org) für Python im Browser und
[PhET](https://phet.colorado.edu) für die Simulation.

<!-- style="font-size: 90%" -->
> Dieser Kurs steht unter
> [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.de).
> Sie dürfen ihn teilen, umarbeiten und im eigenen Unterricht einsetzen –
> unter Nennung der Quelle und unter gleichen Bedingungen.
