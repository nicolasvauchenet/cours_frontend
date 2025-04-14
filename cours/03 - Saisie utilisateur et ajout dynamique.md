# Saisie utilisateur et ajout dynamique d’éléments

## Objectifs de cette section

Cette section vous apprend à **récupérer les données saisies par l’utilisateur** à travers un formulaire, à les traiter
en JavaScript, et à les afficher dynamiquement dans la page.  
À la fin de cette section, vous serez capable de :

- Récupérer la valeur d’un champ de formulaire via JavaScript.
- Ajouter dynamiquement une entrée dans une liste.
- Vider un champ de saisie après soumission.
- Empêcher le rechargement automatique d’un formulaire.

---

## 1. Récupérer une saisie utilisateur

Pour interagir avec un formulaire, on commence par :

- Ajouter un champ `<input>` dans le HTML.
- Cibler ce champ via JavaScript (`getElementById`, `querySelector`…).
- Lire sa valeur via la propriété `.value`.

### Exemple : afficher la valeur d’un champ dans la console

```html
<!-- index.html -->
<input id="taskInput" type="text" placeholder="Nouvelle tâche">
<button id="log">Afficher</button>
```

```javascript
// script.js
document.getElementById("log").addEventListener("click", () => {
    const value = document.getElementById("taskInput").value;
    console.log(value);
});
```

---

## 2. Ajouter une tâche à partir d’un champ de saisie

Vous pouvez créer une tâche à partir d’un champ `<input>` et l’ajouter dynamiquement à une liste avec `appendChild()`.

Il faut :

- Cibler le champ.
- Créer un élément `<li>` contenant la valeur de l’input.
- Ajouter cet élément dans la liste existante.

### Exemple : ajouter une tâche avec un bouton

```html
<!-- index.html -->
<input id="taskInput" type="text" placeholder="Nouvelle tâche">
<button id="add">Ajouter</button>
<ul id="taskList"></ul>
```

```javascript
// script.js
document.getElementById("add").addEventListener("click", () => {
    const input = document.getElementById("taskInput");
    const value = input.value;
    if (value.trim() !== "") {
        const li = document.createElement("li");
        li.textContent = value;
        document.getElementById("taskList").appendChild(li);
        input.value = "";
    }
});
```

---

## 3. Gérer la soumission d’un formulaire

Un formulaire déclenche un événement `submit` qui provoque un rechargement de la page.  
Pour l’intercepter et le traiter côté client :

- Utilisez `event.preventDefault()` dans le gestionnaire.
- Traitez les données à la volée.

### Exemple : intercepter un formulaire et ajouter une tâche

```html
<!-- index.html -->
<form id="taskForm">
    <input id="taskInput" type="text" placeholder="Nouvelle tâche">
    <button type="submit">Ajouter</button>
</form>
<ul id="taskList"></ul>
```

```javascript
// script.js
document.getElementById("taskForm").addEventListener("submit", (e) => {
    e.preventDefault();
    const input = document.getElementById("taskInput");
    const value = input.value;
    if (value.trim() !== "") {
        const li = document.createElement("li");
        li.textContent = value;
        document.getElementById("taskList").appendChild(li);
        input.value = "";
    }
});
```

---

## 4. Exercice de mise en pratique

### Consignes

1. Reprenez le projet commencé précédemment.
2. Ajoutez un formulaire contenant :
    - Un champ de saisie `<input>` pour écrire une tâche.
    - Un bouton “Ajouter”.

3. Lors de la soumission :
    - Empêchez le rechargement de la page.
    - Créez un élément `<li>` avec la valeur saisie.
    - Ajoutez cet élément à la liste existante.
    - Videz le champ de saisie.

### Organisation attendue

```bash
/exercices
└── 03-saisie-tache
    ├── index.html
    └── script.js
```
