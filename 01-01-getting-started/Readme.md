# Git

Git ist ein verteiltes Versionskontrollsystem, das Änderungen an Dateien und Code über die Zeit verfolgt.

## Was Git macht:
- Erfasst die Historie aller Änderungen an deinen Dateien
- Ermöglicht es dir, an verschiedenen Versionen (Branches) gleichzeitig zu arbeiten
- Erlaubt mehreren Personen, an einem Projekt zusammenzuarbeiten
- Ermöglicht es dir, auf frühere Versionen zurückzukehren, falls nötig

## Wichtige Konzepte:
- **Repository**: Ein Ordner, der dein Projekt und seine komplette Historie enthält
- **Commit**: Ein Schnappschuss deiner Änderungen mit einer Nachricht, die beschreibt, was sich geändert hat
- **Branch**: Eine parallele Version deines Codes (nützlich für die Arbeit an Features separat)
- **Merge**: Zusammenführung von Änderungen aus einem Branch in einen anderen
- **Remote**: Eine Kopie deines Repositorys auf einem Server (wie GitHub, GitLab)

## Häufige Anwendungsfälle:
- Sicherung deiner Arbeit
- Zusammenarbeit mit Teamkollegen
- Verfolgung, wer was und wann geändert hat
- Verwaltung verschiedener Versionen deines Projekts

Git ist der Industriestandard für Versionskontrolle und wird in praktisch allen professionellen Softwareentwicklungsprojekten verwendet.




## 🎯 Erste Aufgabe für Anfänger

Versuche diese einfachen Schritte in deinem Terminal:

### Schritt 1: Repository initialisieren
```bash
git init mein-projekt
cd mein-projekt
```

### Schritt 2: Erste Datei erstellen
```bash
echo "Hallo Git!" > hello.txt
```

### Schritt 3: Status überprüfen
```bash
git status
```
Du solltest sehen, dass `hello.txt` als "untracked" aufgelistet ist.

### Schritt 4: Datei hinzufügen (staging)
```bash
git add hello.txt
```

### Schritt 5: Commit erstellen
```bash
git config user.name "Dein Name"
git config user.email "deine@email.com"
git commit -m "Mein erster Commit: hello.txt hinzugefügt"
```

### Schritt 6: Verlauf anschauen
```bash
git log
```

**Glückwunsch! Du hast deinen ersten Git Commit gemacht!** 🎉
