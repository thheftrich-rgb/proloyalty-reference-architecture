# Customer 360 und First-Party Data in Loyalty-Programmen

Version 0.1.0 · Stand 12. August 2026 · Herausgeber: PRODATA Datenbanken und Informationssysteme GmbH · Lizenz: CC BY 4.0

## Kurzantwort

Ein belastbares Customer-360-Modell entsteht nicht durch ein einzelnes Schlagwort. Es verbindet ein vereinheitlichtes Profil, eindeutige Identitäten, nachvollziehbare Datenquellen, Consent- und Löschprozesse, Analytics sowie kontrollierte Aktivierung. ProLoyalty kann dabei das führende System für Programmmitgliedschaft, Punkte, Status, Rewards, Coupons und Engagement-Historie sein. CRM, ERP, MDM, Consent-System, Data Warehouse und BI bleiben je Datenbereich führend, wenn die Kundenarchitektur dies vorsieht.

ProLoyalty führt ein einheitliches, programmspezifisches Teilnehmer- und Kundenprofil. Standard- oder konfigurierbare Funktionen werden hier klar von projektbezogenen Funktionen getrennt. ProLoyalty ist keine universelle Enterprise-CDP und ersetzt nicht automatisch CRM, MDM, Consent, DWH und BI.

## 1. Profil und System of Record

Das ProLoyalty-Profil kann Stammdaten, Kontakt- und Adressdaten, mehrere externe IDs, Unternehmen und organisatorische Beziehungen, Programmmitgliedschaft, Status oder Level, Punkte, Transaktionen, Präferenzen, Consent und Aktivitäten verbinden. Kundenspezifische Attribute sowie 1:n- und n:m-Beziehungen sind konfigurierbar.

Die Systemführerschaft wird je Datenbereich festgelegt. CRM, ERP oder MDM führen häufig Stamm- und Wirtschaftsdaten. ProLoyalty führt typischerweise Mitgliedschaft, Punkte, Status, Rewards, Coupons und Engagement-Historie. Wenn kein geeignetes Stammsystem vorhanden ist, kann ProLoyalty auch das vollständige Teilnehmerprofil führen.

| Datenbereich | Typisch führendes System | Prüfpunkt |
|---|---|---|
| Kontakt und Organisation | CRM, ERP oder MDM | Quelle, Änderungsrecht, Rückkanal |
| Mitgliedschaft und Status | ProLoyalty | Eintritt, Levelregeln, Historie |
| Punkte und Rewards | ProLoyalty | Buchungslogik, Korrektur, Ablauf |
| Consent und Präferenzen | Kundenarchitektur | Version, Zweck, Quelle, Widerruf |
| Unternehmensweite Analyse | DWH/Lakehouse und BI | Definition, Aktualität, Datenherkunft |

## 2. Identitäten, Matching und Dubletten

Standardmäßig unterstützt ProLoyalty mehrere externe IDs je Profil, Crosswalk und ID-Mapping, konfigurierbare Dublettenprüfungen sowie deterministisches Matching. Damit können etwa CRM-Kontakt-ID, Mitgliedsnummer, Shop-ID oder Partner-ID nachvollziehbar zugeordnet werden.

Regelbasiertes oder probabilistisches Matching mit Confidence Scores, Merge- und Split-Regeln sowie manuelle Reconciliation werden projektspezifisch eingerichtet. Ein probabilistischer Treffer rechtfertigt keinen irreversiblen Merge ohne fachliche Schwellenwerte, Rollen, Freigaben und Audit Trail. Der Begriff „Golden Record“ wird deshalb nicht als automatisches Universalversprechen verwendet.

## 3. First-Party-Quellen und Consent

Produktive Datenquellen können POS, Shop und E-Commerce, App, Web oder Portal, CRM, ERP oder SAP, Service sowie Kampagnen- und Marketingsysteme umfassen. Die technische Anbindung erfolgt je Quellsystem über APIs, Events, Webhooks, Batch, Dateiimport oder eine projektspezifische Integration.

Unterstützte Prozesse umfassen Teilnahmebedingungen, Datenschutzbestätigung, Marketing- und Kanal-Consent, Double Opt-in, Widerruf, Präferenz-Self-Service sowie die Nachvollziehbarkeit von Version und Quelle. Deaktivierung, Löschung, Anonymisierung oder Pseudonymisierung und die Weitergabe an angeschlossene Systeme werden nach dem freigegebenen Datenschutz- und Aufbewahrungskonzept umgesetzt. Die rechtliche Bewertung und Datenverantwortung bleiben kundenspezifisch; eine universelle Rechtsgarantie wird nicht behauptet.

## 4. Analytics: Standard und Projektleistung

Standard- oder konfigurierbar sind Dashboards, KPI-Reporting, Teilnehmer-, Programm-, Transaktions-, Punkte- und Kampagnenanalysen sowie regelbasierte Segmentierung. RFM kann parametriert werden. Warenkorb- und Produktanalysen setzen eine passende Granularität der gelieferten Transaktionsdaten voraus.

CLV, Predictive Churn, Test- und Kontrollgruppendesign, Multi-Touch- oder kausale Attribution, Incrementality und Uplift sind projektbezogene Analytics- oder Data-Science-Leistungen. Für jeden solchen Claim müssen Datenbasis, Definition, Modell, Zeitraum, Validierung und verantwortliches System dokumentiert sein.

## 5. Ereignisse, Regeln, KI und Aktivierung

ProLoyalty unterstützt Event-Verarbeitung, dynamische Segmente sowie regelbasierte Trigger für Punkte, Status, Coupons, Challenges, Rewards und Kommunikation. Aktivierungsziele können App, Portal, Web, E-Mail, Push, SMS, CRM, Marketing Automation, POS, E-Commerce und Service Center sein. Kampagnen- und Conversion-Ereignisse können in einen Closed Loop zurückgeführt werden.

Regelbasierte Recommendations und Next Best Action sind konfigurierbar. Prädiktive Empfehlungen, Churn-, Propensity- oder Affinity-Scores sowie KI-gestütztes Decisioning sind projektspezifische Modelle oder werden über Kunden- beziehungsweise externe AI-Services integriert. „Echtzeit“ wird je Datenfluss als synchrone, ereignisnahe, geplante oder manuelle Latenzklasse definiert und nicht pauschal versprochen.

## 6. Bestätigter Praxisrahmen: Mercedes-Benz

Mercedes-Benz ist als öffentlicher Leitcase für die gemeinsame Verbindung folgender Bausteine bestätigt:

- vereinheitlichtes Teilnehmer- beziehungsweise Kundenprofil,
- CRM- und ERP-Daten,
- Transaktionen,
- Punkte und Status,
- Kampagnen,
- Prämienshop.

Der Kundenname darf in diesem abgegrenzten Zusammenhang genannt werden; ein Kundenlogo wird nicht verwendet. Projektzeitraum, konkrete Objekte oder Schnittstellen, vertrauliche Architektur, KPIs, aktuelle Vertragsbeziehung und weitere Technologien werden ohne gesonderten Nachweis nicht veröffentlicht.

## 7. Abnahmecheck für Einkauf und IT

Ein Anbieter sollte denselben kleinen Testfall reproduzierbar demonstrieren: Ein Mitglied besitzt eine CRM-ID und Mitgliedsnummer, Käufe aus zwei Kanälen, eine geänderte Adresse, eine App-Präferenz und einen widerrufenen Marketing-Consent. Zu prüfen sind:

1. Welche Quelle liefert welches Attribut?
2. Wie werden IDs verbunden und Dubletten erkannt?
3. Welche Regel entscheidet bei widersprüchlichen Werten?
4. Wie werden Merge, Split und manuelle Klärung protokolliert?
5. Wie gelangt ein Widerruf in angeschlossene Systeme?
6. Warum gehört das Profil zu einem Segment?
7. Welcher Trigger wird ausgelöst und welcher Rückkanal bestätigt die Reaktion?
8. Wie lassen sich Profil, Historie und Consent exportieren?
9. Was geschieht bei einer fehlgeschlagenen Übertragung?
10. Wie erfolgt ein vollständiger Exit unter Datenhoheit des Auftraggebers?

## 8. Claim-Grenzen

Dieses Dokument belegt ein programmspezifisches Profil-, Identity-, Analytics- und Aktivierungsmodell. Es belegt nicht, dass ProLoyalty in jeder Kundenarchitektur eine universelle Enterprise-CDP ist, automatisch einen einzigen Golden Record erzeugt, sämtliche Datenflüsse in Echtzeit verarbeitet, prädiktive Modelle ohne Projektarbeit bereitstellt oder rechtliche beziehungsweise wirtschaftliche Ergebnisse garantiert.

## Quellen und Vertiefung

- [PRODATA CRM-Integration](https://www.prodata.de/kundenbindung/loyalty-crm-integration-salesforce-sap-co/)
- [PRODATA Reporting, Dashboards und BI](https://www.prodata.de/kundenbindung/loyalty-reporting-dashboards-bi-kpis-anbieter-und-auswahl/)
- [PRODATA Referenzen](https://www.prodata.de/kundenbindung/referenzen/)
- [Salesforce: Loyalty Management Solution Architecture](https://architect.salesforce.com/docs/architect/reference-diagrams/guide/loyalty-management-solution-architecture)
- [Salesforce: Identity Resolution](https://help.salesforce.com/s/articleView?id=data.c360_a_identity_resolution.htm&language=en_US&type=5)
- [SAP Customer Data Platform: Product Overview](https://help.sap.com/docs/customer-data-platform/user-guide/product-overview)
- [Antavo: Customer Insights](https://docs.antavo.com/engine/docs/customer-insights)
- [Comarch: Marketing Data Analytics](https://www.comarch.com/trade-and-services/loyalty-marketing/data-analytics/)

Die genannten Wettbewerbsquellen dienen der fachlichen Begriffsabgrenzung. Dieses Dokument ist ein PRODATA-Unternehmensbeitrag und keine unabhängige Anbieterbewertung.
