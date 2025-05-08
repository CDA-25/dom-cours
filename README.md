# dom-cours

Le DOM (Document Object Model) est une structure hiérarchique représentant une page HTML  
comme un arbre d’objets que JavaScript peut manipuler pour changer dynamiquement  
le contenu, les styles, les attributs et la structure de la page sans la recharger.  
Le DOM est couramment considerer comme une interface de programmation.  

## Le DOM en JS  

### Sélectionner des éléments  
```js
// Par ID
const titre = document.getElementById("titre");

// Par classe
const boutons = document.getElementsByClassName("btn");

// Par tag
const paragraphs = document.getElementsByTagName("p");

// Moderne (querySelector)
const header = document.querySelector("header"); // premier match
const allBtn = document.querySelectorAll(".btn"); // tous les matchs
```

### Manipulation des classes  
```js
<div class="box" >je suis une div</div>

const box = document.querySelector(".box");

box.classList.add("active");      // Ajoute une classe
box.classList.remove("active");   // Supprime une classe
box.classList.toggle("hidden");   // Ajoute si absente, sinon supprime
box.classList.contains("active"); // Vérifie si la classe est présente
```

### Modifie le text ou HTML  
```js
<h3 id="titre" >je suis un titre</h3>

const titre = document.querySelector("#titre");

titre.textContent = "Nouveau texte";       // Change le texte
titre.innerHTML = "<strong>Important</strong>"; // HTML dynamique
```

### Modifier les attributs  
```js
<a href="https://example.com" target="_blank">Je suis un lien</a>

const lien = document.querySelector("a");

lien.setAttribute("href", "https://google.com");
lien.getAttribute("href"); // "https://google.com"
lien.removeAttribute("target");
```

### Créer et insérer des éléments  
```js
<div id="container" >je suis un container</div>

// Créer une <div>
const newDiv = document.createElement("div");

// Ajouter une classe
newDiv.classList.add("box");

// Ajouter du texte
newDiv.textContent = "Je suis nouveau !";

// Ajouter un attribut
newDiv.setAttribute("id", "nouveau");

// Ajouter un enfant à un parent existant
const container = document.querySelector("#container");
container.appendChild(newDiv);
```

### Exemple d'ajout d'element imbriqué
```js
const list = document.createElement("ul");

for (let i = 1; i <= 3; i++) {
    const li = document.createElement("li");
    li.textContent = "Élément " + i;
    list.appendChild(li);
}

// ajout directement dans la balise body, sans passé par un selecteur
document.body.appendChild(list); 
```

### Supprimer des éléments  
```js
const btn = document.querySelector(".btn");
btn.remove(); // Supprime directement
```































