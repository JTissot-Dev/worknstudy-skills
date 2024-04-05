# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'état (_state_) pour contrôler l'affichage d'un composant  ✔️
- les composants enfants et les _props_ qu'on leur passe  ✔️
- le déclenchement d'instructions en fonction des actions de l'utilisateur  ✔️
- le déclenchement d'instructions en fonction de l'étape du cycle de vie du composant ou du changement de valeur de ses props ✔️
- l'usage d'un reducer (_useReducer_) pour gérer un état composé dans un composant ✔️
- l'état stocké dans un composant avec un _context provider_ et accessible dans ses descendants via `useContext`  ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```typescript
export const SideBar: React.FC = () => {

  const [open, setOpen] = useState<Boolean>(false); // Déclaration du state de type booléan permettant d'afficher / masquer le contenu de la sidebar

  return (
    <aside>
      <button
        onClick={() => setOpen(prev => !prev)} // Event onClick du bouton pour modifier le state Open, passe à true si state à false et false si state à true.
      >
        Toggle open
      </button>
      <div>
      { open && // Ternaire affichant le contenu à condition que open = true.
        <p></p>
        ...
      }
      </div>
    </aside>
  )
};

```

### Utilisation dans un projet ❌ / ✔️

[lien github](https://github.com/JTissot-Dev/task-planner)

Description : Projet copie Trello, utilisation avec drag and drop context notament.

[lien github](https://github.com/JTissot-Dev/portfolio-jt)

Description : Portfolio, utilisation avec framer motion notament.

[lien github](https://github.com/JTissot-Dev/ran-day)

Description : Application permettant d'obtenir un programme d'activités aléatoire sur une journée.

[lien github](https://github.com/JTissot-Dev/laps-map)

Description : Projet en cours, utilisation avec Next.

### Utilisation en production si applicable❌ / ✔️

[lien du projet](https://tasks-planner.fly.dev)

Description : Projet copie Trello, utilisation avec drag and drop context notament.

[lien du projet](https://jtissot-portfolio.fr)

Description : Portfolio, utilisation avec framer motion notament.

[lien du projet](https://ran-day.vercel.app/index)

Description : Application permettant d'obtenir un programme d'activités aléatoire sur une journée.

### Utilisation en environement professionnel  ✔️

Description : Utilisation actuelle dans le cadre du développement d'un SIG, avec leaflet notament.

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
