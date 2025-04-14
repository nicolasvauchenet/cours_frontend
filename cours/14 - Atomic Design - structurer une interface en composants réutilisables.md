# Atomic Design : structurer une interface en composants réutilisables

## Objectifs de cette section

Construire une interface cohérente et réutilisable nécessite une **méthode de structuration**.  
Vous allez découvrir **l’Atomic Design**, une méthode de conception qui permet d’organiser vos composants React en *
*unités logiques et hiérarchiques**.  
À la fin de cette section, vous serez capable de :

- Comprendre les principes de l’Atomic Design.
- Identifier et classer vos composants dans 5 niveaux hiérarchiques.
- Structurer un design system basé sur la réutilisabilité.
- Organiser votre projet React selon cette approche.

---

## 1. Qu’est-ce que l’Atomic Design ?

L’Atomic Design est une **méthodologie inventée par Brad Frost** qui consiste à organiser les composants d’une interface
en 5 niveaux :

1. **Atoms** : les éléments les plus simples (bouton, champ de formulaire, icône…).
2. **Molecules** : combinaison de plusieurs atoms (champ + label, bouton + icône).
3. **Organisms** : groupe structuré de molecules (formulaire, header, carte produit…).
4. **Templates** : disposition générale d’une page avec des zones de contenu.
5. **Pages** : application du template avec des contenus concrets (données réelles).

---

## 2. Pourquoi structurer ainsi ?

Cette hiérarchie apporte :

- Une **meilleure réutilisabilité** des composants.
- Une **cohérence visuelle** sur toute l’application.
- Une **meilleure maintenabilité** à mesure que le projet grandit.
- Un pont naturel entre **conception UI/UX** et **développement frontend**.

---

## 3. Appliquer l’Atomic Design à un projet React

Un projet React peut être structuré avec des dossiers représentant chaque niveau :

- `/components/atoms`
- `/components/molecules`
- `/components/organisms`
- `/components/templates`
- `/pages` (géré par React Router ou Next.js)

### Exemple : structuration de composants

```javascript
// components/atoms/Button.jsx
function Button({children, onClick}) {
    return <button onClick={onClick}>{children}</button>;
}

export default Button;
```

```javascript
// components/molecules/SearchBar.jsx
import Button from "../atoms/Button";

function SearchBar({value, onChange, onSearch}) {
    return (
        <div>
            <input type="text" value={value} onChange={onChange}/>
            <Button onClick={onSearch}>Rechercher</Button>
        </div>
    );
}

export default SearchBar;
```

```javascript
// components/organisms/ProductCard.jsx
import Button from "../atoms/Button";

function ProductCard({title, image, onBuy}) {
    return (
        <div>
            <img src={image} alt={title}/>
            <h3>{title}</h3>
            <Button onClick={onBuy}>Acheter</Button>
        </div>
    );
}

export default ProductCard;
```

```javascript
// components/templates/ProductPageTemplate.jsx
function ProductPageTemplate({header, products}) {
    return (
        <div>
            <header>{header}</header>
            <main>{products}</main>
        </div>
    );
}

export default ProductPageTemplate;
```

```javascript
// pages/HomePage.jsx
import ProductPageTemplate from "../components/templates/ProductPageTemplate";
import ProductCard from "../components/organisms/ProductCard";

function HomePage() {
    const products = [
        {title: "Produit 1", image: "img1.jpg"},
        {title: "Produit 2", image: "img2.jpg"},
    ];

    return (
        <ProductPageTemplate
            header={<h1>Bienvenue</h1>}
            products={products.map((p, i) => (
                <ProductCard key={i} title={p.title} image={p.image} onBuy={() => {
                }}/>
            ))}
        />
    );
}

export default HomePage;
```

---

## 4. Exemple d'application simple

On peut imaginer une interface de type e-commerce :

- **Atom** : `Button`, `Input`, `Text`
- **Molecule** : `SearchBar` (Input + Button), `ProductInfo` (Title + Price)
- **Organism** : `ProductCard`, `Navbar`
- **Template** : `ProductPageTemplate` (layout de page)
- **Page** : `HomePage`, `ProductPage`, `CartPage`

---

## 5. Exercice de mise en pratique

### Consignes

1. Créez la structure suivante dans un projet React :

- Atom : un bouton
- Molecule : une search bar (champ + bouton)
- Organism : une carte produit (titre, image, bouton)
- Template : une page avec un header et une liste de cartes
- Page : une `HomePage` qui utilise ce template

### Organisation attendue

```bash
/src
├── components
│   ├── atoms
│   │   └── Button.jsx
│   ├── molecules
│   │   └── SearchBar.jsx
│   ├── organisms
│   │   └── ProductCard.jsx
│   ├── templates
│   │   └── ProductPageTemplate.jsx
├── pages
│   └── HomePage.jsx
├── App.jsx
└── main.jsx
```
