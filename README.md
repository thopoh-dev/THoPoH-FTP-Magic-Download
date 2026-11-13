# THoPoH FTP-Magic

**Kostenloser Download für Windows — 64-Bit**

Ein professioneller Zwei-Panel-Dateimanager für **FTP, FTPS, SFTP, SCP und
WebDAV**. THoPoH FTP-Magic verbindet die Geschwindigkeit von FileZilla
(parallele Transfers mit Einzel-Fortschrittsbalken) mit der Flexibilität von
WinSCP (Root-Rechte per sudo, Schlüssel-Authentifizierung) — und bringt eine
Reihe eigener Komfortfunktionen mit.

## Drei Funktionen, die es sonst nirgends gibt

**Das ist der Grund, dieses Programm zu benutzen.** Alle drei sind abschaltbar,
messen vorher nach und lassen sich jederzeit rückgängig machen.

### 1. Smart-Pipelining — viele Dateien als EIN Paket

Hunderte kleiner Dateien einzeln zu übertragen ist quälend langsam: jede Datei
braucht eigene Befehle, eigene Antworten, eigenes Warten. **Smart-Pipelining**
packt sie **zu einem Archiv**, überträgt **einen** Datenstrom und **entpackt auf
dem Server** wieder — und in der Gegenrichtung genauso (auf dem Server packen,
lokal entpacken). Vorher misst das Programm die Leitung und sagt, ob sich das
Paket überhaupt lohnt. Gemessen auf der Testleitung: **93 ms je Kommando**, bei
2.700 Dateien allein rund **vier Minuten**, die das Paket einspart.

### 2. Smart-Transfer — Dateien von Konto A nach Konto B, ohne Ihren Rechner

Zwei Reiter, zwei Konten: der Admin mit vollen Rechten, der Kunde mit seinen.
Markieren, **Smart-Transfer** wählen — die Dateien werden **serverseitig**
kopiert und laufen **nicht** über Ihre Leitung. Vorher prüft eine Probedatei,
dass beide Reiter wirklich denselben Server meinen; der Besitzer wird auf den
des Zielordners gesetzt.

### 3. Smart-Converter — Bilder werden kleiner, bevor sie hochgehen

Vor dem Upload prüft das Programm, ob Umwandeln lohnt (Stichprobe von drei
Dateien, echte Zahlen statt Schätzung) und schreibt **WebP** oder **AVIF** —
**das Original bleibt** erhalten, wenn Sie es so eingestellt haben. Gemessen an
einem Logo: **WebP −95,6 %**, **AVIF −78,3 %** Größe bei gleicher Anzeige.

Zu finden unter **Extras → Smart-Pipelining - Messung und Empfehlungen**, im
Kontextmenü der beiden Dateilisten (Smart-Transfer) und über den Schalter
**Smart-Converter**. Ausführlich in der mitgelieferten `README.md`
(Abschnitte 1.1.1, 2.11 und 13.8).

Weiter dabei: **zwei Reiter A und B** (zwei Verbindungen gleichzeitig),
**Dunkelmodus** mit Automatik, **sechs Sprachen**, **Zertifikatsprüfung** mit
Schloss, **Delta-Übertragung** (nur Änderungen), **Schnellmodus** für
Schlüsselpaare und der neu aufgebaute **Servermanager** mit beliebig tiefen
Verzeichnissen, freien Trennern und eigener Reihenfolge.

> **⚠️ Ausschließlich 64-Bit-Windows.** Das Programm ist eine 64-Bit-Anwendung
> (x86_64) und läuft nicht auf 32-Bit-Windows.

---

## Download

Die jeweils aktuelle Fassung liegt unter **[Releases](../../releases/latest)** —
dort das ZIP herunterladen. Im Paket enthalten:

| Datei | Zweck |
|---|---|
| `ftpbrowser.exe` | Das Programm |
| `libssh2.dll` | SSH-Bibliothek für SFTP/SCP |
| `libssl-3-x64.dll` | OpenSSL (TLS) |
| `libcrypto-3-x64.dll` | OpenSSL-Kryptografie (muss zu `libssl` passen) |
| `libwebp.dll` | Bild-Umwandlung: WebP |
| `libheif.dll` | Bild-Umwandlung: HEIC und AVIF (Container) |
| `libx265.dll` | HEIC/AVIF-Kodierung (H.265) |
| `de265.dll` | HEIF-Dekodierung (H.265) |
| `dav1d.dll` | AV1-Dekodierung |
| `lang\` | Sprachdateien (deutsch, englisch, französisch, niederländisch, polnisch, türkisch) |
| `README.md` | Ausführliche Anleitung |

`ftpbrowser.ini` und `ftpbrowser.profile.ini` sind **nicht** im Paket — sie
entstehen beim ersten Start bzw. beim ersten gespeicherten Profil.

## Installation

1. ZIP in einen **beschreibbaren** Ordner entpacken, z. B. `C:\Tools\FTP-Magic`
   oder einen Ordner unter `C:\Users\<Name>\...` — **nicht** nach
   `C:\Program Files`, dorthin darf das Programm nicht schreiben.
2. Prüfen, dass `ftpbrowser.exe` und **alle mitgelieferten DLLs** im selben
   Ordner liegen, und der Ordner `lang\` daneben liegt.
3. `ftpbrowser.exe` starten.

> **Warum der Ordner beschreibbar sein muss:** Alle Einstellungen und
> Verbindungsprofile liegen in zwei INI-Dateien **neben der EXE**. In einem
> schreibgeschützten Ordner startet das Programm zwar, kann aber nichts
> speichern — Einstellungen und Profile sind beim nächsten Start wieder weg.
>
> **Schnelltest:** Programm starten, schließen, in den Ordner schauen. Liegt
> dort eine `ftpbrowser.ini`, passt es.

Eine Installation im System findet nicht statt; zum Entfernen genügt das
Löschen des Ordners.

> **⚠️ Vor dem Löschen sichern:** Im Programmordner liegen Ihre Daten. Mit dem
> Ordner verschwinden `ftpbrowser.ini` (Einstellungen),
> `ftpbrowser.profile.ini` (alle Verbindungen) und alle Protokolle. Liegt dort
> ein Unterordner `keys\` mit eigenen Schlüsseln (Schnellmodus), ist auch der
> weg — danach kommen Sie auf diese Server nur noch mit Passwort. Den Ordner
> also vorher **umbenennen oder kopieren**, nicht einfach löschen.

## Vertrauen und Sicherheit

THoPoH FTP-Magic stammt von Thomas Pohlmann (Gewerbe seit 2008) und ist bewusst
so gebaut, dass es nichts tut, was es nicht offen sagt:

* **Keine Telemetrie, kein „nach Hause telefonieren".** Übertragen werden nur
  Ihre eigenen Serververbindungen und — höchstens alle 7 oder 30 Tage,
  abschaltbar — eine anonyme Abfrage der Versionsnummer bei GitHub. Kein Konto,
  keine Kennung, keine Cookies.
* **Kein Hintergrunddienst, kein Autostart, keine Fernsteuerung** und keine
  stillen Änderungen an Systemeinstellungen, Browsern oder Firewall.
* **Kein automatisches Update.** Der Hinweis auf eine neue Fassung öffnet nur
  den Browser; entpackt und ersetzt wird von Hand.
* **Keine Installation.** Das Programm läuft portabel aus seinem Ordner; zum
  Entfernen genügt das Löschen des Ordners.
* **Lizenz ohne Server:** Die Freischaltung wird lokal geprüft, es gibt keine
  Online-Aktivierung und keine Übertragung Ihrer Daten. Eine registrierte
  Fassung gilt für einen Windows-Benutzer auf einem Rechner.
* **Nachvollziehbar:** Zu jedem Release gehört eine `SHA256SUMS.txt`. Prüfen mit

  ```powershell
  Get-FileHash .\THoPoH_FTP-Magic_v1.0.3_win64.zip -Algorithm SHA256
  ```

  Der angezeigte Hash muss Zeichen für Zeichen dem Eintrag in `SHA256SUMS.txt`
  entsprechen.

**Warum Windows warnt:** Das Programm ist nicht kostenpflichtig signiert (ein
Code-Signing-Zertifikat kostet jährlich einen dreistelligen Betrag und ist seit
2023 an Hardware-Token gebunden). Windows zeigt deshalb „Der Herausgeber konnte
nicht überprüft werden" — das ist eine Aussage über die fehlende Signatur, nicht
über den Inhalt der Datei. Weiter mit **Weitere Informationen → Trotzdem
ausführen**; bei einer ZIP aus dem Internet zusätzlich Rechtsklick →
Eigenschaften → unten **Zulassen** ankreuzen.

Die vollständige Liste — welche Verbindungen aufgebaut, welche Dateien angelegt
werden und was das Programm ausdrücklich nicht tut — steht in der
mitgelieferten `README.md`, Abschnitt 12.1 bis 12.5.

## Registrierung

Das Programm läuft **30 Tage als Testversion** und lässt sich danach mit einem
Freischalt-Schlüssel zur Vollversion machen:

* **Vollversion: 10,00 Euro (einmalig)** — Schlüssel per E-Mail an
  **info@thopoh.de** anfordern, Name für die Registrierung angeben.
* Eingetragen wird der Schlüssel in den **Einstellungen → Gruppe
  „Registrierung"** (Name + Schlüssel).
* Der Ueber-Dialog zeigt jederzeit, ob Test- oder Vollversion läuft.

Der Preis ist bewusst niedrig gehalten: Es ist kein großer Kopierschutz,
sondern eine Anerkennung für die Arbeit — eher ein Kaffee als eine Hürde.

## Änderungen

### 1.0.3 — 13.11.2026

**Das Wichtigste vorweg:** Diese Fassung bringt die drei Funktionen, die es in
dieser Form nirgends gibt — **Smart-Pipelining** (viele kleine Dateien als ein
Paket übertragen und auf dem Server entpacken, in beide Richtungen),
**Smart-Transfer** (serverseitig von Konto A nach Konto B, ohne Umweg über den
eigenen Rechner) und **Smart-Converter** (Bilder vor dem Upload auf WebP/AVIF,
mit Stichprobe und gemessener Ersparnis). Dazu zwei Reiter, Dunkelmodus, sechs
Sprachen, Zertifikatsprüfung und der neu aufgebaute Servermanager.

**Neu**

* **Zwei Reiter A und B.** Zwei Verbindungen gleichzeitig — gedacht für
  „Serveradmin mit vollem Zugriff" und „Usertask zum Gegenprüfen". Jeder Reiter
  hat eigene Verbindung, eigene Pfade, eigenes Schloss, eigene Dateiliste; die
  Warteschlange bleibt eine.
* **Smart-Pipelining.** Viele kleine Dateien werden zu einem Archiv gepackt, in
  einem Transfer übertragen und auf der Gegenseite entpackt. Unter **Extras →
  Smart-Pipelining - Messung und Empfehlungen...** misst das Programm vorher die
  Leitung und sagt, ob sich das Paket lohnt.
* **Smart-Transfer (A → B).** Markierte Dateien serverseitig in den Ordner des
  anderen Reiters kopieren, ohne Umweg über den eigenen Rechner — mit
  Probedatei-Prüfung und Übernahme des Ziel-Besitzers.
* **Smart-Converter.** Bilder vor dem Hochladen in WebP/AVIF umrechnen, mit
  Stichprobe und eigener Fortschrittsanzeige.
* **Dunkelmodus mit Automatik.** Schalter in der Statusleiste: Auto / Dunkel /
  Hell; „Auto" übernimmt die Windows-Einstellung.
* **Sechs Sprachen über Textdateien** im Ordner `lang` (deutsch, englisch,
  französisch, niederländisch, polnisch, türkisch), wählbar in den
  Einstellungen. Fehlt eine Übersetzung, wird die Stelle sichtbar markiert.
* **Nur Änderungen hochladen (Delta).** Unveränderte Dateien werden erkannt,
  gezählt und auf Wunsch übersprungen.
* **Schnellmodus.** Schlüsselpaar auf diesem Rechner erzeugen und auf dem
  Server eintragen — mit Rücknahme; Ablage in `keys\`.
* **Servermanager neu aufgebaut.** Beliebig tiefe Verzeichnisse, freie Trenner,
  eigene Reihenfolge, Importe in getrennten Blöcken, Einträge per Menü **oder
  Maus** verschieben, Trenner umbenennen.
* **Zertifikatsprüfung mit Schloss** in der Statusleiste, einschließlich
  selbst ausgestellter Zertifikate nach Rückfrage.
* **Schreibrechte-Prüfung beim Start.** Ist der Programmordner nicht
  beschreibbar, sagt das Programm es einmal je Start im Klartext.

**Behoben**

* **`german.lng` enthielt türkische Texte** — die Sprachspalte wurde nach
  Zeilenposition statt nach Sprachcode gewählt.
* **Schlüsseldatei gehörte dem falschen Konto** — der Dateiname enthielt nur den
  Server, jetzt steht der Benutzer darin; alte Dateien werden weiter gefunden.
* **Update-Prüfung meldete den falschen Stand**, wenn die Fassung im Netz älter
  war als die installierte.
* **„Gezählte Objekte (Remote)" zeigte eine alte Zahl** beim direkten
  Ordner-Download (übertragen wurde alles, nur die Anzeige war falsch).
* **Schnellmodus fror ein („Keine Rückmeldung")** — leere Argumente gingen auf
  der Kommandozeile verloren, dadurch wurde der Schlüssel still verschlüsselt.
* **Deutsche Reste in fremder Sprache** — geänderte Texte verloren ihren
  Schlüssel; sie sind wieder übersetzt.
* **Löschen einer Gruppe** sichert die Profildatei vorher und nennt im Dialog,
  wie viele Server betroffen sind.
* **Kein „+ Neuer Server" mehr im Baum** — ein Fehlklick legte einen Server an
  einer nicht gewählten Stelle an; der Knopf **Neuer Server** genügt.

### 1.0.2 — 08.11.2026

**Neu**

* **Hinweis auf neue Versionen.** Beim Start prüft das Programm höchstens alle
  7 oder 30 Tage (einstellbar, Standard 7, auch abschaltbar), ob eine neuere
  Fassung vorliegt — anonym, ohne Konto. Auf Wunsch öffnet sich der Download im
  Browser; installiert wird nichts automatisch.
* **Menü „Hilfe" erweitert:** **Funktionen...** zeigt die Leistungsübersicht in
  einem eigenen Fenster, **Auf Updates prüfen...** fragt sofort nach.
* **Neuer „Ueber"-Dialog:** Name, Version, Registrierung und die technischen
  Angaben — inklusive der Versionen von `libssh2.dll`, `libssl-3-x64.dll` und
  `libcrypto-3-x64.dll`.
* **Datei-Eigenschaften der EXE:** Beschreibung, Dateiversion, Produktname,
  Copyright und Sprache sind jetzt hinterlegt (Rechtsklick > Eigenschaften >
  Details).
* **Transparenz:** Die README listet vollständig alle Netzwerkverbindungen, alle
  angelegten Dateien und was das Programm ausdrücklich nicht tut.

**Behoben**

* Mehrfachauswahl per Maus im Remote-Fenster (die Spalten waren breiter als das
  Fenster, dadurch fehlte der freie Streifen für den Auswahlkasten).
* Markierung ging bei der automatischen Aktualisierung verloren.
* Beim Schließen der Einstellungen kam fälschlich „Kein Lizenz-Key eingetragen";
  zugleich blieb das Key-Feld leer. Beides behoben — bei unverändertem
  Schlüssel schließt das Fenster ohne Meldung.

### 1.0.1 — 07.11.2026

**Neu**

* **Registrierung:** Vollversion oder 30-Tage-Testversion, Schlüssel wird in den
  Einstellungen eingetragen.
* **Verbindungsmanager: Sortierung und Live-Suche.** Die Liste ist alphabetisch
  sortierbar (Knopf über der Liste zeigt `A-Z` bzw. `Z-A`) und hat ein
  Suchfeld, das beim Tippen sofort filtert (`t` → alles mit t, `th` → weiter
  eingegrenzt). Sortierung und Filter wirken nur auf die Anzeige — die
  Profildatei bleibt unverändert, neue Profile werden weiterhin unten angehängt.
* **pCloud-Endpunkte:** Bei Protokoll WebDAV zeigt der Dialog die beiden
  richtigen Adressen (EU `https://ewebdav.pcloud.com`, US
  `https://webdav.pcloud.com`, beide Port 443).

**Behoben**

* „Hostadresse konnte nicht aufgelöst werden" bei Eingabe einer vollständigen
  Adresse wie `https://server/pfad`.
* HTTP 401 trotz richtigem Passwort — Ursache war der falsche pCloud-Endpunkt
  (US-Adresse bei einem EU-Konto).
* Leeres Remote-Fenster bei WebDAV (Auswertung der Serverantwort).

### 1.0.0 — 06.11.2026

Erste Fassung: Zwei-Panel-Oberfläche für FTP, FTPS, SFTP, SCP und WebDAV,
parallele Übertragungen mit Fortschrittsbalken, Warteschlange, Resume,
Schlüssel-Authentifizierung, Root-Rechte per sudo-SFTP, Import aus FileZilla
und WinSCP, integrierter Editor, Protokollfenster, PuTTY-Schnellzugriff.

---

*THoPoH FTP-Magic — Thomas Pohlmann — info@thopoh.de*
