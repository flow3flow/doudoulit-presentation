# 🤝 Guide de Contribution - DoudouLit

Merci de ton intérêt pour contribuer à **DoudouLit** ! 🎉

---

## 📋 Table des matières

1. [Code de conduite](#code-de-conduite)
2. [Comment contribuer](#comment-contribuer)
3. [Processus de développement](#processus-de-développement)
4. [Standards de code](#standards-de-code)
5. [Soumettre une Pull Request](#soumettre-une-pull-request)
6. [Reporter un bug](#reporter-un-bug)
7. [Proposer une fonctionnalité](#proposer-une-fonctionnalité)

---

## 📜 Code de conduite

DoudouLit s'engage à fournir un environnement accueillant et inclusif. En participant, tu acceptes de :

- ✅ Être respectueux et courtois envers tous les contributeurs
- ✅ Accepter les critiques constructives
- ✅ Se concentrer sur ce qui est meilleur pour la communauté
- ✅ Faire preuve d'empathie envers les autres membres

---

## 🚀 Comment contribuer

Nous acceptons plusieurs types de contributions :

### 1. 🐛 Corrections de bugs

Si tu trouves un bug :
1. Vérifie qu'il n'a pas déjà été reporté dans les [Issues](https://github.com/flow3flow/doudoulit/issues)
2. Si non, crée une nouvelle issue avec le label `bug`
3. Décris le problème de manière détaillée
4. Propose une solution si possible

### 2. ✨ Nouvelles fonctionnalités

Pour proposer une nouvelle fonctionnalité :
1. Ouvre une [Discussion](https://github.com/flow3flow/doudoulit/discussions)
2. Décris ta proposition et son utilité
3. Attends les retours de la communauté
4. Si approuvée, crée une issue avec le label `enhancement`

### 3. 📝 Documentation

La documentation est essentielle ! Tu peux contribuer en :
- Améliorant le README
- Ajoutant des exemples de code
- Corrigeant des fautes d'orthographe
- Traduisant la documentation

### 4. 🎨 Design & UX

Si tu as des compétences en design :
- Propose des améliorations d'interface
- Crée des maquettes Figma
- Optimise l'expérience utilisateur

### 5. 🧪 Tests

Aide à améliorer la couverture de tests :
- Ajoute des tests unitaires
- Crée des tests d'intégration
- Teste l'application sur différents navigateurs/devices

---

## 🛠️ Processus de développement

### 1. Fork & Clone

```bash
# Fork le projet sur GitHub, puis clone ton fork
git clone https://github.com/TON_USERNAME/doudoulit.git
cd doudoulit
```

### 2. Créer une branche

```bash
# Crée une branche depuis main
git checkout -b feature/ma-fonctionnalite
# ou
git checkout -b fix/correction-bug
```

**Convention de nommage des branches :**
- `feature/` : nouvelle fonctionnalité
- `fix/` : correction de bug
- `docs/` : documentation
- `refactor/` : refactoring de code
- `test/` : ajout de tests

### 3. Installer les dépendances

```bash
# Backend
conda create -n doudoulit python=3.11 -y
conda activate doudoulit
pip install -r backend/requirements.txt

# Frontend
cd frontend-react/doudoulit-react
npm install
```

### 4. Développer & tester

```bash
# Lancer l'API
python -m uvicorn backend.app.main:app --reload

# Lancer le frontend (dans un autre terminal)
cd frontend-react/doudoulit-react
npm run dev
```

### 5. Commit

```bash
git add .
git commit -m "feat: ajout de la fonctionnalité X"
```

**Convention de commit (Conventional Commits) :**
- `feat:` nouvelle fonctionnalité
- `fix:` correction de bug
- `docs:` documentation
- `style:` formatage, style
- `refactor:` refactoring
- `test:` ajout de tests
- `chore:` tâches diverses

**Exemples :**
```bash
git commit -m "feat: ajout du mode nuit"
git commit -m "fix: correction du lecteur audio sur Safari"
git commit -m "docs: mise à jour du README avec nouvelles captures"
```

---

## 📏 Standards de code

### Frontend (React/TypeScript)

```typescript
// ✅ Bon
interface StoryProps {
  title: string;
  duration: number;
  ageMin: number;
}

const StoryCard: React.FC<StoryProps> = ({ title, duration, ageMin }) => {
  return (
    <div className="rounded-2xl shadow-lg p-6">
      <h3 className="text-xl font-bold">{title}</h3>
    </div>
  );
};

// ❌ Mauvais
const StoryCard = (props) => {
  return <div style={{borderRadius: '16px'}}><h3>{props.title}</h3></div>
}
```

**Règles :**
- ✅ Utiliser TypeScript avec types explicites
- ✅ Utiliser TailwindCSS pour le style (pas de CSS inline)
- ✅ Composants fonctionnels avec hooks
- ✅ Nommer les composants en PascalCase
- ✅ Utiliser Prettier pour le formatage

### Backend (FastAPI/Python)

```python
# ✅ Bon
from fastapi import APIRouter, HTTPException
from sqlmodel import Session

router = APIRouter()

@router.get("/stories/{story_id}")
async def get_story(story_id: int, session: Session = Depends(get_session)) -> Story:
    """Récupère une histoire par son ID"""
    story = session.get(Story, story_id)
    if not story:
        raise HTTPException(status_code=404, detail="Histoire non trouvée")
    return story

# ❌ Mauvais
@router.get("/stories/{story_id}")
def get_story(story_id):
    story = session.query(Story).filter(Story.id == story_id).first()
    return story
```

**Règles :**
- ✅ Type hints partout
- ✅ Docstrings pour les fonctions
- ✅ Gestion des erreurs explicite
- ✅ Utiliser SQLModel pour les modèles
- ✅ Respecter PEP 8

---

## 📤 Soumettre une Pull Request

### Checklist avant soumission

- [ ] Mon code suit les standards du projet
- [ ] J'ai testé mes changements localement
- [ ] J'ai ajouté des tests si nécessaire
- [ ] J'ai mis à jour la documentation
- [ ] Mon commit message suit les conventions
- [ ] Ma branche est à jour avec `main`

### Processus

1. **Push ta branche**
```bash
git push origin feature/ma-fonctionnalite
```

2. **Ouvre une Pull Request sur GitHub**
   - Titre clair et descriptif
   - Description détaillée des changements
   - Screenshots si changements visuels
   - Références aux issues liées

3. **Template de PR**
```markdown
## 📝 Description
Brève description des changements

## 🎯 Type de changement
- [ ] Bug fix
- [ ] Nouvelle fonctionnalité
- [ ] Breaking change
- [ ] Documentation

## ✅ Checklist
- [ ] Code testé localement
- [ ] Tests ajoutés/mis à jour
- [ ] Documentation mise à jour
- [ ] Pas de console.log/print oubliés

## 📸 Screenshots (si applicable)
[Ajouter captures d'écran]

## 🔗 Issues liées
Closes #123
```

4. **Review & feedback**
   - Attends les retours de review
   - Réponds aux commentaires
   - Effectue les modifications demandées

5. **Merge**
   - Une fois approuvée, ta PR sera mergée ! 🎉

---

## 🐛 Reporter un bug

### Template d'issue bug

```markdown
## 🐛 Description du bug
Description claire et concise du problème

## 📝 Étapes pour reproduire
1. Aller sur '...'
2. Cliquer sur '...'
3. Scroller jusqu'à '...'
4. Voir l'erreur

## ✅ Comportement attendu
Ce qui devrait se passer

## ❌ Comportement actuel
Ce qui se passe réellement

## 📸 Screenshots
[Ajouter captures d'écran]

## 🖥️ Environnement
- OS: [ex: Windows 11]
- Navigateur: [ex: Chrome 120]
- Version Node: [ex: 18.17.0]
- Version Python: [ex: 3.11.5]

## 📋 Logs/Console
```
[Copier les logs d'erreur ici]
```

## ℹ️ Informations additionnelles
Tout autre contexte pertinent
```

---

## 💡 Proposer une fonctionnalité

### Template d'issue feature

```markdown
## 💡 Proposition de fonctionnalité
Description claire de la fonctionnalité

## 🎯 Problème résolu
Quel problème cette fonctionnalité résout-elle ?

## ✨ Solution proposée
Comment proposez-vous de résoudre ce problème ?

## 🔄 Alternatives considérées
Autres solutions envisagées

## 📸 Maquettes/Sketches
[Ajouter visuels si disponibles]

## 📊 Impact utilisateur
Qui bénéficiera de cette fonctionnalité ?
```

---

## 🎨 Standards de design

### Couleurs

Utilise les couleurs définies dans `tailwind.config.js` :
```js
colors: {
  primary: '#f6ad55',    // Orange doux
  secondary: '#fbb6ce',  // Rose pastel
  accent: '#68d391',     // Vert menthe
}
```

### Espacement

Utilise le système de spacing TailwindCSS :
- `p-4` : padding de 1rem
- `m-6` : margin de 1.5rem
- `gap-4` : gap de 1rem

### Typographie

```jsx
// Titres
<h1 className="text-4xl font-black">Titre</h1>

// Corps de texte
<p className="text-base text-gray-700">Texte</p>

// Labels
<label className="text-sm font-semibold">Label</label>
```

---

## 🧪 Tests

### Frontend (React Testing Library)

```typescript
import { render, screen } from '@testing-library/react';
import { StoryCard } from './StoryCard';

test('affiche le titre de l\'histoire', () => {
  render(<StoryCard title="Le Corbeau" duration={5} ageMin={5} />);
  expect(screen.getByText('Le Corbeau')).toBeInTheDocument();
});
```

### Backend (pytest)

```python
def test_get_story_success(client: TestClient):
    """Test récupération d'une histoire existante"""
    response = client.get("/api/stories/1")
    assert response.status_code == 200
    assert response.json()["title"] == "Le Corbeau et le Renard"
```

**Lancer les tests :**
```bash
# Frontend
npm run test

# Backend
pytest backend/tests/ --cov
```

---

## 📞 Questions ?

Si tu as des questions :
- 💬 [Discussions GitHub](https://github.com/flow3flow/doudoulit/discussions)
- 📧 Email : flow3flow@example.com
- 🐛 [Issues](https://github.com/flow3flow/doudoulit/issues)

---

## 🙏 Remerciements

Merci de contribuer à DoudouLit ! Chaque contribution, petite ou grande, aide à créer une meilleure expérience pour les enfants. 💖

---

### ✨ *"Ensemble, transformons chaque histoire en moment magique"* ✨
