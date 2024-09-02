# Skriptbeschreibung

Dieses Skript dient dazu, eine TPCC (Transaction Processing Performance Council)-Benchmark-Datenbank auf einem Microsoft SQL Server einzurichten und zu befüllen. Der TPCC-Benchmark wird häufig verwendet, um die Leistungsfähigkeit von OLTP-Systemen (Online Transaction Processing) zu bewerten. Das Skript automatisiert die Erstellung des Datenbankschemas, füllt die Tabellen mit Beispieldaten und erstellt gespeicherte Prozeduren, die für die Ausführung des TPCC-Benchmarks erforderlich sind.

## Voraussetzungen

- **TCL 8.6 oder höher**
- **tdbc::odbc-Modul** für die Datenbankverbindung
- **Microsoft SQL Server** (empfohlen ab Version 2016)
- **ODBC-Treiber 17/18 für SQL Server**

## Funktionen

- **Datenbankerstellung**: Erstellt automatisch die TPCC-Datenbank und alle erforderlichen Tabellen.
- **Datenladung**: Unterstützt das schnelle Einfügen großer Datenmengen in Tabellen mittels BCP (Bulk Copy Program).
- **In-Memory-Unterstützung**: Optionales Erstellen von Tabellen als In-Memory-Tabellen zur Leistungssteigerung.
- **Mehrthreading**: Unterstützt mehrthreadige Dateneinfügung zur Beschleunigung des Prozesses.
- **Gespeicherte Prozeduren**: Generiert und installiert automatisch TPCC-spezifische gespeicherte Prozeduren für die Transaktionsverarbeitung.
- **Statistikaktualisierung**: Aktualisiert automatisch die Datenbankstatistiken, um die Abfrageleistung zu optimieren.

## Installationsanweisungen

### Installiere TCL und erforderliche Module
Stelle sicher, dass TCL 8.6 oder höher installiert ist, zusammen mit dem tdbc::odbc-Modul.

### Bereite den SQL Server vor
Stelle sicher, dass deine SQL Server-Instanz läuft und zugänglich ist. Du solltest über Administratorrechte verfügen, um Datenbanken zu erstellen und BCP-Befehle auszuführen.

### Konfiguriere das Skript
Passe die Parameter im Skript nach Bedarf an:

```tcl
server: Hostname oder IP-Adresse des SQL Servers.
port: Portnummer der SQL Server-Instanz (Standard ist 1433).
odbc_driver: Version des ODBC-Treibers (z.B. "ODBC Driver 18 for SQL Server").
authentication: Authentifizierungsmethode ("windows", "sql" oder "entra").
uid und pwd: Benutzername und Passwort für die SQL-Authentifizierung.
