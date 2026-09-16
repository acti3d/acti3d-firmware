# Publier un firmware ACTI3D

## Préparer le dépôt

Créer un dépôt **public** nommé `acti3d-firmware` sous le compte **seb449-art**.
Son adresse sera `https://github.com/seb449-art/acti3d-firmware`.
Y déposer uniquement les fichiers de ce dossier de distribution.
Ne pas publier le dossier complet du projet ESP-IDF.

## Préparer une version

1. Définir la version dans `main/acti3d_config.h`.
2. Exécuter `idf.py build` dans le projet du contrôleur.
3. Flasher et valider ce build sur le matériel, y compris le retour depuis
   HISTORIQUE et le cycle STOP / confirmation / rétablissement.
4. Conserver les binaires de ce même build avec leurs notes de version.
   Ne pas mélanger des fichiers issus de compilations différentes.

La V1.9 utilise une partition factory de 1 Mo et ne prend pas en charge l'OTA.
Pour préparer une carte par USB, inclure le bootloader, la table de partitions,
le binaire d'application et une procédure reprenant les paramètres et offsets
du build. Le fichier `build/flash_args` fournit les paramètres du flash.

## Créer la release

1. Dans GitHub, ouvrir **Releases → Draft a new release**.
2. Créer le tag `v1.9` pour la première version de référence.
3. Utiliser le titre `ACTI3D V1.9` et les notes de `RELEASE-v1.9.md`.
4. Joindre le paquet USB complet testé. Le binaire d'application peut aussi
   être joint séparément sous le nom stable `ACTI3D_Controller.bin`.
5. Joindre les sommes SHA-256 des fichiers distribués, obtenues avec
   `Get-FileHash -Algorithm SHA256` sous PowerShell.
6. Vérifier les fichiers dans le brouillon, puis publier la release.

Ne pas remplacer discrètement les fichiers d'une version déjà distribuée.
Publier une nouvelle version lorsqu'un firmware change.

## Préparer les futures versions OTA

Chaque release OTA devra contenir le fichier `ACTI3D_Controller.bin` et des
informations permettant au contrôleur de vérifier la version, la compatibilité
matérielle, la taille et l'intégrité du téléchargement. Le format sera fixé
lors de l'intégration de l'OTA au firmware.

GitHub permet de consulter la dernière release publiée via :

```text
https://api.github.com/repos/seb449-art/acti3d-firmware/releases/latest
```

Cet endpoint sera disponible après publication d'une première release stable.
Le firmware devra utiliser les liens de téléchargement des assets renvoyés
par l'API, suivre les redirections HTTPS et contrôler les erreurs réseau.

Les versions expérimentales seront publiées comme **prereleases**, pour les
distinguer des versions stables destinées aux clients.

Sources : [gestion des releases](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)
et [API des releases](https://docs.github.com/en/rest/releases/releases).
