Made by MK-snpz

# Netzwerk Manager Version 1.0

## Was ist das?
Eine lokale Web-App zur Verwaltung eines Heim- oder Kleinbuero-Netzwerks. Sie bietet eine zentrale Uebersicht fuer Router-Infos, Raspberry Pi Details, Port-Status, Versionsverlauf und Speedtests.

## Fuer wen?
Fuer alle, die ihr lokales Netzwerk an einem Ort dokumentieren und verwalten wollen, z. B. in der Familie oder im kleinen Buero.

## Warum existiert es?
Damit wichtige Netzwerkdaten nicht in Notizen verloren gehen und Aenderungen nachvollziehbar bleiben.

## Anforderungen
- Node.js (empfohlen: aktuelle LTS)

## Installation
```bash
npm install
```

## Konfiguration
- `Data/Nutzer`:
  - Zeile 1 = Benutzername
  - Zeile 2 = Passwort
  - Hinweis: Diese Datei ist nur zum Einsehen; Aenderungen erfolgen ueber die Website.
  - Beispiel:
    ```txt
    admin
    admin
    ```
- `Data/LoginToken.txt`:
  - Jede Zeile: `token|Geraetename`
  - `token` ist ein frei waehlbarer Code, der beim Login abgefragt werden kann.
  - `Geraetename` dient nur zur Anzeige/Identifikation in der UI.
  - Keine Leerzeilen am Anfang; Kommentare sind nicht vorgesehen.
  - Token generieren:
    - **macOS:** `./generate-token.command` ausfuehren
    - **Linux/Raspberry Pi:** `node -e "console.log(require('crypto').randomUUID())"`
  - Beispiel:
    ```txt
    123456789|MacBook von Manu
    987654321|iPhone
    ```
- `PORT`: Optionaler Port (Standard: `5055`)
- `PI_SPEEDTEST_ENABLED`: Optional, `1` aktiviert Speedtest-Proxy
- `PI_SPEEDTEST_HOST` und `PI_SPEEDTEST_PORT`: Ziel fuer den Proxy

## Starten
```bash
npm start
```

## Benutzen
- Im Browser `http://localhost:5055` oeffnen.
- Mit den Daten aus `Data/Nutzer` anmelden.
- Token ist optional; er dient nur fuer einen schnellen Direkt-Login.
- Optional Token in `Data/LoginToken.txt` hinterlegen.
- Port- und Geraeteinfos pflegen, Aenderungen werden gespeichert.

## Hinweise
- Laufzeitdaten werden in `Data/state.json` gespeichert.
- Diese Repo-Version enthaelt keine gespeicherten Zugangsdaten oder Geraeteinformationen.

## Security / Privacy
- Teile dein `Data/`-Verzeichnis niemals oeffentlich.
- Tokens und Passwoerter nicht in GitHub committen.
- Nutze bei Bedarf ein starkes Passwort in `Data/Nutzer`.

## Lizenz
Wenn du die Seite verwendest/weiterentwickelst und selbst veroeffentlichst, gib mir bitte Credits: github.com/MK-snpz


Viel Spass :)
Made by MK-snpz
