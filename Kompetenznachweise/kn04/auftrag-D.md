# Auftrag D

## AWS Storage-Optionen

**EBS (Elastic Block Store) - Block-Storage:**

- **Persistenz:** Ja
- **Geschwindigkeit:** Hoch (abhängig von der gewählten EBS-Instanz)
- **Sicherheit:** Datensicherheit durch Verschlüsselung und Zugriffskontrollen
- **Standort:** Verfügbar in einzelnen AWS-Regionen
- **Weitere Charakteristiken:** Skalierbar, für virtuelle Maschinen geeignet

**S3 (Simple Storage Service) - Object-Storage:**

- **Persistenz:** Ja
- **Geschwindigkeit:** Variabel (abhängig von der Zugriffsklasse)
- **Sicherheit:** Objektverschlüsselung und Zugriffskontrollen
- **Standort:** Global verteilt (in verschiedenen AWS-Regionen)
- **Weitere Charakteristiken:** Skalierbar, für unstrukturierte Daten und Dateien geeignet

**EFS (Elastic File System) - File-Storage:**

- **Persistenz:** Ja
- **Geschwindigkeit:** Mittel bis Hoch (abhängig von der Instanztyp)
- **Sicherheit:** Zugriffskontrollen und Dateisystemverschlüsselung
- **Standort:** Verfügbar in einzelnen AWS-Regionen
- **Weitere Charakteristiken:** Netzwerkdateisystem, für gemeinsam genutzte Dateien geeignet

**Use-Cases:**

1. **EBS:** EBS eignet sich gut für den Einsatz als persistenter Blockspeicher für Amazon EC2-Instanzen. Zum Beispiel, um eine relationale Datenbank auf EC2 zu hosten, da sie hohe Geschwindigkeiten und Datensicherheit bietet.

2. **S3:** S3 ist ideal für die Speicherung von Daten wie Medieninhalten, Backups und Datenanalysen. Zum Beispiel, für die Archivierung von Bildern, Videos und Log-Dateien in einer skalierbaren, sicheren und globalen Umgebung.

3. **EFS:** EFS eignet sich gut für Anwendungsfälle, in denen mehrere EC2-Instanzen auf gemeinsame Dateien zugreifen müssen. Zum Beispiel, für Webserver-Cluster, die Dateien für eine Webseite hosten und gemeinsam darauf zugreifen müssen.

<hr>

### Quelle
- [chatGPT](https://chat.openai.com/)