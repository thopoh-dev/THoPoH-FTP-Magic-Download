# THoPoH FTP-Magic

**Kostenloser Download für Windows — 64-Bit**

Ein professioneller Zwei-Panel-Dateimanager für **FTP, FTPS, SFTP, SCP und
WebDAV**. THoPoH FTP-Magic verbindet die Geschwindigkeit von FileZilla
(parallele Transfers mit Einzel-Fortschrittsbalken) mit der Flexibilität von
WinSCP (Root-Rechte per sudo, Schlüssel-Authentifizierung) — und bringt eine
Reihe eigener Komfortfunktionen mit.

> **⚠️ Ausschließlich 64-Bit-Windows.** Das Programm ist eine 64-Bit-Anwendung
> (x86_64) und läuft nicht auf 32-Bit-Windows.

> **Dieses Repository enthält nur die fertigen Programm-Pakete.** Der Quellcode
> ist nicht öffentlich.

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
| `README.md` | Ausführliche Anleitung |

`ftpbrowser.ini` und `ftpbrowser.profile.ini` sind **nicht** im Paket — sie
entstehen beim ersten Start bzw. beim ersten gespeicherten Profil.

## Installation

1. ZIP in einen **beschreibbaren** Ordner entpacken, z. B. `C:\Tools\FTP-Magic`
   oder einen Ordner unter `C:\Users\<Name>\...` — **nicht** nach
   `C:\Program Files`, dorthin darf das Programm nicht schreiben.
2. Prüfen, dass `ftpbrowser.exe` und die drei DLLs im selben Ordner liegen.
3. `ftpbrowser.exe` starten.

> **Warum der Ordner beschreibbar sein muss:** Alle Einstellungen und
> Verbindungsprofile liegen in zwei INI-Dateien **neben der EXE**. In einem
> schreibgeschützten Ordner startet das Programm zwar, kann aber nichts
> speichern — Einstellungen und Profile sind beim nächsten Start wieder weg.
>
> **Schnelltest:** Programm starten, schließen, in den Ordner schauen. Liegt
> dort eine `ftpbrowser.ini`, passt es.

Eine Installation im System findet nicht statt; zum Entfernen genügt das
Löschen des Ordners (vorher `ftpbrowser.profile.ini` sichern, wenn Sie Ihre
Profile behalten wollen).

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
