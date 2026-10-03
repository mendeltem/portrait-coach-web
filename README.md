# Portrait-Coach – Web (Handy)

Läuft komplett im Handy-Browser, keine App-Installation. Öffnen → Kamera
startet → Pose wird live bewertet → bei bester Pose automatisch Foto.

- 🔴 **ANALYSE** / 🟡 **HALTEN** / 🟢 **PERFEKT!** (Vollbild-Rand + Badge)
- Rückkamera → echte **Blitz-Lampe** leuchtet beim Analysieren (Android)
- Frontkamera (Selfie) → **Bildschirm-Blitz** als Signal (keine Lampe vorhanden)
- Bei bester Pose: Foto wird angezeigt, Lampe aus, Vibration

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
