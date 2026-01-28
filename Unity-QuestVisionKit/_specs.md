# 📑 DOCUMENT DE RÉFÉRENCE : QuestVisionKit
> **Dernière mise à jour :** 2026-01-26 | **Statut :** En cours

## 1. 🎯 État de la Vision
*Ce qui a été décidé sur le 'Pourquoi' et le 'Pour qui'.*
Développement d'un kit de vision pour Quest (et potentiellement Pico) intégrant la détection de QR Codes et l'affichage caméra (Passthrough).

## 2. 🏗️ Architecture Validée
* **Stack :** Unity (C#), XR Interaction Toolkit / Meta XR
* **Structure de données :** -
* **Arborescence :** Standard Unity Project
  * Assets/Samples/3 QRCodeTracking : Feature de tracking QR

## 3. ✅ Fonctionnalités Implémentées
* Détection QR Code (Permissions corrigées : Caméra + Spatial Data)

## 4. 🚧 En Cours de Développement / Prochaine Étape
* Résolution du problème d'ajout du symbole de compilation `ZXING_ENABLED` pour la détection de la DLL `zxing.unity.dll`.

## 5. 📝 Journal des Décisions (Le "ChangeLog")
* **2026-01-26 :** Fix de `ZXingDefineSymbolChecker.cs` pour supporter `zxing.unity.dll`.
* **2026-01-26 :** Ajout des permissions Android (Camera + Use Scene) dans le Manifest et requête au runtime dans `QrCodeDisplayManager.cs`.

## 📌 Glossaire & Contraintes
* ZXing : Librairie de scan de QR codes.
