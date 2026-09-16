# ACTI3D V1.9

Version de référence du contrôleur de chambre ACTI3D.

- Matériel : Waveshare ESP32-S3-Touch-LCD-7B, écran 1024 × 600.
- Capteurs : SHT31 et DS18B20 sur GPIO6.
- Régulation de chauffage et d'extraction par consigne.
- Historique de température et d'humidité en RAM sur 24 heures.
- Bouton STOP bistable avec confirmation avant rétablissement.
- Interface avec pictogrammes et logo commun à l'accueil et à REGLAGES.

**Installation : USB. Cette version n'est pas compatible avec une mise à jour OTA.**

La configuration de référence utilise `ACTI3D_OUTPUTS_ARMED=0` : les sorties
de puissance GPA0 à GPA3 sont désarmées.

Avant publication, joindre les binaires d'un même build testé, sa procédure
de flash USB et les sommes SHA-256 correspondantes.
