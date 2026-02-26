# Versions Android a installer

Pour compiler l'application, installer les composants Android suivants :

- Android SDK Build-Tools : `33.0.0`
- Android NDK : `23.1.7779620`

Ces versions correspondent au besoin de compilation demande pour ce projet.

## Installation via Android Studio

1. Ouvrir `SDK Manager`
2. Onglet `SDK Tools`
3. Cocher :
   - `Android SDK Build-Tools 33.0.0`
   - `NDK (Side by side)` puis selectionner `23.1.7779620`
4. Appliquer les changements

## Installation via ligne de commande

Sous Windows, utiliser `sdkmanager.bat` (pas `sdkmanager`).

### Windows (cmd)

```bat
sdkmanager.bat "build-tools;33.0.0" "ndk;23.1.7779620"
```

### Windows (PowerShell)

```powershell
sdkmanager.bat "build-tools;33.0.0" "ndk;23.1.7779620"
```

### macOS / Linux

```bash
sdkmanager "build-tools;33.0.0" "ndk;23.1.7779620"
```

Option recommandee (plateforme Android 33) :

Windows :

```bat
sdkmanager.bat "platforms;android-33"
```

macOS / Linux :

```bash
sdkmanager "platforms;android-33"
```

## Verification rapide

### Windows (cmd)

```bat
sdkmanager.bat --list | findstr /R /C:"build-tools;33.0.0" /C:"ndk;23.1.7779620"
```

### Windows (PowerShell)

```powershell
sdkmanager.bat --list | Select-String "build-tools;33.0.0|ndk;23.1.7779620"
```

### macOS / Linux

```bash
sdkmanager --list | grep -E "build-tools;33.0.0|ndk;23.1.7779620"
```
