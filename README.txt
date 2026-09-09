Wohnungsprotokoll – Version 2.6 (Datenschutz + neue Mieteranschrift)

Neu in V2.6:
- Feld für die neue Anschrift des Mieters / der Mieterin (Straße/Hausnummer sowie PLZ/Ort), insbesondere für Wohnungsabnahmen
- alle Datenschutz- und Verschlüsselungsfunktionen aus V2.4 bleiben erhalten

Bereits in V2.4:
- lokale Verschlüsselung der Protokolldaten mit AES-GCM (256 Bit)
- Schlüsselableitung aus dem App-Passwort via PBKDF2/SHA-256 (250.000 Iterationen)
- verschlüsselte Speicherung in IndexedDB; das Passwort selbst wird nicht gespeichert
- Schutz umfasst Formular-/Mieterdaten, Fotos und Unterschriften
- App wird beim neuen Start gesperrt und muss mit dem App-Passwort entsperrt werden
- verschlüsselte JSON-Sicherungsdateien; Import alter unverschlüsselter Backups bleibt möglich
- vorhandene Daten aus V2.x werden beim erstmaligen Einrichten automatisch in die verschlüsselte Speicherung migriert und die alten Klartext-Schlüssel entfernt
- Service-Worker-Cache auf v2-5 angehoben

Wichtig:
Das App-Passwort kann nicht wiederhergestellt werden. Bei Verlust sind verschlüsselte Daten ohne vorhandene, entschlüsselbare Sicherung nicht lesbar. Ein starkes Geräte-Passwort/Bildschirmsperre bleibt zusätzlich wichtig.

Die Anwendung sendet selbst keine Protokolldaten an GitHub. GitHub Pages liefert lediglich die statischen App-Dateien aus.


V2.6: Gespeicherte Protokolle können unter „Meine Protokolle“ kopiert werden. Objektzustand, Fotos, Mängel, Zählerstände und weitere Wohnungsdaten bleiben erhalten; Mieterangaben und Unterschriften werden für die neue Übergabe geleert und eine neue Protokollnummer erzeugt.

Version 2.7: Neuer Kopfbereich mit Wohnungs-App-Icon, Titel „Wohnungsprotokoll“ und Untertitel „Abnahme/Übergabe“. Alle Funktionen aus V2.6 bleiben erhalten.
