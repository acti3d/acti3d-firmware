# Versions ACTI3D

## V1.9 — référence validée

- Régulation de température de chambre avec SHT31 et surveillance DS18B20 sur GPIO6.
- Extraction automatique avec consigne réglable par − / + et dans REGLAGES.
- Historique SHT31 de température et d'humidité sur 24 heures en RAM,
  avec une mesure par minute ; effacé au redémarrage.
- STOP bistable : coupure et inhibition des sorties, rétablissement confirmé.
- Indication de STOP actif sur l'écran et état STOP dans le monitoring.
- Pictogrammes des cadres, de REGLAGES et d'HISTORIQUE.
- Réserve mémoire LVGL supplémentaire en PSRAM pour les pages et leur dessin.
- Logo du menu REGLAGES identique à celui de l'accueil.

La configuration actuelle conserve `ACTI3D_OUTPUTS_ARMED=0` : les sorties
de puissance GPA0 à GPA3 restent désarmées. Le buzzer PB0 est indépendant de
ce verrou et est également inhibé par STOP. La release doit décrire fidèlement
la configuration réellement compilée et testée.

Wi-Fi, Moonraker et OTA ne sont pas intégrés à cette version.
