# Searchfinder

Application mobile Android pour consulter les règles de **Pathfinder 2e** en français, 100% hors-ligne.

![React Native](https://img.shields.io/badge/React%20Native-0.76.9-61DAFB?logo=react)
![SQLite](https://img.shields.io/badge/SQLite-FTS5-003B57?logo=sqlite)
![License](https://img.shields.io/badge/License-MIT-green)

## ✨ Fonctionnalités

- 🔍 **Recherche full-text** instantanée sur tout le contenu PF2e
- 📱 **100% hors-ligne** — Toutes les données stockées localement en SQLite
- 🇫🇷 **En français** — Traductions officielles de la communauté Pathfinder-FR
- ⭐ **Favoris** — Accès rapide à vos règles préférées
- 🏷️ **Filtres avancés** — Par type, niveau, rareté, traits
- 🎨 **Interface parchemin/pastel** — Design élégant inspiré de l'univers Pathfinder

## 📚 Contenus inclus

| Catégorie | Description |
|-----------|-------------|
| 💀 Créatures | Bestiaire complet avec stats, capacités, attaques |
| ✨ Sorts | Tous les sorts avec composants, portée, effets |
| ⭐ Dons | Dons généraux, de classe, d'ascendance |
| ⚔️ Équipement | Armes, armures, objets magiques |
| 🎭 Classes | Capacités, progression, maîtrises |
| 🏃 Actions | Actions de base et spéciales |
| 🧬 Ascendances | Héritages et dons d'ascendance |
| 📜 Archétypes | Dons de dévouement et multiclassage |
| ⚠️ États | Conditions et afflictions |
| Et plus... | Dangers, backgrounds, règles diverses |

## 🚀 Installation

### Prérequis

- Node.js 18+
- JDK 21
- Android Studio avec SDK 34
- React Native CLI

### Installation

```bash
# Cloner le repo
git clone https://github.com/E-Paroxysme/Searchfinder.git
cd Searchfinder

# Installer les dépendances
npm install

# Lancer sur Android
npx react-native run-android
```

### Base de données

La base de données SQLite (~250 Mo) est téléchargée automatiquement au premier lancement de l'application depuis les [GitHub Releases](https://github.com/E-Paroxysme/Searchfinder/releases).

## 📁 Structure du projet

```
Searchfinder/
├── App.js                    # Point d'entrée avec vérification BDD
├── src/
│   ├── screens/
│   │   ├── HomeScreen.jsx    # Accueil avec catégories rapides
│   │   ├── SearchScreen.jsx  # Recherche avec filtres
│   │   ├── DetailScreen.jsx  # Routeur vers les détails
│   │   ├── FavoritesScreen.jsx
│   │   ├── AboutScreen.jsx   # Crédits et mise à jour
│   │   └── DownloadScreen.jsx
│   ├── components/
│   │   ├── details/          # Composants de détail par type
│   │   │   ├── CreatureDetail.jsx
│   │   │   ├── SpellDetail.jsx
│   │   │   ├── ClassDetail.jsx
│   │   │   ├── FeatDetail.jsx
│   │   │   ├── EquipmentDetail.jsx
│   │   │   ├── ActionDetail.jsx
│   │   │   └── GenericDetail.jsx
│   │   └── common/           # Composants réutilisables
│   ├── database/
│   │   └── index.js          # API SQLite
│   ├── hooks/
│   │   └── useFavorites.js   # Gestion des favoris
│   ├── navigation/           # Navigation par onglets
│   └── utils/
│       ├── theme.js          # Thème parchemin/pastel
│       └── config.js         # Configuration
└── package.json
```

## 🎨 Thème

L'application utilise un thème parchemin/pastel avec des couleurs distinctes par type de contenu :

| Type | Couleur |
|------|---------|
| Créatures | Rouge `#D45B5B` |
| Sorts | Violet `#7B68C8` |
| Dons | Vert `#4A9B8C` |
| Équipement | Or `#C9943A` |
| Classes | Violet foncé `#8B5B8B` |
| Actions | Bleu `#5B8DC7` |

Raretés : Commun (noir), Peu commun (or), Rare (bleu), Unique (violet)

## 🔧 Configuration

### Personnaliser le thème

Modifiez `src/utils/theme.js` pour ajuster les couleurs et la typographie.

### URL de la base de données

L'URL de téléchargement est configurée dans `src/utils/config.js`.

## 📊 Sources de données

Les données proviennent des projets open-source de la communauté :

- [pathfinder-fr/pf2-data-fr](https://github.com/pathfinder-fr/pf2-data-fr) — Traductions françaises officielles
- [foundryvtt/pf2e](https://github.com/foundryvtt/pf2e) — Données de référence anglaises

## ⚠️ Notes techniques

- **SQLite avec FTS5** pour la recherche full-text performante
- **react-native-quick-sqlite** pour la compatibilité React Native 0.76+
- **Pas de Reanimated** — Animations avec l'API Animated native de React Native
- Compatible **JDK 21**

## 📄 Licence

MIT

---

**Pathfinder** est une marque déposée de Paizo Inc. Cette application utilise les données du System Reference Document (SRD) sous licence Open Game License (OGL).

Les traductions françaises sont fournies par la communauté [Pathfinder-FR](https://www.pathfinder-fr.org/).
