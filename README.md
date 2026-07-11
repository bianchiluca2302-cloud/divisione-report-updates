# Divisione Report — aggiornamenti

Canale di distribuzione degli aggiornamenti dell'app **Divisione Report**.
Qui NON c'è il codice sorgente: solo il file `version.json` (letto dall'app
all'avvio per sapere se esiste una versione nuova) e, nelle
[Release](../../releases), l'installer da scaricare.

## Come pubblicare una nuova versione (promemoria per Luca)

1. Alza la versione in `app.py` (`APP_VERSION`) e `installer.iss`
   (`MyAppVersion`), poi `build_installer.bat`.
2. Crea la release con l'installer (nome asset SEMPRE
   `DivisioneReport-Setup.exe`, così il link in version.json non cambia mai):

       copy installer_output\DivisioneReport-Setup-X.Y.Z.exe DivisioneReport-Setup.exe
       gh release create vX.Y.Z DivisioneReport-Setup.exe --title "vX.Y.Z" --notes "cosa c'è di nuovo"

3. Aggiorna `version` e `note` in `version.json` e fai push.

Al prossimo avvio i clienti (dalla 2.1.0 in su) vedranno il banner
"È disponibile la versione X.Y.Z" col tasto Scarica.
