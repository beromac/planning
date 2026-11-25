# Planning – disponibilités, congés et réservations

Application installable sur téléphone (PWA), qui fonctionne aussi hors connexion.

## Utilisation

- **W** : touchez ou glissez le doigt sur les jours où vous êtes disponible. Retouchez un jour W pour l'enlever.
- **CP** : même chose pour vos congés.
- **Pastilles magasins** : choisissez un magasin dans la barre du bas, puis touchez un jour **W** pour poser la pastille (initiales + couleur). Retouchez pour la retirer. Plusieurs magasins possibles sur le même jour.
- **⌫ Gomme** : efface un jour (type + pastilles).
- **↶** annule la dernière action.
- **Magasins (🏪 / +)** : jusqu'à 10 magasins, nom, initiales (3 lettres max) et couleur différente pour chacun.
- **Jours travaillés par magasin** : sous le calendrier du mois, chaque magasin affiche son nombre de jours (jours W portant sa pastille) et le total de jours travaillés. La vue **Année** ajoute un tableau magasin × mois avec le total de l'année. Les mêmes totaux figurent sur les impressions.
- **Jours fériés et vacances scolaires (zone A)** : les jours fériés (France métropolitaine, calculés pour n'importe quelle année) apparaissent en **violet** avec leur nom, les vacances scolaires de la zone A en **bleu clair**. Vos jours **CP** gardent leur couleur orange et **W** sa couleur verte : un liseré violet ou bleu reste visible sur le bord de la case. Ces couleurs figurent aussi sur la vue Année et sur les impressions. Chaque affichage se coupe dans ⚙ Paramètres. Les dates de vacances viennent du calendrier officiel et sont enregistrées de **septembre 2025 à août 2028** ; au-delà, seuls les jours fériés s'affichent jusqu'à une mise à jour de l'application.
- **Mois / Année** : bascule entre la vue mensuelle et la vue de l'année entière (touchez un mois pour l'ouvrir).
- **Navigation** : flèches ‹ › pour changer de mois (ou d'année), touchez le titre pour aller directement à n'importe quel mois/année. Le planning n'a pas de limite d'années.
- **🖨 Imprimer** : un mois ou une année complète sur **une seule page A4** (paysage ou portrait), avec légende des magasins.
- **⚙ Paramètres** : affichage des fériés / vacances, synchronisation (dont **Modifier le jeton**) et sauvegarde. La synchronisation relie plusieurs appareils (téléphone, ordinateur…) : ce que vous saisissez sur l'un apparaît sur l'autre automatiquement (voir plus bas). On y trouve aussi la sauvegarde / restauration par fichier (.json).

> Les données sont enregistrées dans le navigateur de l'appareil. Sans synchronisation, elles restent uniquement sur cet appareil : pensez à faire une sauvegarde de temps en temps (effacer les données du navigateur efface le planning).

## Relier téléphone et ordinateur (synchronisation)

Le planning est copié dans un **gist privé** (un petit fichier) de votre compte GitHub, et chaque appareil le met à jour automatiquement.

1. Ouvrez l'application, touchez **⚙**, puis le lien « page de création du jeton GitHub » (ou allez sur `github.com/settings/tokens/new`).
2. Note : `Planning`. **Expiration : No expiration**. Cochez **uniquement « gist »**. Touchez **Generate token** tout en bas, puis **copiez** le jeton (`ghp_…`) : il n'est affiché qu'une fois.
3. Collez le jeton dans l'application, touchez **Activer la synchronisation**.
4. Sur l'autre appareil : ouvrez l'application, ⚙, collez **le même jeton** et activez. Le planning s'y affiche aussitôt.

Les modifications partent quelques secondes après la saisie et sont récupérées à chaque ouverture de l'application. Hors connexion, tout reste enregistré et part dès que le réseau revient. Si deux appareils modifient le même jour, la modification la plus récente l'emporte.

**Changer de jeton** : ⚙ Paramètres → Synchronisation → **Modifier le jeton**, collez le nouveau jeton et enregistrez. Avec le même compte GitHub, le planning en ligne est conservé ; le jeton précédent est simplement remplacé (pensez à le supprimer sur `github.com/settings/tokens`).

Le jeton ne donne accès qu'aux gists de votre compte (pas à vos dépôts) et reste uniquement dans l'appareil. Pour couper l'accès : `github.com/settings/tokens` → Delete. Pour supprimer les données en ligne : `gist.github.com` → ouvrir le gist « Planning » → Delete.

## Installer sur le téléphone via GitHub (GitHub Pages)

1. Sur [github.com](https://github.com), créez un compte puis un **nouveau dépôt** (par ex. `planning`), en **Public**.
2. Dans le dépôt : **Add file → Upload files**, envoyez ces 5 fichiers **à la racine** du dépôt :
   `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`
   puis **Commit changes**.
3. **Settings → Pages** : *Source* = **Deploy from a branch**, *Branch* = **main** / **(root)**, puis **Save**.
4. Après 1 à 2 minutes, l'application est disponible à l'adresse :
   `https://VOTRE-NOM.github.io/planning/`
5. Ouvrez cette adresse sur le téléphone :
   - **Android (Chrome)** : menu ⋮ → **Installer l'application** (ou « Ajouter à l'écran d'accueil »).
   - **iPhone (Safari)** : bouton Partager → **Sur l'écran d'accueil**.

Pour mettre à jour l'application plus tard, remplacez simplement `index.html` dans le dépôt : le téléphone récupère la nouvelle version dès qu'il a du réseau.

## Impression depuis le téléphone

Touchez 🖨, choisissez Mois ou Année, puis **Imprimer**. Dans la fenêtre du téléphone, choisissez votre imprimante, ou **Enregistrer en PDF** pour obtenir un fichier A4 prêt à partager.
Sur iPhone, si l'impression ne s'ouvre pas depuis l'application installée sur l'écran d'accueil, ouvrez la même adresse dans Safari et imprimez depuis là.
