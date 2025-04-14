# TP : Mini-RPG Web App

## Objectif du projet

Créer une application frontend de type **mini-RPG**, qui permettra au joueur de :

- consulter son personnage,
- gérer un petit inventaire,
- lancer des combats contre des ennemis.

Ce TP se déroulera en **trois séances**, et permettra de mettre en œuvre les notions abordées tout au long du cours :

- Web Components
- React et gestion de l’état
- Atomic Design et Next.js

---

## Organisation des séances

### Web Components

- Introduction à la logique du RPG
- Création de composants natifs :
    - `<character-card>`
    - `<item-slot>`
    - `<battle-log>`
- Manipulation du DOM, événements personnalisés, encapsulation avec Shadow DOM
- Comparaison avec une version équivalente en React à venir

### Prototype React

- Recréation de la logique en React
- Mise en place d’un composant `Battle`
- Utilisation du `state` pour suivre les points de vie et l’historique du combat
- Intégration d’un personnage unique pré-déterminé
- Début de réflexion sur la structure Atomic Design pour la suite

### Projet final en Next.js

- Création d’un projet Next.js complet
- Mise en place du routing entre les vues :
    - `/character` – fiche du PJ
    - `/inventory` – objets du joueur
    - `/quest` – journal de quête
    - `/battle` – interface de combat
- Intégration de données statiques (JSON)
- Organisation des composants selon Atomic Design
- Bonus : ajout de visuels (personnages, items, monstres) fournis

---

## Outils et livrables

- Diagramme de cas d’utilisation du jeu
- (Optionnel) Diagramme d’activité pour le système de combat
- Web Components natifs (fichiers JS + HTML démo)
- Composants React (App fonctionnelle en local)
- Projet Next.js proprement organisé (`/pages`, `/components`, `/styles`, etc.)

---

## Objectifs pédagogiques

- Mettre en œuvre les **Web Components** sans framework
- Expérimenter la même logique en **React** pour en voir les avantages
- Appliquer une structuration propre avec **Atomic Design** et **Next.js**
- Favoriser le travail collaboratif :
    - discussion, pair programming, partages d’astuces
    - construction collective de l’interface
