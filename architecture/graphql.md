# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL ✔️
- les besoins auxquels répond GraphQL  ✔️
- la définition d'un schéma
- Query  ✔️
- Mutation  ✔️
- Subscription ❌ 

## 💻 J'utilise

### Un exemple personnel commenté  ✔️

``` typescript
  const [delAd] = useMutation(DEL_AD, { // Utilisation du hook useMutation de apollo client pour réaliser la suppression d'un élément "Ad", DEL_AD correspond à la query GraphQL.
    variables: { delAdId: Number(router.query.id) }, // Passage des variables à la query GraphQL
    update(cache, { data: { delAd } }) { // Mise à jour du cache: data liste des annonces récupéré dans un autre composant, afin d'actualiser la liste d'item sans celui supprimer.
      cache.modify({
        fields: {
          ads(existingAds = []) { // ads permet de spécifié sur quelle data du cache apollo on intervient
            return existingAds.filter(
              (adRef: any) => adRef.__ref !== `Ad:${delAd.id}` // ici on filtre les éléments dont la référence de l'élément dans le cache apollo ne correspondent pas à celui supprimer.
            );
          }
        }
      });
    }
  });
```

### Utilisation dans un projet  ✔️

[lien github](https://github.com/JTissot-Dev/laps-map)

Description : Projet en cours, utilisation avec Next.

### Utilisation en production si applicable ❌ 

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌

Description :

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
