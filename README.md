# Fenêtre — suivi de jeûne intermittent

Application web personnelle pour organiser un jeûne intermittent (16/8, 15/9, 14/10) :
minuteur en temps réel, check-in quotidien, tableau de suivi hebdomadaire, mesures
(poids / tour de taille) et guide de référence.

Aucune installation, aucun serveur : tout tourne dans le navigateur et les données
sont stockées localement sur l'appareil (`localStorage`), rien n'est envoyé
ailleurs.

## Mettre en ligne avec GitHub Pages (gratuit)

1. Crée un nouveau dépôt sur GitHub (public).
2. Ajoute **tous les fichiers** de ce dossier à la racine du dépôt : `index.html`,
   `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png` (glisser-déposer sur
   github.com fonctionne, ou `git add` / `git commit` / `git push`).
3. Dans le dépôt : **Settings → Pages** → sous "Build and deployment", choisis
   la branche `main` et le dossier `/ (root)` → **Save**.
4. Après une minute ou deux, l'appli est accessible à :
   `https://<ton-nom-utilisateur>.github.io/<nom-du-depot>/`

`manifest.json` et `sw.js` sont ce qui rend l'appli réellement **installable**
(et non juste un raccourci) — sans eux, le bouton "Installer" de Chrome ne
fonctionne pas de façon fiable sur Android.

## Installer sur le téléphone comme une appli

Une fois l'URL GitHub Pages ouverte dans le navigateur du téléphone :

- **Android (Chrome)** : une bannière ou une icône ⊕ dans la barre d'adresse
  propose *"Installer l'application"* — sinon menu ⋮ → *Installer l'application*.
  Recharge la page une fois si l'option ne s'affiche pas tout de suite (le
  service worker doit s'enregistrer avant que Chrome propose l'installation).
- **iPhone (Safari)** : bouton Partager → *Sur l'écran d'accueil*

## Notes

- Les données sont propres à chaque navigateur/appareil (pas de synchronisation
  entre téléphone et ordinateur pour l'instant).
- Un bouton "Réinitialiser mes données" est disponible dans l'onglet Guide.
