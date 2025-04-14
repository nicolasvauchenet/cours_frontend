# Manipulation du DOM et gestion des événements

## Objectifs de cette section

Dans cette section, vous allez apprendre à manipuler plus finement le DOM à travers la sélection d’éléments, la
modification de contenu, et la gestion d’événements utilisateurs.  
À la fin de cette section, vous serez capable de :

- Cibler un ou plusieurs éléments dans le DOM.
- Ajouter dynamiquement du contenu à une page web.
- Gérer les événements utilisateur avec `addEventListener`.
- Générer une liste d’éléments à partir d’un tableau statique.

---

## 1. Sélectionner et modifier le contenu du DOM

JavaScript permet de sélectionner des éléments avec différentes méthodes :

- `getElementById()` pour un élément avec un identifiant.
- `querySelector()` pour cibler un élément selon un sélecteur CSS.
- `querySelectorAll()` pour récupérer une **NodeList** d’éléments correspondants.

On peut ensuite modifier leur contenu avec `textContent`, `innerHTML`, `classList`, `style`, etc.

### Exemple : Modifier dynamiquement le texte d’un élément

```html
<!-- index.html -->
<p id="message">Bonjour !</p>
<button id="changer">Changer le message</button>
```

```javascript
// script.js
document.getElementById("changer").addEventListener("click", () => {
    const msg = document.getElementById("message");
    msg.textContent = "Bonne journée !";
});
```

---

## 2. Ajouter dynamiquement des éléments

Il est possible de créer de nouveaux éléments HTML avec `document.createElement()`, puis de les insérer dans le DOM avec
`appendChild()` ou `append()`.

### Exemple : Ajouter un élément à une liste

```html
<!-- index.html -->
<ul id="liste"></ul>
```

```javascript
// script.js
const ul = document.getElementById("liste");
const li = document.createElement("li");
li.textContent = "Nouvelle tâche";
ul.appendChild(li);
```

---

## 3. Réagir aux événements utilisateur

Les événements sont des actions comme un clic ou une saisie.  
La méthode `addEventListener()` permet d’exécuter une fonction lorsqu’un événement se produit.

### Exemple : Ajouter un élément dans une liste lors d’un clic

```html
<!-- index.html -->
<ul id="tasks"></ul>
<button id="add">Ajouter une tâche</button>
```

```javascript
// script.js
document.getElementById("add").addEventListener("click", () => {
    const ul = document.getElementById("tasks");
    const li = document.createElement("li");
    li.textContent = "Tâche ajoutée dynamiquement";
    ul.appendChild(li);
});
```

---

## 4. Exercice de mise en pratique

### Consignes

1. Reprenez le projet commencé à la section précédente.
2. Dans votre fichier JavaScript, créez un **tableau contenant 3 tâches** (ex. : “Acheter du pain”, “Sortir le chien”,
   “Appeler Mamie”).
3. Lors du chargement de la page, générez dynamiquement une liste `<ul>` contenant une `<li>` pour chaque tâche.
4. Supprimez le bouton de la section précédente : les tâches doivent s’afficher directement.

### Organisation attendue

```bash
/exercices
└── 02-liste-taches
    ├── index.html
    └── script.js
```
