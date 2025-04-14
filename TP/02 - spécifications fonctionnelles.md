# Spécifications fonctionnelles – Mini-RPG Web App

## Objectif global

Créer une application frontend qui permet à un joueur de :

- Visualiser son personnage
- Gérer un inventaire d’objets
- Suivre une quête
- Lancer et résoudre des combats simples contre des ennemis

---

## 1. Gestion du personnage

- Affichage de la fiche personnage avec :
    - Nom, classe
    - Points de vie, points de magie, attaque, défense
- Données statiques ou chargées depuis un fichier JSON
- (React) Utilisation de `props` et `state`

---

## 2. Inventaire

- Liste des objets possédés (potions, artefacts)
- Composants visuels pour chaque objet
- Actions disponibles :
    - Acheter un objet
    - Utiliser un objet

---

## 3. Journal de quête

- Liste des étapes de la quête (en cours / terminée)
- Détail d’une étape : titre, description, objectif, récompense
- Action possible : marquer comme terminée
- Possibilité d’ajouter une nouvelle étape quand la précédente est terminée

---

## 4. Combat

- Système de combat simple en tour par tour :
    - Le joueur clique sur “Attaquer”
    - Le monstre riposte
    - Un log affiche les actions successives
- Affichage des PV en temps réel
- Fin de combat :
    - Victoire → récompense et retour à l’écran principal
    - Défaite → affichage “Game Over”
- (React/Next) Utilisation du `state`, conditions d’affichage

---

## 5. Navigation

- Vue `/character` → fiche perso
- Vue `/inventory` → liste des objets
- Vue `/quest` → journal
- Vue `/battle` → combat en cours
- Vue `/` → page d’accueil ou menu

---

## 6. Éléments graphiques fournis

- Avatars de personnage (PNG ou SVG)
- Icônes d’objets
- Illustrations de créatures
- Illustration de PNJ
- Couleurs et typos prédéfinies

---

## 7. Bonus possibles

- Ajout de classes de personnage (guerrier, mage…)
- Choix d’action : défense, sorts, vol à la tire
- Barre de progression pour les PV
- Ajout de bruitages (clic, combat)
