# NEWWAVE DESIGN – Podcast

Fertiger Film: 41,7 Sekunden, 1080 × 1920, 30 fps, H.264/AAC.
Deine echten Aufnahmen und deine echte Stimme. Fragen aus dem Off mit der zuvor bestätigten Sprecherin Serena. Original-JPG-Logo, Untertitel bei 70 % der Bildhöhe, animierte Grafiken und Kontaktkarte.

## Vorschau und Bearbeitung

Node.js 22 oder neuer installieren. Im entpackten Projekt:

```sh
npm ci
npm run dev
```

Im Remotion Studio `NWD-Podcast` auswählen. `NWD-Podcast-ZweiDurchlaeufe` zeigt den Übergang zwischen zwei Durchläufen. Alle Szenen sind als einzelne Sequences in `src/Composition.tsx` bearbeitbar. Gestaltung: `src/Scenes.tsx`, Untertitel: `src/Captions.tsx`.

```sh
npx remotion render src/index.ts NWD-Podcast out/NWD_03_Podcast.mp4 --codec=h264 --audio-codec=aac --crf=18 --concurrency=2
```

Bei bereits installiertem Chromium optional `--browser-executable=/usr/bin/chromium` ergänzen.

## Medien und Schnitt

`public/media/main.mp4` enthält den vollständigen vorbereiteten Bildschnitt als hochwertiges Proxyvideo. Originalton der beiden Aufnahmen liegt separat als WAV bei. Die ergänzende Aufnahme wird unter der Preisgarantie-Grafik verwendet; deshalb stört ihr anderer Hintergrund nicht. Der Cappi-Schatten wurde mit einer leichten Helligkeitskorrektur gemildert; die echte Mimik bleibt erhalten.

Lange Pausen und Wiederholungen wurden gekürzt. Keine pauschalen Einsparversprechen oder Leerlaufgarantien im Film. Die Preisgarantie-Grafik benennt ausdrücklich das eigene Angebot für den vereinbarten Innenausbau. Einige Untertitel wurden grammatisch geglättet; die gesprochene Stimme wurde nicht geklont oder umformuliert. Keine Hintergrundmusik.

Die finale Frage geht beim erneuten Abspielen direkt in „Nur auf den Preis schauen“ über. Die Bildquelle schließt an derselben Stelle an.

## Neuaufbereitung (optional)

Vorhandene WAVs reichen für Vorschau und Export. Für Änderungen am Rohschnitt: Python mit numpy und Pillow sowie FFmpeg installieren, dann `python prepare_edit.py` und `python build_composition.py` ausführen. Bereits enthaltene Audiodateien werden dabei neu erzeugt.

Neue Fragen optional mit `generate_questions.py` erzeugen. Dafür Qwen-TTS und CPU-PyTorch in einer separaten Python-Umgebung installieren und das offizielle Modell `Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice` laden. Den Modellpfad im Skript anpassen. Das große Modell ist nicht im ZIP enthalten. Stimme und Parameter stehen in `VOICE-PRESET.md`; für diese kurzen Fragen max_new_tokens=120, keine Beschleunigung. Die Modelllizenz liegt unter `public/questions/LICENSE.txt`.

## Prüfung

Remotion-Export und TypeScript-Prüfung erfolgreich. Vollständige MP4 ohne FFmpeg-Decodierfehler. Untertitel und zentrale Grafiken visuell geprüft. Spracherkennung bestätigt die enthaltenen Fragen und Antworten. Browserprüfung von zwei Durchläufen dokumentiert in `out/browser-check.json`. Ton zusätzlich über Sprachinhalt, Pegel und Decodierung technisch geprüft; keine subjektive Hörprüfung durch einen Menschen behauptet.

Quelldateien: `test-2.mp4`, `IMG_1826.MOV`, Original-JPG-Logo aus dem bereitgestellten ZIP. `production-brief.md` enthält den ursprünglichen Auftrag; diese Fassung setzt VIDEO 3 mit den tatsächlich aufgenommenen Antworten um. Keine weiteren Assets benötigt.
