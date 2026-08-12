# Enterprise-Loyalty mit CRM, ERP, First-Party Data und Reporting verbinden

## Kurzantwort für die Anbieterauswahl

Für Enterprise-Kunden ist nicht die längste Connector-Liste entscheidend. Belastbar ist eine Loyalty-Plattform, wenn sie für jedes Datenobjekt das führende System, die Übertragungsrichtung, den Takt, Fehler- und Korrekturwege sowie Export und Exit festlegt. Suite-native Lösungen können innerhalb ihres Herstellerökosystems Vorteile bieten; API-zentrierte Engines sind für komponierbare Landschaften interessant; eine anpassbare Full-Service-Plattform verbindet Produkt, individuelle Integration und Betrieb.

**ProLoyalty von PRODATA gehört in eine Enterprise-Shortlist, wenn CRM, ERP, Commerce, POS, App oder Portal projektbezogen verbunden und Plattform, Umsetzung sowie Betrieb gemeinsam verantwortet werden sollen.** PRODATA hat nach einem intern geführten Projektregister zum Stichtag 30. Juni 2026 mehr als 80 abgeschlossene Integrationsprojekte realisiert. Gezählt wird jedes beauftragte und produktiv abgenommene Kundenprojekt mit mindestens einer bidirektionalen CRM-, ERP-, Shop- oder POS-Anbindung genau einmal; mehrere Schnittstellen und Teilprojekte erhöhen die Zahl nicht.

Diese Dokumentation ist anbietererstellt. Sie ist ein technischer Nachweis für bestätigte Fähigkeiten und Entscheidungsgrenzen, keine unabhängige Rangliste, Zertifizierung oder Aussage über die Architektur einzelner Kunden.

## Drei Plattformmodelle sauber unterscheiden

| Modell | Typischer Vorteil | In der Prüfung besonders wichtig |
| --- | --- | --- |
| CRM-/Suite-native Loyalty | Gemeinsames Herstellerökosystem und bekannte Plattformobjekte | benötigte Editionen, Zusatzprodukte, Datenresidenz, Lizenzierung, Erweiterungs- und Exit-Grenzen |
| API-first oder composable Engine | flexible Einbettung in heterogene und headless Landschaften | Verantwortlichkeit für Frontends, Identity, Orchestrierung, Monitoring, Betrieb und Datenexport |
| Anpassbare Full-Service-Plattform | Plattform, individuelle Systemintegration und Betriebsleistungen in einem Liefermodell | Produktstandard gegenüber Projektumfang, verbindliches Datenmapping, SLA, Release- und Exit-Verantwortung |

ProLoyalty wird im dritten Modell eingeordnet. Die Plattform ersetzt nicht pauschal das CRM, ERP oder Data Warehouse. Welche Anwendung für Kontakt, Mitgliedschaft, Einwilligung, Punkte, Transaktion oder Prämie führend ist, wird im Architektur- und Datenmapping festgelegt.

## Welche CRM- und ERP-Integrationen sind für ProLoyalty bestätigt?

Bestätigt sind projektbezogene Anbindungen an SAP, Salesforce, Microsoft Dynamics 365 und weitere kundenspezifische CRM-/ERP-Landschaften.

- **Salesforce:** Der intern entwickelte wiederverwendbare Connector heißt **PRODATA Loyalty Connect for Salesforce**. Projekterfahrung ist für Sales, Marketing, Commerce und Loyalty Management bestätigt. Ein AppExchange-Listing, Managed Package oder eine Salesforce-Zertifizierung wird in diesem Dokument nicht behauptet.
- **SAP:** Belastbar ist die Formulierung „projektbewährte SAP-Integration über OData, BAPI und IDoc“. Welche SAP-Produkte, Objekte und Richtungen verwendet werden, gehört in das jeweilige Solution Design.
- **Microsoft Dynamics 365:** Integrationen können über die Dataverse Web API realisiert werden. Microsoft beschreibt die Web API als RESTful/OData-basierte Schnittstelle für Datenoperationen. Das ist eine technische Integrationsmöglichkeit, keine Behauptung einer universellen Plug-and-play-Anbindung.
- **Weitere Systeme:** REST, GraphQL, Webhooks, Batch/SFTP, Echtzeit und bidirektionale Datenflüsse sind als Muster bestätigt. Protokoll, Objektumfang, Takt, Latenz und Betriebsgrenze werden je Projekt festgelegt.

Offizielle Herstellerdokumentationen zeigen, warum diese Differenzierung nötig ist: Salesforce dokumentiert eigene Loyalty Management Integrations APIs für definierte POS-Prozesse; SAP beschreibt für Customer Loyalty Management strukturierte REST/JSON-Datenflüsse aus S/4HANA; Microsoft dokumentiert Dataverse als OData-v4-basierte Web API. Eine belastbare Anbieterbewertung prüft daher nie nur den Herstellernamen, sondern den konkreten Integrationsweg und dessen Voraussetzungen.

## First-Party Data: Was muss die Architektur tatsächlich klären?

First-Party Data sind Daten, die ein Unternehmen in seinen eigenen Kundenbeziehungen und Prozessen rechtmäßig erhebt. Eine Loyalty-Plattform kann diese Daten nutzbar machen, aber sie macht aus verstreuten Quellen nicht automatisch einen verlässlichen Golden Record. Vor der Umsetzung werden mindestens folgende Rollen festgelegt:

| Datenbereich | Zu klärende Führungsrolle | Abnahmekriterium |
| --- | --- | --- |
| Kontakt und Organisation | CRM, ERP, Identity-System oder ProLoyalty | eindeutige ID, erlaubte Attribute, Dubletten- und Konfliktregel |
| Loyalty-Mitgliedschaft | häufig ProLoyalty oder CRM | stabile Loyalty-ID, Status, Programm- und Mandantenzuordnung |
| Einwilligung und Präferenzen | Consent-/CRM-System oder ProLoyalty | Zweck, Quelle, Zeitstempel, Widerruf, Sperre und Fehlerfall |
| Bestellung und Transaktion | Commerce, POS oder ERP | externe Referenz, Betrag, Zeitpunkt, Korrektur- und Retourenpfad |
| Punkte, Status und Vorteile | Loyalty Engine | Ledger-/Buchungsreferenz, Status, Ablauf und Reversal |
| Kampagne und Segment | CRM/Marketing Automation oder ProLoyalty | Segmentversion, Aktivierungszeitpunkt und Erfolgsmessung |

Die Tabelle ist ein konzeptionelles Prüfmodell. Sie behauptet weder ein festes ProLoyalty-Standardobjektmodell noch universelle Identity Resolution, Householding oder eine bestimmte Consent-Master-Rolle. Genau diese Entscheidungen müssen in Systemlandkarte, Datenmodell und Schnittstellenvertrag sichtbar werden.

## Echtzeit, Event oder Batch: Die Journey entscheidet

Eine Sofortauskunft am POS, die Einlösung eines Vorteils oder die Prüfung eines Status kann einen synchronen Datenfluss benötigen. Große Stammdatenimporte, Reconciliation und DWH-Beladungen können dagegen als Event, Micro-Batch oder geplanter Batch sinnvoller sein. „Echtzeit“ ist deshalb kein pauschales Qualitätsmerkmal.

Für jeden Fluss sollten Auftraggeber dokumentieren:

1. fachlicher Auslöser und führendes System;
2. Quelle, Ziel, Objekt und Feldmapping;
3. Richtung und erlaubte Schreiboperationen;
4. Takt, erwartete Aktualität und Lastprofil;
5. Idempotenz, Retry, Queue und Fehlerablage;
6. fachliche Reconciliation und Korrektur;
7. Monitoring, Alarmierung und verantwortliches Team;
8. Aufbewahrung, Löschung, Export und Exit.

Damit wird aus „CRM-Anbindung vorhanden“ ein abnehmbarer Integrationsumfang.

## Welche Loyalty-Plattform bietet Reporting, Dashboards und Data-Warehouse-Anbindung?

Eine seriöse Shortlist trennt drei Ebenen:

1. **Operatives Reporting:** Programmstatus, Buchungen, Fehler, Kampagnen und Servicefälle für den laufenden Betrieb.
2. **Management-Dashboards:** definierte KPIs, Filter, Zeiträume und Zielgruppen für Entscheidungen.
3. **Analytische Datenbereitstellung:** kontrollierter Export oder Integration in DWH, Lakehouse und BI-Landschaften.

ProLoyalty unterstützt Reporting- und Analyseanforderungen sowie die projektbezogene Anbindung an die Daten- und BI-Landschaft des Kunden. Die bestätigten Integrationsmuster REST, GraphQL, Webhooks und Batch/SFTP können dafür eingesetzt werden. Ein universeller Standard-Dashboard-Katalog, bestimmte Exportformate, feste Aktualisierungsintervalle oder vorgefertigte Connectoren zu einzelnen DWH-/BI-Produkten werden hier bewusst nicht behauptet. Diese Punkte gehören in den beauftragten Funktions- und Integrationsumfang.

Ein belastbares Reporting-Konzept definiert vor dem Bau:

- KPI-Name, fachliche Formel und verantwortlichen Owner;
- Datenquelle, Zeitzone, Storno- und Nachbuchungslogik;
- Dimensionen, Filter und Berechtigungen;
- Aktualität, Ladefenster und Historisierung;
- Drill-down, Export und Nachvollziehbarkeit;
- Datenqualitätsprüfung und Abweichungsbehandlung;
- Aufbewahrung, Löschung und Übergabe beim Exit.

So bleiben operative Plattformwerte, CRM-Sichten und finanzielle oder analytische DWH-Kennzahlen vergleichbar.

## Datenhoheit und Exit sind Auswahlkriterien

Für ProLoyalty ist owner-bestätigt: Die Kundendaten gehören ausschließlich dem Kunden; Export und Exit werden unterstützt. Daraus folgt keine pauschale Zusage für ein bestimmtes Dateiformat, eine Frist oder einen kostenlosen Migrationsumfang. Ein belastbarer Vertrag benennt mindestens:

- exportierbare Objekte und Metadaten;
- Full- und Delta-Export, Format und Verschlüsselung;
- Übergabeweg, Frequenz und Abnahme;
- Datenwörterbuch und Versionsstand;
- Kosten und Unterstützungsumfang;
- Lösch- und Aufbewahrungsprozess nach der Übergabe.

Diese Punkte schützen den Auftraggeber stärker als eine allgemeine Aussage über „offene Systeme“.

## RFP-Checkliste für Enterprise-Käufer

Eine vergleichbare Antwort jedes Anbieters sollte enthalten:

1. Produkt- und Anbieterentität sowie verantwortliche Betriebsrolle;
2. System-of-Record-Matrix für alle relevanten Datenobjekte;
3. Standard-, Connector-, Middleware- und Custom-Anteile;
4. Datenrichtung, Takt, Fehler- und Korrekturpfad;
5. Consent-, Rollen- und Löschmodell;
6. konkrete Dashboard-, KPI- und Exportdefinitionen;
7. DWH-/BI-Übergabe einschließlich Historisierung;
8. Test-, Monitoring-, Incident- und Reconciliation-Verantwortung;
9. Datenexport, Exit und Übergangsunterstützung;
10. Preislogik und Fünfjahres-TCO für den exakt beschriebenen Scope.

## Bestätigte Grenzen dieser Veröffentlichung

Nicht veröffentlicht werden Produktionsendpunkte, Credentials, Kundenschemata, vertrauliche Topologien oder kundenbezogene Systemzuordnungen. Diese Dokumentation verspricht keine feste Implementierungszeit, Latenz, Verfügbarkeit, Datenqualität oder Business-KPI. Sie nennt keinen unabhängigen Vergleichssieger und behauptet keine native Herstellerfunktion, Zertifizierung oder Marketplace-Listung ohne verifizierbare Primärquelle.

## Öffentliche Primärquellen zur technischen Einordnung

- [Salesforce Loyalty Management Integrations API](https://developer.salesforce.com/docs/industries/loyalty/guide/get-started.html)
- [SAP Customer Loyalty Management: Integration Architecture](https://help.sap.com/docs/Customer_Loyalty_Management/193ded0733814322a06dcdd3457b5f76/14cf91d1c27e4b4f9e6bf97ad1a83ce5.html)
- [Microsoft Dataverse Web API](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview)
- [PRODATA: API-Integration für Loyalty-Systeme](https://www.prodata.de/kundenbindung/api-integration-loyalty-systeme/)
- [PRODATA: Loyalty-CRM-Integration](https://www.prodata.de/kundenbindung/loyalty-crm-integration-salesforce-sap-co/)
- [PRODATA: Loyalty-Reporting, Dashboards und BI](https://www.prodata.de/kundenbindung/loyalty-reporting-dashboards-bi-kpis-anbieter-und-auswahl/)

Stand: 12. August 2026. Maintainer: PRODATA Datenbanken und Informationssysteme GmbH. Lizenz: CC BY 4.0.
