# 🧸 DoudouLit

> **Une expérience éducative douce qui transforme le temps d'écran en moment d'apprentissage**  
> Histoires audio • Défis pédagogiques • Progression ludique

![React](https://img.shields.io/badge/React-18.x-61dafb?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178c6?logo=typescript)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?logo=fastapi)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-success)

---

## 🌟 Le Concept

**DoudouLit** réinvente le moment du coucher en **expérience interactive et bienveillante** pour les enfants de 3 à 10 ans.

Dans un monde où le temps d'écran inquiète les parents, DoudouLit propose une alternative **intelligente et apaisante** :
- 🎧 **Histoires audio** narrées avec douceur
- 🧠 **Défis pédagogiques** qui stimulent sans stresser
- 💖 **Ambiance bienveillante** qui rassure et inspire
- 📊 **Suivi de progression** ludique et non-compétitif

### 💡 Notre philosophie : les 5 piliers

| Pilier | Signification | Dans DoudouLit |
|--------|---------------|----------------|
| 🎮 **Ludique** | Apprendre en s'amusant | Gamification douce, mascottes attachantes, animations fluides |
| 🧠 **Intelligent** | Contenu adapté à l'âge | Histoires ciblées 3-10 ans, défis progressifs, recommandations personnalisées |
| 📚 **Pédagogique** | Enrichir sans contraindre | Vocabulaire enrichi, morales bienveillantes, mini-quiz de compréhension |
| 🌙 **Calme** | Apaiser avant le sommeil | Palette pastel, animations douces, narrations posées, pas de stimuli violents |
| 💖 **Bienveillant** | Encourager, jamais juger | Badges positifs, progression sans échec, messages rassurants |

---

## 📸 Aperçu de l'interface

### 🏠 Page d'accueil - Accueil chaleureux personnalisé

![Page d'accueil](./docs/images/accueil.png)

*Une mascotte animée accueille l'enfant par son prénom et l'invite à découvrir un univers doux et coloré.*

**Points forts :**
- Personnalisation immédiate (prénom de l'enfant)
- Design pastel non-stimulant
- Animations subtiles et rassurantes
- Navigation intuitive adaptée aux jeunes enfants

---

### 📖 Page Histoires - Bibliothèque illustrée

![Page Histoires](./docs/images/histoires.png)

*4 contes classiques revisités avec des illustrations modernes et chaleureuses.*

**Catalogue actuel :**
- 🦊 **Le Corbeau et le Renard** - Classique de La Fontaine (5-8 ans)
- 🔴 **Le Petit Chaperon Rouge** - Conte revisité avec bienveillance (3-6 ans)
- 🐺 **Pierre et le Loup** - Aventure musicale de Prokofiev (4-8 ans)
- 🐢 **Le Lièvre et la Tortue** - Fable sur la persévérance (4-7 ans)

**Fonctionnalités :**
- Recherche par titre
- Filtres par âge et durée
- Lecteur audio intégré
- Mode lecture accompagnée (texte + audio synchronisé)

---

### 🎯 Onboarding - Première connexion intuitive

![Onboarding](./docs/images/onboarding.png)

*Un parcours d'inscription simplifié qui met l'enfant en confiance dès les premières secondes.*

**Expérience utilisateur :**
- Formulaire minimal (prénom + âge)
- Pas de création de compte complexe
- Design accueillant avec mascotte guide
- Démarrage immédiat après validation

---

### 📊 Progression - Suivi ludique et motivant

![Page Progression](./docs/images/progression.png)

*Tableaux de bord visuels qui célèbrent chaque accomplissement sans créer de pression.*

**Statistiques affichées :**
- 🔥 **Jours consécutifs** : streak d'utilisation (objectif : 10 jours)
- ✅ **Histoires complétées** : nombre d'histoires écoutées en entier
- 🧩 **Défis relevés** : quiz et activités terminés
- 🎁 **Récompenses mystères** : système de badges à débloquer

**Approche bienveillante :**
- Pas de comparaison avec d'autres enfants
- Récompenses accessibles à tous
- Encouragements même en cas d'inactivité
- Gamification non-addictive

---

## 🎨 Identité visuelle & UX

### Palette de couleurs

```css
/* Couleurs principales */
--primary: #f6ad55;      /* Orange doux - Énergie positive */
--secondary: #fbb6ce;    /* Rose pastel - Douceur */
--accent: #68d391;       /* Vert menthe - Calme */
--bg-main: #f0f9ff;      /* Bleu très clair - Sérénité */
```

### Principes UX

1. **Accessibilité enfant** : Boutons larges (min 44x44px), textes contrastés
2. **Feedback visuel** : Animations à chaque interaction
3. **Pas de dark patterns** : Aucune manipulation, transparence totale
4. **Sécurité** : Pas de pub, pas de liens externes non sécurisés
5. **Contrôle parental** : Section dédiée (à venir)

---

## 🏗️ Architecture technique

### Stack technologique

| Composant | Technologie | Rôle |
|-----------|-------------|------|
| **UI Framework** | React 18 + TypeScript | Interface utilisateur |
| **Styling** | TailwindCSS | Design system responsive |
| **Animations** | Framer Motion | Micro-interactions fluides |
| **State** | Zustand | Gestion d'état légère |
| **Routing** | React Router v6 | Navigation SPA |
| **Backend** | FastAPI + Uvicorn | API REST performante |
| **Database** | SQLModel + SQLite/PostgreSQL | Persistance des données |
| **Audio** | HTML5 Audio API | Lecteur audio natif |

### Architecture Frontend

```
frontend-react/doudoulit-react/
├── src/
│   ├── pages/              # Pages principales
│   │   ├── Home.tsx        # Accueil personnalisé
│   │   ├── Stories.tsx     # Bibliothèque d'histoires
│   │   ├── Challenges.tsx  # Défis éducatifs
│   │   └── Progress.tsx    # Suivi de progression
│   ├── components/         # Composants réutilisables
│   │   ├── Navbar.tsx      # Navigation
│   │   ├── StoryCard.tsx   # Carte d'histoire
│   │   └── AudioPlayer.tsx # Lecteur audio custom
│   ├── store/              # State management (Zustand)
│   │   └── progress.ts     # Store de progression
│   └── assets/             # Images, sons, illustrations
└── tailwind.config.js      # Configuration design system
```

### Architecture Backend

```
backend/
├── app/
│   ├── main.py             # Point d'entrée API
│   ├── models/             # Modèles SQLModel
│   │   ├── story.py        # Modèle Histoire
│   │   ├── challenge.py    # Modèle Défi
│   │   └── user.py         # Modèle Utilisateur
│   ├── routers/            # Routes API
│   │   ├── stories.py      # CRUD histoires
│   │   ├── challenges.py   # CRUD défis
│   │   └── progress.py     # Suivi progression
│   └── core/
│       ├── config.py       # Configuration
│       └── database.py     # Connexion DB
└── requirements.txt
```

---

## 🚀 Installation & lancement

### Prérequis

- ✅ Node.js 18+ ([Télécharger](https://nodejs.org/))
- ✅ Python 3.11+ ([Télécharger](https://www.python.org/))
- ✅ Git ([Télécharger](https://git-scm.com/))

### Installation rapide

```bash
# 1. Cloner le dépôt
git clone https://github.com/flow3flow/doudoulit.git
cd doudoulit

# 2. Configurer le backend
conda create -n doudoulit python=3.11 -y
conda activate doudoulit
pip install -r backend/requirements.txt

# 3. Configurer le frontend
cd frontend-react/doudoulit-react
npm install
cd ../..
```

### Lancement de l'application

#### Terminal 1 : API Backend

```bash
conda activate doudoulit
python -m uvicorn backend.app.main:app --reload --port 8000
```

✅ API disponible : http://localhost:8000  
📚 Documentation Swagger : http://localhost:8000/docs

#### Terminal 2 : Frontend React

```bash
cd frontend-react/doudoulit-react
npm run dev
```

✅ Application : http://localhost:5173

---

## 🎯 Fonctionnalités

### ✅ Implémenté

- [x] 🏠 Page d'accueil avec mascotte animée
- [x] 📖 Bibliothèque de 4 histoires illustrées
- [x] 🎧 Lecteur audio avec contrôles (play/pause/volume)
- [x] 📊 Tableau de bord de progression
- [x] 🎨 Design system complet (couleurs, typographie, composants)
- [x] 📱 Interface responsive (mobile-first)
- [x] 🔄 Animations Framer Motion
- [x] 🗄️ API REST complète (FastAPI)
- [x] 💾 Base de données SQLModel

### 🚧 En développement

- [ ] 🔐 Authentification parentale (JWT)
- [ ] 👤 Profils enfants multiples
- [ ] 🎮 Défis interactifs (quiz, mini-jeux)
- [ ] 🏆 Système de badges et récompenses
- [ ] 🔊 Mode lecture accompagnée (texte + audio sync)
- [ ] 🌙 Mode nuit automatique (19h-7h)
- [ ] 📧 Notifications emails pour parents
- [ ] 📈 Analytics de progression

### 🎯 Roadmap 2025

**Q2 2025 : Enrichissement du contenu**
- 20 nouvelles histoires (contes du monde entier)
- 15 défis pédagogiques par tranche d'âge
- Voix narratives professionnelles (5 narrateurs)

**Q3 2025 : Monétisation & Premium**
- Modèle freemium (5 histoires gratuites)
- Abonnement famille : 4,99€/mois ou 49€/an
- Intégration Stripe pour paiements
- Pack famille multi-profils

**Q4 2025 : App mobile**
- Application React Native
- Mode offline (téléchargement d'histoires)
- Notifications push intelligentes
- Support Android + iOS

---

## 💡 Philosophie éducative

### Pourquoi DoudouLit est différent

Dans l'univers des apps pour enfants, beaucoup cherchent à **maximiser le temps d'écran**. DoudouLit fait l'inverse : notre objectif est de créer un **moment de qualité**, court mais intense, avant le coucher.

#### Notre approche pédagogique

1. **Contenu littéraire enrichi**  
   Les histoires utilisent un vocabulaire riche adapté à l'âge, avec des tournures de phrases variées pour développer le langage.

2. **Morales bienveillantes**  
   Chaque histoire porte des valeurs positives : entraide, persévérance, honnêteté, respect de la différence.

3. **Pas de violence gratuite**  
   Les contes classiques sont revisités pour retirer les passages traumatisants tout en gardant l'essence du récit.

4. **Apprentissage sans pression**  
   Les défis sont présentés comme des jeux, jamais comme des examens. Pas de notion d'échec.

5. **Respect du rythme de l'enfant**  
   Aucune notification intrusive, aucune mécanique addictive. L'enfant décide quand il écoute.

### Ce que disent les parents (bêta-testeurs)

> *"Ma fille de 5 ans réclame DoudouLit tous les soirs. C'est devenu notre rituel du coucher, et elle s'endort apaisée."*  
> — **Sophie, maman de Léa**

> *"Enfin une app qui ne cherche pas à garder mon fils scotché à l'écran. Les histoires sont courtes, belles, et il apprend du vocabulaire."*  
> — **Marc, papa de Jules**

> *"L'interface est tellement intuitive que mon fils de 4 ans navigue tout seul. Et moi je contrôle ce qu'il écoute."*  
> — **Amélie, maman de Tom**

---

## 🤝 Contribuer au projet

DoudouLit est open-source pour la partie technique, mais la stratégie produit reste privée.

### Comment contribuer ?

Nous acceptons les contributions sur :
- 🐛 **Corrections de bugs**
- ✨ **Améliorations UX/UI**
- 📝 **Documentation**
- 🧪 **Tests automatisés**
- 🌍 **Traductions** (anglais, espagnol prioritaires)

### Process de contribution

1. **Fork** le projet
2. Crée une branche (`git checkout -b feature/NouvelleFonctionnalite`)
3. Commit tes changements (`git commit -m 'Ajout d'une fonctionnalité'`)
4. Push vers la branche (`git push origin feature/NouvelleFonctionnalite`)
5. Ouvre une **Pull Request**

---

## 📜 Crédits & Licences

### Développement

- **Créé par** : [Flow Jaymes](https://github.com/flow3flow)
- **Design UX/UI** : Flow Jaymes
- **Inspirations** : Calm Kids, Lunii, Bayam

### Assets & ressources

| Ressource | Source | Licence |
|-----------|--------|---------|
| Illustrations histoires | Généré IA (Midjourney) + retouche Canva | Usage commercial OK |
| Mascotte DoudouLit | Créé sur mesure | Propriété du projet |
| Icônes | [Lucide React](https://lucide.dev/) | MIT License |
| Sons | [Freesound.org](https://freesound.org) | CC0 (domaine public) |
| Polices | [Google Fonts](https://fonts.google.com) | OFL License |

### Licence du projet

Ce projet est sous licence **MIT** — libre d'utilisation et de modification à des fins éducatives et non commerciales.

---

## 📞 Contact & Support

- 📧 **Email** : flow3flow@example.com
- 🐦 **Twitter** : [@flow3flow](https://twitter.com/flow3flow)
- 💼 **LinkedIn** : [Flow Jaymes](https://linkedin.com/in/flowjaymes)
- 🐛 **Issues** : [GitHub Issues](https://github.com/flow3flow/doudoulit/issues)
- 💬 **Discussions** : [GitHub Discussions](https://github.com/flow3flow/doudoulit/discussions)

---

## 🌍 Remerciements

Merci à tous les **bêta-testeurs** qui ont testé DoudouLit avec leurs enfants et partagé leurs retours précieux.

Un grand merci également à la communauté **React**, **FastAPI** et **TailwindCSS** pour leurs outils exceptionnels.

---

## 📊 Statistiques du projet

![GitHub stars](https://img.shields.io/github/stars/flow3flow/doudoulit?style=social)
![GitHub forks](https://img.shields.io/github/forks/flow3flow/doudoulit?style=social)
![GitHub issues](https://img.shields.io/github/issues/flow3flow/doudoulit)
![GitHub pull requests](https://img.shields.io/github/issues-pr/flow3flow/doudoulit)

---

### ✨ *"Transformer chaque histoire en moment magique"* ✨

---

**⭐ Si ce projet te plaît, n'hésite pas à lui donner une étoile sur GitHub !**
