# Portrait-Coach – Web (Handy)

Läuft komplett im Handy-Browser, keine App-Installation. Öffnen → Kamera
startet → **5 Sekunden Analyse** → das bestbewertete Bild wird automatisch
gewählt und mit Statistik angezeigt.

- Analyse-Fenster sammelt pro Frame einen Score; gemerkt wird das beste Bild.
- Am Ende: **Statistik** (Bester Score, Durchschnitt, Min, Streuung, Frames).
- Rückkamera → echte **Blitz-Lampe** leuchtet während der Analyse (Android).
- Frontkamera (Selfie) → **Bildschirm-Blitz** als Signal (keine Lampe vorhanden).
- **Foto speichern** (Android: in Galerie/teilen; sonst Download), **Nochmal**.
- Fensterlänge über `CONFIG.session_seconds` einstellbar.

Die gesamte Analyse passiert auf dem Gerät – es wird nichts hochgeladen.

## Auf GitHub Pages veröffentlichen

1. Neues GitHub-Repo anlegen, `index.html` (und dieses README) hochladen.
2. Repo → **Settings → Pages** → Source: `main`, Ordner `/ (root)` → Save.
3. Nach ~1 Minute ist die Seite unter
   `https://<dein-name>.github.io/<repo>/` erreichbar.
4. Auf dem Handy öffnen (am besten als QR-Code teilen).

**Wichtig:** Kamera-Zugriff geht nur über **HTTPS** – GitHub Pages liefert das
automatisch. Beim ersten Öffnen die Kamera-Erlaubnis bestätigen.

## Lokal testen (am PC)

Einfach Doppelklick reicht **nicht** (file:// erlaubt keine Kamera). Stattdessen:

```powershell
cd C:\Users\Mendel\Projects\portrait-coach\web
python -m http.server 8000
```

Dann im Browser `http://localhost:8000` öffnen (localhost gilt als sicher).

## Kalibrieren

Oben im `<script>` steht `CONFIG` – dieselben Werte wie im PC-Prototyp
(Yaw/Pitch-Zielwinkel, Lächel-Band, Auslöse-Score). Die HUD-Zeile unten zeigt
`yaw/pitch/roll/smile/sharp` live zum Ablesen.

## Grenzen im Browser

- Taschenlampe nur auf **Android + Rückkamera** (iPhone/Safari erlaubt das nicht).
- Für die Lampe bei Selfies bräuchte es eine echte App (spätere Android-Portierung).
