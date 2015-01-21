# template-wiss-arbeit

LaTeX-Template für eine wissenschaftliche Arbeit

## Hinweise

### Glossar

####Beispiel für einen Glossareintrag:

Der Befehl ``\makeglossaries`` muss im Header der tex-Datei stehen, die später kompilliert wird. In diesem Template ist das die ``Vorlage.tex``


Ebenfalls im Header wird ein Glossareintrag erstellt:

	\newglossaryentry{Glossareintrag}{name={Glossareintrag},description={Das 
	ist die Beschreibung des Glossareintrags und daneben steht die Seitenzahl, 
	auf der der Eintrag zu finden ist}}

In dieser Vorlage befindet sich die Konfiguration des Glossars in der Datei ``konfiguration/glossarconfig.tex`` 

Im Text selbst werden dann die Verweise für einen Glossareintrag definiert:

	Test test \gls{Glossareintrag} test.

In der kompillierten Datei wird dann folgender Text angezeigt:

	Test test Glossareintrag test.

An der Stelle, an der das Glossar dann im Dokument angezeigt werden soll, ist folgender Befehl in das Dokument einzubinden:

	\printglossary[title={Glossar}, toctitle={Glossar}]

In dieser Vorlage ist das im Dokument ``anhang/glossar.tex`` ausgelagert.

Damit das Glossar auch im Inhaltsverzeichnis angezeigt wird, muss davor folgender Befehl stehen:

	\addcontentsline{toc}{chapter}{Glossar}{}

#### Kompillieren

Da das Glossar beim einfachen kompillieren nicht automatisch erzeugt und gebaut wird, müssen folgende Befehle nacheinander auf der Konsole ausgeführt werden:

1. ``pdflatex vorlage.tex`` 
2. ``makeindex.exe -s vorlage.ist -t vorlage.glg -o vorlage.gls vorlage.glo``
3. ``pdflatex vorlage.tex``