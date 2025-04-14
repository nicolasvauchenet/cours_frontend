# Évaluation : Développement Frontend Moderne

### Travail individuel – Durée : 1h30

---

## 1. QCM (5 questions – 10 points)

**Consigne : Une seule réponse correcte par question.**

1. Quelle technologie permet de créer un composant HTML réutilisable avec encapsulation via le Shadow DOM ?
    - [ ] React
    - [ ] Next.js
    - [ ] Web Component
    - [ ] JSX

2. Quelle méthode React permet de créer une variable d'état dans un composant fonctionnel ?
    - [ ] useClass
    - [ ] useEffect
    - [ ] useState
    - [ ] useVar

3. Dans Next.js, quelle fonction permet de récupérer des données à la génération statique de pages ?
    - [ ] getServerSideProps
    - [ ] getClientProps
    - [ ] useEffect
    - [ ] getStaticProps

4. Dans l’approche Atomic Design, quel est le niveau le plus petit de composant ?
    - [ ] Organisme
    - [ ] Atome
    - [ ] Page
    - [ ] Molécule

5. Quelle est la fonction du Virtual DOM dans React ?
    - [ ] Il permet de styliser les composants avec CSS.
    - [ ] Il optimise le rendu en limitant les manipulations du vrai DOM.
    - [ ] Il remplace complètement le DOM classique.
    - [ ] Il gère les routes côté client.

---

## 2. Vrai/Faux (5 questions – 10 points)

**Consigne : Indiquez si l’affirmation est vraie ou fausse, puis justifiez votre réponse en une phrase.**

1. Le DOM peut être modifié uniquement en HTML. (Vrai / Faux)

2. Un composant React peut avoir plusieurs `useState`. (Vrai / Faux)

3. Un composant Web Component peut être utilisé dans une app React. (Vrai / Faux)

4. `useEffect` s'exécute toujours avant le rendu initial du composant. (Vrai / Faux)

5. Dans Next.js, les pages sont définies manuellement dans un fichier de configuration. (Vrai / Faux)

---

## 3. Questions courtes (5 questions – 10 points)

**Consigne : Répondez en 2 à 3 phrases maximum.**

1. À quoi sert le Shadow DOM dans un Web Component ?

2. Quelle différence faites-vous entre `props` et `state` dans React ?

3. Expliquez comment vous organiseriez vos composants avec Atomic Design.

4. Quelle est la différence entre `getStaticProps` et `getServerSideProps` dans Next.js ?

5. Pourquoi le Virtual DOM améliore-t-il les performances d’une application React ?

---

## 4. Étude de cas / Analyse d’un problème (30 min – 15 points)

**Consigne : Lisez le cas suivant et répondez aux questions en expliquant vos choix.**

### Contexte

Vous travaillez dans une startup qui développe un site de réservation d’activités sportives.  
Le site doit permettre à l’utilisateur de :

- Rechercher des activités selon la ville et la date.
- Afficher une fiche détaillée pour chaque activité.
- Réserver une activité en ligne via un formulaire.

Le projet doit être moderne, rapide, facilement maintenable, et scalable. Vous êtes en charge du développement frontend.

---

### Questions d’analyse

1. Quelle technologie frontend utiliseriez-vous (Vanilla JS, Web Components, React, Next.js) ?  
   Justifiez votre choix.

2. Comment structureriez-vous le projet pour qu’il soit maintenable ?  
   Donnez un exemple de structure de dossiers avec Atomic Design.

3. Comment récupérez-vous les données d’activités depuis une API ?  
   Expliquez où et comment vous intégrez cet appel de données.

4. Quelles optimisations mettriez-vous en place pour améliorer les performances perçues du site ?

---

## 5. Rédaction technique / Justification d’un choix (30 min – 15 points)

**Consigne : Choisissez **un seul** sujet parmi les trois suivants et rédigez une réponse argumentée (10 à 15 lignes).**

### Sujet 1

Vous devez créer un composant de **carte de produit** dans React ou en Web Component.  
Expliquez comment vous vous y prenez, quels props ou attributs vous gérez, et comment vous assurez sa réutilisabilité.

### Sujet 2

Vous devez créer une **page de détail dynamique** dans Next.js.  
Expliquez les étapes nécessaires pour mettre en place la route dynamique et récupérer les données associées.

### Sujet 3

Vous devez intégrer un système de **notation en étoiles** sur une fiche produit.  
Expliquez comment vous gérez l’état du composant, les interactions utilisateur et son accessibilité.

---

## Barème

| Partie                    | Points |
|---------------------------|--------|
| QCM                       | 10     |
| Vrai/Faux + justification | 10     |
| Questions courtes         | 10     |
| Étude de cas              | 15     |
| Rédaction technique       | 15     |
| **Total**                 | **60** |

---

**Bonne chance à vous !**
