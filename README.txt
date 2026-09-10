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

Version 2.8: 12-Stunden-Arbeitssitzung (Passwort nur einmal pro Sitzung), manueller „Sperren“-Button und automatischer Zeitstempel beim Unterschreiben. Keine Adress-Automatik, Name bleibt Wohnungsprotokoll.

Version 2.9: 12-Stunden-Freigabe bleibt über vollständiges Schließen der PWA erhalten; manueller Sperren-Button löscht sie sofort. Neue schreibgeschützte Protokoll-Vorschau vor der Unterschrift. Hinweis: Die persistente 12h-Freigabe ist komfortabler, reduziert während dieses Zeitfensters aber den zusätzlichen Schutz gegenüber einer erneuten Passworteingabe.

V3.0: Korrigierte 12-Stunden-Freigabe über App-Neustarts. Das Passwort wird dafür NICHT gespeichert; stattdessen wird der nicht exportierbare WebCrypto-Schlüssel mit Ablaufzeit lokal in IndexedDB gehalten. Manueller Sperren-Button löscht ihn. Sichtbarer Vorschau-Button in der unteren Leiste.

V3.1: Vorschau vollständig überarbeitet. Sie zeigt nun eine schreibgeschützte Bildschirmansicht im gleichen Drucklayout wie die spätere PDF-/Druckausgabe, statt einer separaten Zusammenfassung.

V3.2: Jeder Raum hat einen Schalter „Raum nicht vorhanden“. Solche Räume werden in Vorschau und PDF vollständig ausgeblendet. Alte Protokolle werden automatisch erkannt, wenn alle Prüfpunkte eines Raums auf „n.v.“ stehen und keine weiteren Inhalte vorhanden sind. In der Vorschau wird der gewählte Zustand (i.O., Mangel oder n.v.) als Text sichtbar angezeigt.

V3.3: Abstellraum und Keller sind getrennte Räume. Zusätzlich gibt es „Weiteres Zimmer 1“ und „Weiteres Zimmer 2“. Beide zusätzlichen Räume können über das Feld „Raumbezeichnung“ individuell benannt werden; der eigene Name erscheint in Vorschau und PDF.

V3.4: 12-Stunden-Komfortfreigabe korrigiert. Nach einer erfolgreichen Passworteingabe kann die installierte PWA auch nach vollständigem Schließen innerhalb von 12 Stunden automatisch entsperren. Technischer Hinweis: Damit dies in einer normalen Browser-PWA zuverlässig über Prozess-Neustarts funktioniert, wird das App-Passwort während dieses Zeitfensters lokal im Browser-Speicher gehalten. „Sperren“ und der Ablauf der 12 Stunden löschen diese Freigabe. Das ist bewusst ein Komfort-/Sicherheits-Kompromiss; die Protokolldaten bleiben verschlüsselt gespeichert.

V3.5: Startfehler der 12-Stunden-Freigabe behoben. Beim App-Start wird jetzt zuerst die gespeicherte, noch gültige Freigabe geprüft. Nur wenn keine gültige Freigabe vorhanden ist, erscheint die Passwortabfrage.

V3.6: Vorschau zeigt Art des Protokolls und gewählten Allgemeinzustand als Text. Bei Übergabe heißt das Adressfeld „Adresse“, bei Abnahme „Neue Adresse“. Telefon und E-Mail wurden ergänzt. Für Strom- und Wasserzähler können Fotos aufgenommen, verschlüsselt gespeichert und in Vorschau/PDF angezeigt werden; Heizkostenverteiler bleiben ohne Fotofunktion.

V3.7: Der blaue gebrandete Kopfbereich mit Wohnungsprotokoll-Icon, Titel, Eigentümer und Domoconzept wird wieder in PDF-Vorschau und PDF/Druck angezeigt. Kompakte A4-Darstellung; alle Funktionen aus V3.6 bleiben erhalten.

V3.8: Raum- und Mängelfotos werden vollständig und proportional ohne Beschnitt dargestellt. Die quadratische Zwangsdarstellung und object-fit: cover wurden entfernt. Zählerfotos bleiben unverändert.

V3.9: In PDF und PDF-Vorschau werden bei Zählerständen und Heizkostenverteilern nur tatsächlich erfasste Einträge angezeigt. Leere Platzhalterzeilen bleiben in der App zur Eingabe sichtbar, werden in der Ausgabe aber ausgeblendet.
