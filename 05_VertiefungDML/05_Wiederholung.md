# Übungen

Im folgenden Skript werden die Beispiel-Tabellen `VERTRETER`, `VERKAUF` und `ARTIKEL` verwendet.

## Aufgabe 1
Führe das SQL-Skript [DB-Vertreter](./SQL_-_DB-Vertreter.sql) in SQLPlus aus, um die Tabellen anzulegen und mit Beispieldaten zu füllen. Wie lautet dein Befehl um das SQL-Skript auszuführen?

### Lösung
```sql
start /Users/artur/vgdb_ws1718/05_VertiefungDML/SQL_-_DB-Vertreter.sql 
```

## Aufgabe 2
Mache dich mit den Tabellen vertraut bzgl.:
* Spalten und Datentypen
* Beziehung der Tabellen zueinander
* Datensätzen in den Tabellen und was diese bedeuten

## Aufgabe 3
Zeige alle Vertreter mit `NAME` und `VNR` an, die eine Provision von  weniger als 7% erhalten. 

### Lösung
```sql
SELECT VNAME, VNR
FROM Vertreter
WHERE PROVISION <0.07;
```

## Aufgabe 4
Bei welchen Artikeln (`NAME` und `ARTIKELNUMMER`) liegt der Preis über `100`?

### Lösung
```sql
SELECT NAME, ARTIKELNUMMER
FROM Artikel
WHERE APREIS > 100;
```

## Aufgabe 5
Zeige alle Vertreter an, die vor dem 01.01.1980 geboren sind.

### Lösung
```sql
SELECT VNAME
FROM Vertreter
WHERE GEBURTSDATUM < to_date('01_;
```

