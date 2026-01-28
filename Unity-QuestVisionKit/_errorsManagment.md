# Journal des Erreurs

## 2026-01-26 - Problème de scripting define ZXING_ENABLED
**Description :** Le symbole `ZXING_ENABLED` n'est pas ajouté automatiquement aux Define Symbols alors que la DLL est présente.
**Cause Identifiée :** Le script `ZXingDefineSymbolChecker.cs` cherche des fichiers finissant par `*ZXing.dll` ou `*zxing.dll`. Le fichier présent est `zxing.unity.dll`, qui ne matche pas ces patterns (il finit par `.unity.dll`).
**Solution :** Ajouter `zxing.unity.dll` aux patterns de recherche dans `ZXingDefineSymbolChecker.cs`.

## 2026-01-26 - QR Code non détecté (Quest 3)
**Description :** Le QRCode n'est pas détecté dans la scène `QRCodeTracking`.
**Cause Identifiée :** Manque de permissions Android. `android.permission.CAMERA` était absent du Manifest, et aucune demande de permission runtime n'était faite pour la Caméra et les Données Spatiales.
**Solution :** 
1. Ajout de `android.permission.CAMERA` dans `AndroidManifest.xml`.
2. Ajout de `RequestUserPermission` (Camera & Scene) dans le `Start()` de `QrCodeDisplayManager.cs`.
