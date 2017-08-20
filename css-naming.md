---
title: Frontend Guide
---
## Naming Conventions
Naming Conventions (Namenskonventionen) in CSS sorgen für Konsistent, besseres Verständnis, stabileren Code, 
bessere Lesbarkeit, mehr Transparenz und erleichtern die gemeinsame Arbeit am Projekt.

**Gute Namenskonvention geben Auskunft darüber:**
* Was eine Klasse tut,
* Wo eine Klasse verwendet werden kann,
* Wozu (sonst) eine Klasse gehört.


**wir unterscheiden zwischen folgenden Typen von Klassennamen**

* beschreibende Klassennamen (.btn-red)
* Kontextbezogene Klassennamen (.btn-submit)
* funktionelle Klassennamen (.btn-primary)

Wann immer möglich, sollte auf funktionelle Klassen gesetzt werden.
Gerade für größere/wachsende Projekte sind sie die bessere Wahl und sollten gegenüber 
kontextbezogenen und beschreibenden Klassen bevorzugt werden.

https://erdmann-freunde.de/css-kurs/teil1-css-klassen-benennen/


**Currently following the naming methodologie BEM (not strictly).**

* using numbers and lowercase Latin characters.
* Individual words within names are separated by a hyphen (-).

---

**Example BEM-tree**


```html

<ul class="menu">
  <li class="menu__item">
    <a class="menu__link">
      <span class="menu__text"></span>
    </a>
  </li>
</ul>

.menu {}
.menu__item {}
.menu__link {}
.menu__text {}

```

- **Block name**
  A block name defines a namespace for elements and modifiers.The namespace defined by the name of a block identifies an element as belonging to the block. An element name is delimited by a double underscore (__).
- **Element name**
  Íf a block has several identical elements, such as in the case of menu items, all of them will have the same name menu__item. Important! Using elements within elements is not recommended by the BEM methodology.


## Mixes
- Combine the behavior and styles of multiple entities without duplicating code.
- Apply the same formatting to different HTML elements.

```html

<!-- `header` block -->
<header class="header">
    <!-- Added the `header__button` class to the `button` block -->
    <button class="button header__button">...</button>
</header>

<!-- `form` block -->
<form class="form" >
    <button class="button">...</button>
</form>

```

**CSS implementation of a button:**
```css

.button {
    font-family: Arial, sans-serif;
    border: 1px solid black;
}

```

**CSS implementation of the button element in the header block:**
```css

.header__button {
    margin: 30px;
    position: relative;
}

```
