# Suppression d’éléments et gestion des événements multiples

## Objectifs de cette section

Vous allez apprendre à **supprimer dynamiquement des éléments du DOM** et à **gérer plusieurs événements similaires**
sur différents éléments.  
À la fin de cette section, vous serez capable de :

- Ajouter un bouton de suppression à chaque élément généré.
- Supprimer dynamiquement un élément du DOM avec `remove()`.
- Attacher un événement à un ensemble d’éléments.
- Utiliser `event.target` pour identifier l’élément cliqué.

---

## 1. Supprimer un élément du DOM

JavaScript permet de retirer un élément avec la méthode `.remove()`.  
On peut l’utiliser dans une fonction appelée au clic sur un bouton “Supprimer”.

### Exemple : supprimer un élément au clic

```html
<!-- index.html -->
<p id="texte">Ceci est un paragraphe</p>
<button id="supprimer">Supprimer</button>
```

```javascript
// script.js
document.getElementById("supprimer").addEventListener("click", () => {
    const element = document.getElementById("texte");
    element.remove();
});
```

---

## 2. Générer une liste avec des boutons de suppression

Lorsqu’on ajoute une tâche, on peut lui ajouter un bouton pour la supprimer, qui sera lui aussi généré dynamiquement.

Il faut :

- Créer un élément `<li>` contenant la tâche.
- Créer un bouton `<button>Supprimer</button>`.
- Ajouter un `addEventListener` au bouton pour qu’il supprime le `<li>` parent.

### Exemple : ajout + suppression dynamique

```javascript
// script.js
const ul = document.getElementById("taskList");
const li = document.createElement("li");
li.textContent = "Nouvelle tâche";

const btn = document.createElement("button");
btn.textContent = "Supprimer";

btn.addEventListener("click", () => {
    li.remove();
});

li.appendChild(btn);
ul.appendChild(li);
```

---

## 3. Identifier l’élément à supprimer avec `event.target`

Lorsqu’un événement se déclenche, l’objet `event` permet de savoir quel élément l’a déclenché grâce à `event.target`.  
Cela permet d’écrire une seule fonction de suppression, réutilisable pour tous les boutons.

### Exemple : utiliser `event.target` pour supprimer le bon élément

```javascript
// script.js
document.getElementById("taskList").addEventListener("click", (e) => {
    if (e.target.tagName === "BUTTON") {
        const li = e.target.closest("li");
        if (li) li.remove();
    }
});
```

⚠️ Ce dernier exemple suppose que chaque bouton de suppression est dans un `<li>`, et que l’événement est attaché au
parent commun `<ul>`, pour une approche dite event delegation.

---

## 4. Exercice de mise en pratique

### Consignes

1. Reprenez le projet de la section précédente.
2. Pour chaque tâche ajoutée, créez un bouton “Supprimer” placé à côté du texte.
3. Lorsque ce bouton est cliqué, la tâche correspondante est supprimée de la liste.

### Organisation attendue

```bash
/exercices
└── 04-suppression-tache
    ├── index.html
    └── script.js
```
