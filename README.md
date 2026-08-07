# 🎌 Manga-Bridge Universal

> Compare ta collection [MangaCollec](https://www.mangacollec.com) avec les sites de vente en ligne pour éviter d'acheter des mangas que tu possèdes déjà. 100% local, zéro tracking.

![Manga-Bridge](https://img.shields.io/badge/Chrome-Extension-orange)
![Version](https://img.shields.io/badge/Version-1.0.2-green)
![License](https://img.shields.io/badge/License-MIT-blue)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local-brightgreen)

---

## ✨ Fonctionnalités

- **🔄 Synchronisation** de ta collection MangaCollec (mangas, tomes, éditeurs, genres)
- **👁️ Détection en temps réel** des mangas que tu possèdes déjà sur n'importe quel site marchand
- **🎓 Mode apprentissage** : configure l'extension pour de nouveaux sites en quelques clics
- **📚 Base annexes** : ajoute manuellement des titres non présents sur MangaCollec
- **💾 Sauvegarde/Restauration** : exporte et importe tes données en un clic
- **🔒 100% local** : aucune donnée n'est envoyée à un serveur tiers

---

## 📥 Installation

### Via Chrome Web Store (bientôt disponible)

### Installation manuelle

1. **Télécharge** le `.zip` depuis les [Releases](https://github.com/frinox/manga-bridge/releases)
2. **Décompresse** le fichier
3. Ouvre `chrome://extensions/` dans Chrome
4. Active le **Mode développeur** (interrupteur en haut à droite)
5. Clique sur **"Charger l'extension non empaquetée"**
6. Sélectionne le dossier décompressé

---

## 🚀 Utilisation

### 1. Synchroniser ta collection

1. Clique sur l'icône **Manga-Bridge** dans la barre d'outils Chrome
2. Entre ton **pseudo MangaCollec**
3. Clique sur **"🔄 Synchroniser la collection"**
4. Attends que la synchro se termine (l'extension ouvre temporairement des onglets MangaCollec)

### 2. Activer sur un site marchand

1. Ouvre un site de vente de mangas
2. Ouvre le popup Manga-Bridge
3. Active le site avec le toggle **"Activer Manga-Bridge ici"**
4. Clique sur **"🎓 Configurer ce site"** pour apprendre à l'extension à reconnaître les cases manga

### 3. Mode apprentissage

1. Clique sur le bouton **"🎓 +"** dans le panneau de contrôle
2. Clique sur une **case manga** sur la page (titre, image, tome...)
3. Sélectionne le **sélecteur de case** dans la liste (encadrement orange permanent)
4. Sélectionne le **sélecteur de titre** dans la liste des sous-éléments
5. Valide et l'extension se souvient de la configuration

---

## 🔒 Confidentialité

Toutes les données sont stockées **localement** sur ton appareil via `chrome.storage.local`. Aucune donnée n'est envoyée à un serveur tiers.

👉 [Politique de confidentialité complète](https://frinox.github.io/manga-bridge/privacy.html)

---

## 📁 Structure du projet

```
manga-bridge/
├── manifest.json              # Configuration de l'extension
├── background.js              # Service worker
├── content/                   # Scripts injectés dans les pages
│   ├── site-injector.js       # Orchestrateur : état global, init, observer
│   ├── learn-ui.js            # Positionnement, candidats, auto-détection de base
│   ├── learn-flow.js          # Flux d'apprentissage manuel (étapes, cleanup)
│   ├── auto-detect-flow.js    # Flux d'auto-détection complet
│   ├── card-processing.js     # Extraction, badges, traitement des cartes
│   ├── control-panel.js       # Panneau de contrôle, sync, import
│   ├── correction-menu.js     # Menu de correction (recherche, alias, ignore)
│   ├── matcher.js             # Moteur de matching (wrapper)
│   ├── mangacollec-bridge.js  # Bridge vers MangaCollec
│   ├── mangacollec-inject.js  # Injection sur MangaCollec
│   ├── mangacollec-series-genre-capture.js  # Capture des genres
│   └── site-injector.css      # Styles injectés
├── popup/                     # Popup de l'extension
│   ├── popup.html
│   ├── popup.css
│   └── popup.js
├── options/                   # Page de configuration
│   ├── options.html
│   ├── options.css
│   └── options.js
├── shared/                    # Utilitaires partagés
│   ├── matching-utils.js      # Algorithme de matching (TextProcessor, MBMatching)
│   ├── storage.js             # Couche de stockage
│   └── mascot.js              # Mascotte de l'extension
└── icons/                     # Icônes de l'extension
    ├── icon16.png
    ├── icon48.png
    └── icon128.png
```

---

## 🛠️ Technologies

- **Manifest V3** — Dernière version du manifest Chrome
- **JavaScript vanilla** — Pas de dépendances externes
- **chrome.storage.local** — Stockage local isolé
- **MutationObserver** — Détection des changements DOM en temps réel
- **Levenshtein** — Algorithme de similarité de texte pour le matching

---

## 📝 License

Ce projet est sous licence [MIT](LICENSE) — tu es libre de l'utiliser, le modifier et le redistribuer.

---

## 🐛 Signaler un bug

Si tu rencontres un problème, ouvre une [Issue](https://github.com/frinox/manga-bridge/issues) sur GitHub avec :
- Le site concerné
- Une description du problème
- Des captures d'écran si possible

---

## 💡 Contribuer

Les contributions sont les bienvenues ! N'hésite pas à :
- Proposer des améliorations
- Signaler des bugs
- Ajouter des fonctionnalités

---

> Fait avec ❤️ pour les collectionneurs de mangas
