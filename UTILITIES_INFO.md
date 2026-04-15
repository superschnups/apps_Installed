# 📂 Dienstprogramme (Utilities) - Info

## Was ist das?

Diese Liste erfasst alle Apps und Tools im macOS Dienstprogramme-Ordner:
```
/Applications/Utilities/
```

## Automatische Erstellung

Die Liste wird **automatisch alle 3 Tage** zusammen mit dem Hauptinventar erstellt.

**Dateiname:** `utilities_dienstprogramme_DD.MM.YYYY.md`

## Inhalt

Die Liste zeigt:
- **App Name** - Der Name der Anwendung/des Tools
- **Typ** - Ob es sich um eine App, einen Alias (Verknüpfung) oder ein Tool handelt

## Wichtiger Hinweis

⚠️ **Die meisten Einträge sind Aliase (Verknüpfungen)** zu Apps im Hauptordner `/Applications/`.

Das bedeutet:
- Die eigentliche App ist bereits im Hauptinventar (`installed_apps_*.md`) erfasst
- Der Dienstprogramme-Ordner enthält nur Verknüpfungen für schnellen Zugriff
- Bei einer Neuinstallation werden die Apps über das Hauptinventar installiert

## Typische Einträge

### System-Apps (macOS vorinstalliert)
- **Activity Monitor** (Aktivitätsanzeige)
- **Console** (Konsole)
- **Terminal**
- **Disk Utility** (Festplattendienstprogramm)
- **System Information** (Systeminformationen)

### Benutzerdefinierte Aliase
Viele Benutzer erstellen hier Aliase zu häufig genutzten Tools:
- **Visual Studio Code**
- **GitHub Desktop**
- **Cryptomator**
- etc.

## Verwendung bei Neuinstallation

### Schritt 1: Apps installieren
Verwenden Sie zuerst das Restore-Script für das Hauptinventar:
```bash
~/bin/restore_apps.sh ~/Documents/apps_installed_16.11.2025/apps_installed_mac_homebrew_applite/installed_apps_16.11.2025.md
```

### Schritt 2: Utilities überprüfen
Nach der Installation können Sie die `utilities_dienstprogramme_*.md` Liste als **Referenz** nutzen:
- Prüfen Sie, ob Sie spezielle Aliase im Dienstprogramme-Ordner hatten
- Erstellen Sie diese Aliase bei Bedarf manuell neu

### Aliase manuell erstellen (falls gewünscht)

**Beispiel:** Visual Studio Code Alias im Utilities-Ordner erstellen:

```bash
# Prüfen ob die App existiert
ls -la "/Applications/Visual Studio Code.app"

# Alias erstellen
ln -s "/Applications/Visual Studio Code.app" "/Applications/Utilities/Visual Studio Code Alias"
```

## Manuelle Ausführung

Das Utilities-Inventar wird automatisch vom Hauptscript erstellt. 

Falls Sie es manuell ausführen möchten:
```bash
~/bin/inventory_apps.sh
```

Dies erstellt beide Listen:
- `installed_apps_*.md` (Hauptinventar)
- `utilities_dienstprogramme_*.md` (Utilities)

## Zusammenfassung

📝 **Zweck:** Dokumentation der Utilities-Ordner-Struktur  
🔄 **Automatisch:** Alle 3 Tage via Cron-Job  
💡 **Verwendung:** Hauptsächlich als Referenz für manuelle Aliase  
⚠️ **Wichtig:** Apps selbst werden über Hauptinventar installiert

---

**Vollständige Dokumentation:** `~/bin/APP_RESTORE_README.md`
