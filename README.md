# Firmwares ACTI3D

Distribution des firmwares du contrôleur ACTI3D, sur ESP32-S3 avec écran
Waveshare ESP32-S3-Touch-LCD-7B 1024 × 600.

Compte GitHub prévu : **seb449-art**. Dépôt prévu : **acti3d-firmware**.

Ce dépôt contient les informations de distribution. Les binaires sont joints
aux **Releases**, et le code source du contrôleur reste dans un dépôt séparé.

## Version de référence

**V1.9** : régulation de la chambre, extraction automatique, historique SHT31
en mémoire et bouton STOP bistable avec confirmation de rétablissement.

La V1.9 ne dispose pas de connexion Wi-Fi ni de mise à jour OTA. Elle nécessite
un flash USB. La préparation de ce dépôt n'ajoute pas ces fonctions à l'écran.

## Télécharger une version

Ouvrir **Releases** et sélectionner une version compatible avec le matériel.
Lire ses notes de version avant installation. Les archives « Source code »
créées automatiquement par GitHub ne sont pas le firmware de l'écran.

Pour une mise à jour USB complète, suivre la procédure fournie avec la release.
Le fichier d'application `ACTI3D_Controller.bin` seul ne suffit pas à préparer
une carte vierge : le bootloader et la table de partitions sont aussi nécessaires.

Les versions OTA seront signalées explicitement lorsque cette fonction sera
intégrée au contrôleur. Un écran devra être préparé par USB avec le firmware
et les partitions OTA avant de pouvoir utiliser ce mode de mise à jour.

## Publication

Voir [PUBLICATION.md](PUBLICATION.md) pour préparer une release et
[CHANGELOG.md](CHANGELOG.md) pour les changements de version.

Documentation officielle : [Releases GitHub](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)
et [OTA ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/v5.5/esp32s3/api-reference/system/ota.html).
