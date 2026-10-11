# Bevorzugte NEWWAVE-Sprachfassung

Der Nutzer hat die Serena-Fassung ausdrücklich als sehr gelungen und deutlich menschlicher klingend bestätigt. Für weitere NEWWAVE-Videos diese Stimme und Vorgehensweise bevorzugen.

## Stimme und Modell

- Modell: Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice
- Sprecherin: Serena
- Sprache: German
- Ausgabe: 24 kHz
- Lizenz: Apache 2.0
- Lokales Modell: /workspace/tts-models/qwen-natural
- Python-Umgebung: /workspace/natural-voice-tools
- Referenzprojekt: /workspace/nwd-angebotsvergleich-natuerlich
- Produktionsskript: generate_voice.py im Referenzprojekt
- Freigegebene Referenz: NWD_02_Serena.mp4 auf GitHub, Branch video-2-serena

## Tatsächlich verwendete Einstellungen

Qwen3TTSModel.from_pretrained mit device_map='cpu', dtype=torch.bfloat16 und attn_implementation='sdpa'.
PyTorch: 4 Threads, 1 Interop-Thread, seed=42.
generate_custom_voice: speaker='Serena', language='German', do_sample=True, temperature=0.7, top_p=0.9, max_new_tokens=180 pro Satz.
Das 0.6B-Modell unterstützt keine Stilsteuerung über instruct. Keine solche Wirkung behaupten.

## Vorgehensweise für den bestätigten Klang

Den Text mit dem neueren Qwen-Sprachmodell neu synthetisieren. Den natürlich wahrgenommenen Klang lieferte dieses Modell mit Serena; er entstand nicht durch eine Tonhöhenverschiebung der vorherigen Stimmen.

Nur leise Ränder der einzelnen Aufnahmen kürzen: Amplitudenschwelle 0.008, 35 ms Vorlauf und 70 ms Nachlauf behalten. Für vorhandene Filme die Satzstarts erhalten. Bestehende stille Pausen bei Bedarf mitnutzen, um kurze Sätze weniger zu beschleunigen. Tonhöhe bei einer nötigen Tempoanpassung über FFmpeg atempo erhalten. Die tatsächlichen Anpassungen stehen in public/voice-timing.json. 1.15 war das angestrebte Beschleunigungslimit; bei engen Zeitfenstern wurde es teilweise überschritten, z.B. 1.279 für „Welche Ausbaustufe?“. Für neue Filme zuerst natürlich erzeugte Sprache verwenden und das Bildtiming daran anpassen, sofern der Nutzer keine feste Länge verlangt.

Lautheit: FFmpeg loudnorm=I=-16:TP=-1.5:LRA=9, danach 24 kHz. Gemessene Referenz: -17.08 LUFS integriert, -1.45 dBTP, 4.2 LU Lautheitsbereich. Nicht jedes neue Ergebnis auf exakt diese Messwerte zwingen.

Markenname im Synthesetext als „New Wave Design“ schreiben. Anzeige und Original-Sprechertext bleiben „NEWWAVE DESIGN“. Alle Wörter der fertigen Aufnahme wurden mit Whisper small korrekt erkannt, einschließlich Markenname und Preisgarantie. Die vollständige MP4 wurde im Chromium abgespielt und decodiert. Bei reinem Tonwechsel die freigegebene H.264-Bildspur mit -c:v copy übernehmen, damit die Videoqualität erhalten bleibt.

Keine Stimme klonen. Keine weiteren Medien, Preise oder Leistungen erfinden. Die Preisgarantie gilt nur für das eigene Angebot zum vereinbarten Innenausbau.

## Downloads

Der Nutzer kann Cloud-Dateien oft nicht herunterladen. Fertige Dateien wie bereits autorisiert im Repository imanaziiiziii-NWD/Werbevideo bereitstellen, mit GitHub-Dateilinks und Hinweis auf „Download raw file“.

Referenzfilm:
https://github.com/imanaziiiziii-NWD/Werbevideo/blob/video-2-serena/downloads/video-2-serena/NWD_02_Serena.mp4
