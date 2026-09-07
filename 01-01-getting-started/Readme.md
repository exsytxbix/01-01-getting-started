# Git
### Kontrollfragen

- Was bedeutet das **U** bzw. das **M** neben einer Datei in der Quellcodeverwaltung?
- Warum braucht jeder Commit eine Nachricht?
- Welchen Git-Befehlen entsprechen die Buttons **Repository initialisieren**, **+** und **Commit**?

## GitHub per SSH verbinden - ganz einfach

SSH ist eine sichere Verbindung zwischen deinem Computer und GitHub. Du musst dein Passwort dann nicht bei jedem `push` eingeben.

### 1. Neues Repository auf GitHub erstellen

1. Gehe zu [github.com](https://github.com) und melde dich an.
2. Klicke oben rechts auf **+** und dann auf **New repository**.
3. Vergib einen Namen, z. B. `mein-erstes-repo`.
4. Klicke auf **Create repository**.
5. Lasse **README**, `.gitignore` und **License** zunächst leer. Dein lokales Projekt hat bereits Dateien.

### 2. SSH-Schlüssel erstellen

Öffne in VS Code das Terminal über **Terminal -> Neues Terminal** und führe diesen Befehl aus. Ersetze die E-Mail-Adresse durch die E-Mail-Adresse deines GitHub-Kontos:

```bash
ssh-keygen -t ed25519 -C "deine-email@example.com"
```

Drücke bei der Frage nach dem Speicherort einfach **Enter**. Danach kannst du ein Passwort für den Schlüssel festlegen. Wenn du keines möchtest, drücke zweimal **Enter**.

### 3. SSH-Schlüssel bei GitHub hinterlegen

Starte den SSH-Agenten und füge deinen Schlüssel hinzu:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Kopiere nun deinen öffentlichen Schlüssel in die Zwischenablage:

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

Gehe anschließend auf GitHub zu **Profilbild -> Settings -> SSH and GPG keys -> New SSH key**. Vergib bei **Title** z. B. `Mein Mac`, füge den kopierten Schlüssel bei **Key** ein und klicke auf **Add SSH key**.

### 4. Verbindung testen

```bash
ssh -T git@github.com
```

Beim ersten Mal fragt GitHub, ob du der Verbindung vertraust. Tippe `yes` und drücke **Enter**. Eine Nachricht wie `Hi dein-benutzername!` bedeutet, dass die Verbindung funktioniert.

### 5. Lokales Repository mit GitHub verbinden

Ersetze `DEIN-BENUTZERNAME` und `mein-erstes-repo` durch deine eigenen Werte. Führe die Befehle im Projektordner aus:

**So findest du die beiden Werte:**

- **Benutzername:** Klicke auf GitHub oben rechts auf dein Profilbild. Dein Benutzername steht unter deinem Namen und auch in deiner Profiladresse, zum Beispiel `github.com/tobias123`.
- **Repository-Name:** Öffne auf GitHub dein Repository. Der Name steht oben auf der Seite, zum Beispiel `mein-erstes-repo`. Er ist normalerweise auch der Name deines lokalen Projektordners.
- **Am einfachsten:** Öffne dein Repository auf GitHub, klicke auf **Code**, wähle **SSH** und klicke auf das Kopier-Symbol. Dann musst du den SSH-Link nicht selbst zusammensetzen.

```bash
git remote add origin git@github.com:exsytxbix/01-01-getting-started.git
git branch -M main
git push -u origin main
```

Danach ist dein lokales Repository mit GitHub verbunden. Weitere Änderungen kannst du normalerweise so hochladen:

```bash
git add .
git commit -m "Beschreibung der Änderung"
git push
```

Den SSH-Link findest du auf der GitHub-Seite deines Repositorys über **Code -> SSH**. Er sieht ungefähr so aus:

```text
git@github.com:exsytxbix/01-01-getting-started.git
```
Test am 7.9.