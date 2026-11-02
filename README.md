# Régie — outils d'ingénieur du son (Android)

Heures (timbrage), célérité, télémètre, line array, générateur (rose, blanc, sinus, sweep),
analyseur (RTA + spectrogramme) et mesure de délai entre deux sources par sweep.
Fonctionne hors ligne. Les heures sont stockées sur le téléphone ; export CSV par le menu Partager.

## Obtenir l'APK

**Android Studio** : File › Open › ce dossier, puis Build › Build APK(s).
Ou en ligne de commande (SDK Android + Gradle 8.9) : `gradle assembleRelease`
→ `app/build/outputs/apk/release/app-release.apk`

**Sans rien installer** : poussez ce dossier sur un dépôt GitHub. Le workflow
`.github/workflows/build.yml` compile l'APK ; téléchargez-le dans l'onglet Actions › regie-apk.

Sur le téléphone : autoriser l'installation depuis la source (Fichiers / navigateur), puis ouvrir l'APK.

## Modifier l'interface
Toute l'app est dans `app/src/main/assets/index.html` (HTML/JS, sans dépendance).

## Mesure de délai — mode d'emploi
1. Sortie casque/USB du téléphone → une entrée de la console.
2. Téléphone posé à la position d'écoute à aligner.
3. Envoyer le retour uniquement vers la source A (ex. façade) → MESURER A.
4. Uniquement vers B (ex. tour de délai, front-fill) → MESURER B.
5. Lire le délai conseillé (inclut l'offset de précédence choisi).
La latence téléphone + console est identique dans les deux mesures et s'annule.
Visez un rapport signal/bruit > 20 dB.
