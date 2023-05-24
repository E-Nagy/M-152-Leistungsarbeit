# M152 Leistungsarbeit

## Inhalt

* [Einführung](#einf-hrung)
* [Anforderungen](#anforderungen)
    + [Fehler beheben](#fehler-beheben)
    + [Fehlende Funktionen implementieren](#fehlende-funktionen-implementieren)
        - [Ausloggen](#ausloggen)
        - [Profil](#profil)
        - [Mobile Darstellung](#mobile-darstellung)
        - [Alle Noten löschen](#alle-noten-l-schen)
    + [Darstellung](#darstellung)
* [Setup](#setup)
* [Prüfungsregeln](#pr-fungsregeln)
* [Abgabe](#abgabe)
* [Viel Glück!](#viel-gl-ck-)

## Einführung

Sie haben vor kurzem Ihr Praktikum gestartet und bereits Ihr erstes Projekt übernommen. Es handelt sich um eine Applikation,
welche Ihre Vorgängerin erstellt hat. Da das Praktikum für sie jedoch zu Ende ging, konnte sie die Applikation nicht fertigstellen.

Ihre Aufgabe ist es nun, diese Applikation lauffähig zu machen, die fehlenden Funktionen zu implementieren und die Darstellung zu verbessern.
Da Sie als Frontend-Entwickler eingestellt sind, müssen Sie Sich keine Gedanken darüber machen wie die Daten gespeichert werden. Einzig die
Funktionen welche im Browser ausgeführt werden und/oder dargestellt werden fallen in Ihren Aufgabenbereich.

## Anforderungen

### Fehler beheben

In der Applikation haben sich mindestens 6 Fehler eingeschlichen. Dies kann sein, dass eine Funktion welche über das GUI erreichbar ist,
nicht funktioniert oder dass etwas im Code begonnen wurde, aber nicht komplett fertiggestellt wurde.

Ihr Aufgabe ist es, diese 6 Fehler zu finden und zu beheben.

> Die Behebung der Fehler macht 40% der Bewertung aus.

### Fehlende Funktionen implementieren

Einige Funktionen konnten aufgrund der Zeit nicht implementiert werden. Diese müssen Sie nun entsprechend den folgenden Vorgaben fertigstellen.

> Das fertigstellen der fehlenden Features macht 40% der Bewertung aus.

#### Ausloggen

Klickt man auf "Logout" soll sich ein Modal öffnen welches den Benutzer fragt, ob er sich wirklich abmelden möchte. Bei einem "Nein" schliesst
sich das Modal wieder, bei einem "Ja" wird der Benutzer auf google.com weitergeleitet.

Es ist bereits ein Teil davon in der Datei `App.vue` vorbereitet welchen Sie übernehmen sollen.

#### Profil

Unter dem Menupunkt "Profil" soll ein Formular erscheinen in welchem der Benutzer seine persönlichen Daten eingeben kann.
Folgende Daten sind für die Applikation relevant:

- Name und Vorname
- E-Mail Adresse der Schule
- E-Mail Adresse privat
- Wohnadresse inkl. PLZ + Stadt
- Jahrgang
- Schuljahr (1. Jahr, 2. Jahr oder 3. Jahr)
- Passwort

> Hinweis: Die Validation spielt keine Rolle. Die Daten sollten aber bereits im Vue Code zur Verfügung stehen.

#### Mobile Darstellung

Zurzeit ist die Applikation nur auf Desktop Geräten gut nutzbar. Passen Sie diese so an, dass Sie auch auf Mobilen Geräten
gut genutzt werden kann.

#### Alle Noten löschen

Leider kann man im Moment nur ein ganzes Fach löschen oder alle Noten des Faches einzeln. Fügen Sie, pro Fach, einen weiteren
Button hinzu, welcher alle Noten des Faches löscht.

### Darstellung

Die Darstellung ist im Moment zwar nutzbar, aber lässt einiges zu wünschen übrig. Buttons kleben zusammen, die Farbkontraste sind schlecht, usw.

Verbessern Sie die Darstellung so gut es Ihnen möglich ist.

> Die Verbesserung der Darstellung macht 20% der Bewertung aus

## Setup

Klonen Sie dieses Repository und führen Sie dann folgende Befehle aus:

```shell
npm install
npm run dev
```

## Prüfungsregeln

Es sind alle im Internet zugänglichen Unterlagen erlaubt (siehe folgende Ausnahmen). Auch alte Projekte dürfen als Hilfestellung verwendet werden.
Kommen Sie gar nicht mehr weiter, fragen Sie bei mir nach Rat.

Nicht erlaubt sind:

- Austausch mit Sitznachbarn
- Alle Chat und/oder Kommunikationsprogramme (Teams, Whatsapp, Discord, Signal, usw...)
- Generative AI's wie ChatGPT, CoPilot oder ähnliche Software

## Abgabe

Wenn Sie mit der Arbeit fertig sind, führen Sie folgende Schritte aus:

1. Öffnen Sie den Projektordner im Explorer
2. Verpacken Sie von dort aus alle Ordner und Dateien **ausser** `.git/` und `node_modules/` in ein Zip File
   1. Für das Verpacken verwenden Sie am besten die Software 7Zip
3. Senden Sie die Zip Datei per Teams an mich.
4. Lassen Sie Sich den Erhalt und die Lesbarkeit der Datei von mir bestätigen.

## Viel Glück!