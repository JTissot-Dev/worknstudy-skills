# REST API

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les verbes HTTP  ✔️
- les statuts HTTP  ✔️
- les endpoints  ✔️
- CORS  ✔️
- la nomenclature recommandée pour les routes  ✔️

## 💻 J'utilise

### Un exemple personnel commenté  ✔️

``` typescript
adWs.post("/ads", async (req, res) => { // end point pour l'ajout d'un "ad" , prend en parametre le chemin, et une fonction de rapelle contenant un objet reg pour les élement de la requête et res pour la réponse.

  try {

    const postAd: AdData = req.body; // récupération des données présente dans le corp de la requête
    const category: Category = await Category.findOne({ // Recherche de la catégorie correspondante en base de données via TypeOrm
      where: {
        name: postAd.category,
      }
    });
  
    const tags: Tag[] = req.body.tags ? req.body.tags.map(async (tag: string) => { // Traitement des tags récupérés dans le corp de la requête, et gestion de la création du tag en BD si non existant.
      const tagFound = await Tag.findOneBy({ name: tag});
      if (tagFound) return tagFound;
  
      const newTag = new Tag();
      newTag.name = tag;
      await newTag.save();
      return newTag;
    }) : [];
  
    // Création du nouveau tag
    const ad: Ad = new Ad(); 
    ad.title = postAd.title;
    ad.description = postAd.description;
    ad.owner = postAd.owner;
    ad.price = Number(postAd.price);
    ad.picture = postAd.picture;
    ad.location = postAd.location;
    ad.category = category;
    ad.tags = await Promise.all(tags);
  
    // Validation des données, renvoi une erreur 422 si les données ne sont pas valide.
    const errors = await validate(ad);
    if (errors.length > 0) {
      return res.status(422).send(errors); 
    }
  
    ad.save(); // Ajout en BD via TypeOrm
    res.status(201).send(); // Renvoi un succès 201 si le serveur est parvenu à créer l'élément.

  } catch (error) {

      // Renvoi une erreur 500 si le serveur n'est pas parvenu à exécuter la demande.
      console.log(error);
      res.status(500).send();

  }
  
});
```

### Utilisation dans un projet ❌

[lien github](...)

Description :

### Utilisation en production si applicable❌

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

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
