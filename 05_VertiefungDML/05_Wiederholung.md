# Übungen

Im folgenden Skript werden die Beispiel-Tabellen `VERTRETER`, `VERKAUF` und `ARTIKEL` verwendet.

## Aufgabe 1
Führe das SQL-Skript [DB-Vertreter](./SQL_-_DB-Vertreter.sql) in SQLPlus aus, um die Tabellen anzulegen und mit Beispieldaten zu füllen. Wie lautet dein Befehl um das SQL-Skript auszuführen?

### Lösung
```sql
start /Users/artur/vgdb_ws1718/05_VertiefungDML/SQL_-_DB-Vertreter.sql 

INSERT INTO Vertreter
   values (2345, 'Peter', to_date('01.06.1995', 'dd.mm.yyyy'), 8.1);
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
WHERE GEBURTSDATUM < to_date('01.01.1980', 'dd.mm.yyyy')
AND VNAME LIKE '%a%';  
```

## Aufgabe 6
Füge dich als Vertreter in die Tabelle Vertreter ein mit einer Mitarbeiternummer 7777.

### Lösung
```sql
INSERT INTO Vertreter
   values (7777, 'Galiev', to_date('01.06.1995', 'dd.mm.yyyy'), 0.06);
```

## Aufgabe 7
Füge für deinen Vertreter einen Verkauf mit UNR 1014 hinzu. 
Der neue Datensatz soll abbilden, dass heute 22 Wintermäntel vom Vertreter mit VNR 7777 verkauft wurden.

### Lösung
```sql
INSERT INTO Verkauf
   values (1014, 7777, 10, 22, to_date('27.09.2017', 'dd.mm.yyyy'));
```

## Aufgabe 8
Ändere den Preis eines Stiefels auf 88,90.

### Lösung
```sql
UPDATE Artikel
SET APREIS = 88,90
ANAME = 'Stiefel';

```

## Aufgabe 9
Füge der Tabelle Vertreter eine Spalte bonus hinzu, in die ein bis zu vierstelliger, ganzzahliger Wert eingetragen werden soll.

### Lösung
```sql
ALTER TABLE Vertreter
ADD (bonus NUMBER(4));

```

## Aufgabe 10
Setze den Bonus für alle Vertreter auf 500.

### Lösung
```sql
ALTER TABLE Vertreter
ADD (bonus NUMBER(4));

```
