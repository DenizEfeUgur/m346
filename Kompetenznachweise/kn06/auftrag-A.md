# Hochverfügbarkeit (HA) - Massnahmen für Stromausfall und Erdbeben

#### Stromausfall

1. **Unabhängige Stromversorgung:**
   - Implementieren von mehreren Stromquellen

2. **Verteilung auf mehrere Standorte:**
   - Nutzung von Multi-Availability-Zonen.

3. **Automatisierung und Failover:**
   - Verwenden von AWS Auto Scaling und Elastic Load Balancing für automatisierte Failover-Mechanismen.

#### Erdbeben

1. **Geografische Diversifizierung:**
   - Verteilung der Infrastruktur auf geografisch stabile Gebiete.

2. **Ressourcenreplikation:**
   - Implementieren von Datenreplikationstechniken zwischen Regionen.

3. **Datacenter-Hardening:**
   - Stärkung von Rechenzentren in erdbebengefährdeten Gebieten durch Sicherheitsmassnahmen und bauliche Verbesserungen.

# Redundanzmassnahmen zur Steigerung der Fault Tolerance

#### Ich würde die Redundanz einführen, aus den Folgenden Gründen:

In einem kleinen Serverraum ist es ratsam, grundlegende Redundanzen zu implementieren. Dies könnte die Verwendung von, redundante Stromversorgung durch USVs, sowie die Sicherung der Daten auf externen Speichermedien umfassen. Diese Massnahmen sind kostengünstiger und leichter zu verwalten.

# AWS Load Balancer

Ein AWS Load Balancer ist ein verwalteter Dienst von Amazon Web Services, der den Datenverkehr auf mehrere EC2-Instanzen oder andere Ressourcen in Ihrer AWS-Infrastruktur verteilt. Die Hauptfunktionen eines AWS Load Balancers im Kontext von AWS sind:

- Verteilung des Datenverkehrs
- Hochverfügbarkeit
- Skalierbarkeit
- Session Persistence

### Verschiedene Typen von AWS Load Balancern

1. **Application Load Balancer (ALB):** Ein Layer-7-Load-Balancer für HTTP und HTTPS-Verkehr.
2. **Network Load Balancer (NLB):** Ein Layer-4-Load-Balancer für TCP- und UDP-Verkehr.
3. **Classic Load Balancer:** Die ältere Version des Load Balancers, wird nicht mehr aktiv weiterentwickelt.

### Kombination von Auto Scaling und Load Balancern

AWS Auto Scaling ermöglicht die automatische Anpassung von EC2-Instanzen basierend auf der Last. In Kombination mit einem Load Balancer kann Auto Scaling die Skalierbarkeit und Verfügbarkeit Ihrer Anwendungen verbessern.

### Sicherheitsmassnahmen und Best Practices für Load Balancer

- Implementieren Sie Web Application Firewall (WAF) in Verbindung mit einem Application Load Balancer.
- Aktivieren Sie SSL/TLS für Verschlüsselungsschutz.
- Konfigurieren Sie Zugriffssteuerungen, um unberechtigten Zugriff zu verhindern.

### Leistungsüberwachung und Optimierung von Load Balancern

- Verwenden Sie AWS CloudWatch, um die Leistung des Load Balancers zu überwachen.
- Nutzen Sie Auto Scaling, um die Kapazität automatisch anzupassen.

Die effektive Verwendung von AWS Load Balancern in Kombination mit den richtigen Sicherheitsmassnahmen und Überwachungstools ist entscheidend, um die Skalierbarkeit, Verfügbarkeit und Sicherheit Ihrer Anwendungen in der AWS-Cloud zu gewährleisten.

# AWS Auto Scaling

AWS Auto Scaling ist ein verwalteter Dienst von Amazon Web Services, der entwickelt wurde, um die Skalierbarkeit von Anwendungen und Workloads in der AWS-Cloud zu optimieren. Die Hauptfunktion von AWS Auto Scaling ist es, die Anzahl der bereitgestellten Amazon EC2-Instanzen automatisch zu erhöhen oder zu verringern, um die Anforderungen an die Anwendung zu erfüllen. Dies ermöglicht die Bereitstellung der richtigen Menge an Ressourcen zur richtigen Zeit, um die Leistung und die Kostenoptimierung zu gewährleisten.

### Arten von Richtlinien in AWS Auto Scaling

1. **Zielverfolgung:** Diese Richtlinie basiert auf einem Zielwert für eine bestimmte Metrik, wie z. B. die CPU-Auslastung oder die Anzahl der Anfragen pro Sekunde. AWS Auto Scaling passt die Anzahl der Instanzen an, um das Ziel zu erreichen.

2. **Zeitpläne:** Sie können Zeitpläne erstellen, um Instanzen zu bestimmten Zeiten oder nach einem Zeitplan hinzuzufügen oder zu entfernen. Dies ist nützlich für saisonale Workloads oder geplante Wartungsfenster.

3. **Ereignisbasiert:** Mit ereignisbasierten Richtlinien können Sie Aktionen auslösen, basierend auf bestimmten CloudWatch-Ereignissen oder benutzerdefinierten Skalierungsrichtlinien.

### Warum ist AWS Auto Scaling nützlich für die Kostenoptimierung

- Es ermöglicht die Anpassung der Ressourcen an die aktuelle Nachfrage, wodurch unnötige Kosten für überdimensionierte Ressourcen vermieden werden.
- Durch die automatische Skalierung können Sie Ressourcen nach Bedarf hinzufügen und entfernen, was die Betriebskosten senkt.
- Es ermöglicht eine optimale Ressourcenauslastung und minimiert Verschwendung.

### Rolle von Elastic Load Balancing (ELB) in Verbindung mit AWS Auto Scaling

Elastic Load Balancing (ELB) ist ein wichtiger Bestandteil von AWS Auto Scaling. ELB verteilt den eingehenden Datenverkehr auf die EC2-Instanzen in einer Auto Scaling-Gruppe. In Kombination mit Auto Scaling gewährleistet ELB eine gleichmäßige Verteilung des Datenverkehrs auf die Instanzen, während Auto Scaling die Anzahl der Instanzen entsprechend der Last erhöht oder verringert. Dies sorgt für eine bessere Verfügbarkeit und Leistung von Anwendungen, da die Last auf die Instanzen je nach Bedarf skaliert wird.

