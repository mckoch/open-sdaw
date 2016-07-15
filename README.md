open-sdaw
=========

Tools to read and write the SDAW Format "Standarddatensatz Außenwerbung"


##A collection

This is the master brach for a toolset to read and write a common format of the german advertising industry. 
It contains code to read sdaw files from Windows, export them to a SQL database, some PHP classes to query, and a Javascript/jQuery based interface using google maps.

This collection is not plug-and-play, but provides a lot of "how to" to the application programmer, since the sdaw format has only very few public available documentation.

*Since this collection is specific to the german market, some main parts and comments are in german language.*

##SDAW unleashed

SDAW - kurz für: Standarddatensatz Außenwerbung (gelegentlich auch Standardisierter Datensatz Außenwerbung) ist das Austauschformat der deutschen Außenwerbung. Hiermit werden Daten zu Standorten von Werbeträgern, deren Belegung, Beschreibungen anzubringender Medien sowie Buchungs- und Abrechnungsdaten ausgetauscht. 

> Für Unternehmen in der Außenwerbung ist die Verarbeitung dieses Formats zwingend vorgeschrieben.

Jedes Objekt und Ereignis in der realen welt wird durch einen eigenen Dateityp repräsentiert, so dienen z.B. STA-Dateien der Beschreibung von Werbeträgerstandorten, FRE-Dateien enthalten deren aktuelle Belegung/Freizahlen. Insgesamt gibt es rund 30 verschiedene SDAW-Dateitypen. 

> Es gibt nur eine geringe, i. d. R. sehr hochpreisige Auswahl an Software zur Verarbeitung von SDAW-Dateien. 

Alle SDAW-Datien haben folgende Punkte gemeinsam:

* Es sind reine Textdateien.
* Die erste Zeile enthält eine Beschreibung des Dateiinhaltes und des Herausgebers (Kopfsatz).
* Jede Zeile entspricht einem Datensatz (Nutzdaten bzw. Kontrolldaten).
* Der erste Buchstabe jeder Zeile beschreibt den Inhalt des Datensatzes.
* Datenfelder sind durch ihre numerische Position in der Zeile festgelegt.
* Leerstellen bis zur nächsten Feldbeginn werden aufgefüllt.
* Eine Zeile kann mehrere Detaildatensätze enthalten (z.B. Freizahlen zu einem Standort)

Es sind keinerlei Steuerungsdaten für Programme oder Escape-Sequenzen vorgesehen. Per Konvention werden SDAW-Dateien entsprechend Typ, Datum und Herausgeber benannt. 

> Das SDAW-Format wird in einem vom Fachverband Außenwerbung an die Verbandsmitglieder herausgegebenem Dokument beschrieben. 

Zusammenfassend: Das SDAW-Format basiert auf Textdateien, deren Zeilen einzelne Datensätze repräsentieren. Datenfelder werden durch Position in der Zeile definiert. Der Inhalt (Datentyp) einer SDAW-Datei wird durch ihren Kopfdatensatz (K) in  der ersten Zeile festgelegt. Vereinfacht gesagt, gibt es zwei Klassen an SDAW-Dateien: "deskriptive" Formate, die Informationen über den Zustand von z.B. Standorten liefern (Stammdaten), sowie "ereignisbasierte" Formate wie z.B. Buchungen oder Plakatieraufträge. Die Verarbeitung ist nicht an propietäre Software gebunden.

## Open Sdaw

Trotz der intensiven Nutzung des Formats sind nur wenige Werkzeuge verfügbar. Dem gegenüber steht eine hohe Anzahl Anwender, denn das Format bildet den gesamten Arbeitsfluss der Außenwerbung - vom Standortpächter über den Flächenvermarkter bis zum Plakatkleber - ab. Allen Beteiligten sind auf wenige, hochpreisige Softwarelösungen bzw. Dienstleister mit dieser Software angewiesen; so ist z.B. die Einsicht in flächendeckende Standort- und Belegungsdaten wenigen Spezialmittlern vorbehalten. Spezifikation und Dokumentation sind öffentlich nur rudimentär verfügbar.

## Bestehende Komponenten / Code Recycler

### Serverkomponenten

#### GDM API

Version 0.4dev/0.7stable open
PHP5, ADODB

https://github.com/mckoch/geodatamapper 

#### GDM SDAW Importmodul

Version 0.7stable open
PHP5, ADODB

https://github.com/mckoch/sdaw-import

### Interfacekomponenten

#### GDM API Browser Interface

Version 0.4/0.7stable/0.9b open
jQuery, gmaps

https://github.com/mckoch/gdm-api-sdaw 


#### sdxist.exe

SDAW File Reader & Converter, win32 binary, 1.0beta1 (Preprozessor)
Windows Forms, C#.

https://github.com/mckoch/sdxist 

### Anmerkungen

Sämtliche Datenformate werden per XML konfiguriert und sind somit serverseitig übergreifend verfügbar, unabhängig vom verwendeten Importformat. Insofern sind die Komponenten unspezifisch gegenüber bestehenden  lat/lng  Daten. 

----------
"'Free' in 'free software' has nothing to do with 'free' in 'free beer'." 

----------
