# 11 secteurs CSS que chaque développeur devrait connaître
# Définition

**Les sélecteurs** définissent les éléments sur lesquelles s'applique un ensemble de règles CSS.

Un sélecteur est une expression qui indique au navigateur à quelle entité HTML s'applique la règle CSS correspondante.

CSS a plusieurs types de sélecteurs 30 environs.

Mais dans ce tutoriel nous allons voir les 11 principaux sélecteurs que vous allez rencontrer partout,

Et au sorti ce tuto les sélecteurs CSS n'orront plus de secret pour vous 😉,

Nous pouvons diviser les sélecteurs CSS en cinq catégories :

**Sélecteurs simples** (sélection d'éléments en fonction du nom, de l'identifiant, de la classe)
**Sélecteurs de combinaisons** (sélection d'éléments sur la base d'une relation spécifique entre eux)
**Pseudo-sélecteurs de classe** (sélection d'éléments en fonction d'un certain état)
**Sélecteurs de pseudo-éléments** (sélectionner et styliser une partie d'un élément)
**Sélecteurs d'attributs** (sélectionner des éléments en fonction d'un attribut ou d'une valeur d'attribut)

# I Les sélecteurs simples

Sélectionnez les éléments en fonction du nom, de l'identifiant, de la classe

## 1. Les sélecteurs de type

Ce sélecteur simple permet de cibler les éléments qui correspondent au nom indiqué.

```html
<p>
	Ma phrase avec la balise P
</p>
<div>
	Ma phrase avec la balise Div
</div>
```

```css
p{
  color: red;
}
```

## 2. Les sélecteurs de classe

Ce sélecteur simple permet de cibler les éléments en fonction de la valeur de leur attribut `class`.

```html
<div class="succes">Félicitations ✨🎊💪</div>
```

```css
.succes{
  background-color: #6EE7B7;
  padding: 5px;
}
```

## 3. Les sélecteurs d'identifiant

Ce sélecteur simple permet de cibler un élément d'un document en fonction de la valeur de son attribut id. Dans un document, il ne doit y avoir qu'un seul élément pour un identifiant donné.

```html
<div id="error">Erreur 😭</div>
```

```css
#error{
  background-color: #fecaca;
  padding: 5px;
}
```

## 4. Le sélecteur universel

Sélectionne tout dans le document et leur applique un style.

```html
<p>Ma phrase avec P</p>
<div class="">Ma phrase avec div</div>
```

```css
* {
  font-weight: bold;
  font-size: 20px;
}
```

## 5. Les sélecteurs d'attribut

Ce sélecteur simple permet de cibler des éléments d'un document en fonction de la valeur d'un de leurs attributs.

```html
<div class="un" title="title1">title001</div>
<div class="deux" title="title2">title002</div>
<div class="trois" title="title3">title003</div>
<div class="quatre" title="title4">title004</div>
```

```css
[title] {
  color: red;
}

[title="title2"] {
  color: blue;
}
```

# II Les combinateurs

## 6. Les sélecteurs de voisin direct

Le combinateur '+' permet de sélectionner les nœuds qui suivent immédiatement un élément donné.

```html
<div class="un" title="title1">title001</div>
<div class="deux" title="title2">title002</div>
<div class="trois" title="title3">title003</div>
<div class="quatre" title="title4">title004</div>
```

```css
.un + .deux {
  background: red;
}
```

## 7. Les sélecteurs de voisins

Le combinateur '~' permet de sélectionner les nœuds qui suivent un élément.

```html
<span>Ici, ce n'est pas rouge.</span>
<p>Voici un paragraphe.</p>
<code>Un peu de code.</code>
<span>Et un autre span.</span>
<code>Encore du code</code>
<span>Ici aussi, c'est rouge</span>
```

```css
p ~ span {
  color: red;
}
```

## 8. Les sélecteurs d'éléments fils

Le combinateur '>' permet de sélectionner les nœuds qui sont des fils directs d'un élément donné.

```html
<div class="mere">
   <div class="enfant1">enfant1</div>
   <div class="enfant2">enfant2</div>
   <div class="enfant3">enfant3</div>
</div>
```

```css
.mere > .enfant2 {
  color : red;
}
```

## 9. Les sélecteurs d'éléments descendants

Cette forme de combinateur permet de sélectionner un élément uniquement si celui-ci « suit » un élément donné et que les deux éléments sont les fils d'un même élément parent.

En d'autres termes, il sélectionne l'élément qui se trouve juste à côté d'un autre élément au même niveau de la hiérarchie.

```html
<div>
    <p>Ma phrase est dans la DIV</p>
    <span>Ma phrase est dans la DIV</span>
</div>
<p>Ma phrase n'est pas dans la DIV</p>
```

```css
div p {
  color : red;
}
```

# III Les pseudo

## 10. Les pseudo-classes

Les pseudo-classes permettent de cibler des éléments selon **une information d'éta**t qui n'est pas stockée dans l'arbre du document.

```html
<span>❤</span>
```

```css
span { 
  font-size : 2rem;
  text-decoration : none;
}

span:hover {
  color : red;
  font-size :  3rem;
}
```

## 11. Les pseudo-éléments

Les pseudo-éléments représentent des entités du document qui ne sont pas décrites en HTML.

```html
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora, beatae, temporibus in modi suscipit voluptates aliquid quibusdam veniam est pariatur ea exercitationem dolore optio numquam debitis repudiandae totam iure nemo!</p>
```

```css

p:first-line {
  color : red;
  font-size :  3rem;
}
```

> Attention : Ne confondez pas pseudo-éléments et **`pseudo-classes`**. La distinction est la suivante : Les pseudo classes désignent un état de l'élément, par exemple un lien qui a déjà été visité, un élément survolé par la souris, etc.

> Les pseudo éléments désignent une partie d'un élément. Par exemple **`::first-line`** désigne la première ligne de texte de l'élément.

> Les noms des pseudo-éléments commencent par un double deux points ( **`::`** ).
