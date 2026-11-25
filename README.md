# TablMarkUNSS Prof

Application **professeur** : centralise les feuilles envoyées par TablMarkUNSS Élève, permet de les vérifier, valider, imprimer, exporter (CSV) et calcule les classements par poule ainsi que le suivi des jeunes officiels.

Activités : handball, hand à 4, futsal, basketball, basket 3×3, football, badminton, tennis de table.

Application complémentaire : [TablMarkUNSS_Eleve](https://github.com/VinzToc/TablMarkUNSS_Eleve)

## Utilisation

- En ligne (GitHub Pages) : https://vinztoc.github.io/TablMarkUNSS_Prof/ — une fois Pages activé.
- Installable sur tablette / téléphone (« Ajouter à l'écran d'accueil ») et **utilisable hors ligne** après une première ouverture.
- Le fichier `index.html` fonctionne aussi seul (dépôt sur un portail ou ouverture locale), sans l'installation hors ligne.

## Préparer un match depuis OPUSS

Onglet « Préparer un match » : importer les fichiers « Tous les inscrits » exportés d'OPUSS (.xlsx, un par équipe ou un pour la compétition). L'appli lit les onglets accompagnateurs, jeunes officiels et élèves, puis pré-remplit la feuille : compétition, niveau, catégorie, équipes, professeurs, joueurs avec licence, jeunes officiels et jeunes coachs (licence, n° JO, niveau). La feuille préparée est transmise à TablMarkUNSS Élève par fichier ou par code. Le fichier Excel est lu dans le navigateur : rien n'est envoyé sur Internet.

## Échange élève → prof

L'élève clôture la feuille puis télécharge un fichier `.json` ou copie un code `TMU1:…`. Le professeur importe ces fichiers ou codes dans TablMarkUNSS Prof. Aucune donnée n'est envoyée à un serveur : tout reste dans le navigateur de chaque appareil (pensez aux sauvegardes côté prof).

## Transmission par QR code

À la clôture, l'élève peut afficher un **QR code pour le prof** : il contient un résumé compact de la feuille (rencontre, équipes, score par période ou sets, jeunes officiels et n° JO). Le prof le scanne dans TablMarkUNSS Prof (« Feuilles reçues → Scanner un QR code », ou photo du QR code). Le fichier .json reste le moyen de transmettre la feuille complète ; importé ensuite, il remplace le résumé.

Dans l'autre sens, la **feuille préparée par le prof** (équipes, joueurs, licences, jeunes officiels) passe aussi par QR code : l'appli prof affiche un ou plusieurs QR codes qui défilent automatiquement, et la tablette de la table de marque les scanne (« Importer une feuille du prof → Scanner le QR code du prof »), dans n'importe quel ordre, jusqu'à « Feuille reçue ».

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | l'application complète (HTML, CSS, JS dans un seul fichier) |
| `manifest.webmanifest` | nom, couleurs et icônes pour l'installation |
| `sw.js` | mise en cache pour le fonctionnement hors ligne |
| `icons/` | icônes 192 et 512 px |
| `lib/qrcode.js` | qrcode.js (Kazuhiko Arase, licence MIT) génère les QR codes des feuilles préparées |
| `lib/jsQR.js` | jsQR (licence Apache 2.0) lit le QR code quand le navigateur n'a pas de détecteur intégré |

Après une modification de `index.html`, changer le numéro de version `CACHE` dans `sw.js` pour que les appareils récupèrent la nouvelle version.
