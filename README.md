# DermaSuivi : suivi photo de la cicatrisation

Application installable sur téléphone (Android, iPhone) et ordinateur, qui remplace le dossier
« un album par patient » de la galerie photo :

- **un espace par médecin** : au lancement, chacun choisit son espace (« Dr Martin »…) et ne voit que
  ses patients ; un code personnel peut le protéger (verrouillage automatique après 5 min hors de l'app) ;
- **un dossier par patient** (nom, n° de dossier, notes), recherche, tri récent / A→Z ;
- **prendre une photo** directement ou **importer** depuis la galerie (plusieurs à la fois) ;
  la date de prise de vue est lue automatiquement dans la photo et reste modifiable ;
- **zones / lésions** (ex. « jambe droite ») pour suivre plusieurs lésions chez un même patient ;
- **frise chronologique** avec le jour de suivi : J0, J+14, J+49… ;
- **comparaison côte à côte** de 2 à 4 photos, bouton « première / dernière photo »,
  et **curseur avant / après** qui superpose deux photos ;
- **image de comparaison** (photos + dates) à partager ou enregistrer, par exemple pour le patient ;
- **fonctionne hors ligne** ; **sauvegarde / restauration** dans un fichier pour changer d'appareil.

## Confidentialité

Les photos restent **uniquement sur l'appareil** (IndexedDB du navigateur) : rien n'est envoyé sur
internet. Les fichiers de sauvegarde contiennent des données de santé : à conserver en lieu sûr.
Sur iPhone, installer l'app sur l'écran d'accueil évite que Safari efface les données d'un site
inutilisé.

Le code d'un espace empêche un autre médecin utilisant le même appareil de l'ouvrir ; ce n'est pas un
chiffrement des photos. Chaque médecin peut aussi simplement installer l'app sur son propre téléphone.

Police : EB Garamond (licence libre SIL OFL), incluse dans `fonts/` pour fonctionner hors ligne.

## Installer

Adresse : `https://actionplantracker23-ship-it.github.io/Derma/`

Chaque push sur `main` republie l'application (`.github/workflows/pages.yml`).
Première fois : **Settings → Pages → Source : GitHub Actions**.

- **iPhone / iPad** : ouvrir l'adresse dans Safari → Partager → « Sur l'écran d'accueil ».
- **Android** : Chrome → menu ⋮ → « Installer l'application ».
- **Ordinateur** : Chrome ou Edge → icône d'installation dans la barre d'adresse.

## Développement

Aucune dépendance ni compilation : HTML, CSS et JavaScript.

```sh
python3 -m http.server 8000   # puis http://localhost:8000
```

`index.html` (page), `app.js` (logique, base IndexedDB), `style.css`, `sw.js` (hors ligne),
`manifest.webmanifest` et `icons/` (installation).
