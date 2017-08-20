---
title: Frontend Guide
---
## Naming Conventions
CSS Namenskonventionen (naming conventions) sorgen für Konsistent, besseres Verständnis, stabileren Code, bessere Lesbarkeit, mehr Transparenz und erleichtern die gemeinsame Arbeit am Projekt.

**Gute Namenskonvention geben Auskunft darüber:**
* was eine Klasse tut,
* wo eine Klasse verwendet werden kann,
* wozu (sonst) eine Klasse gehört.


**Wir können zwischen folgenden Typen von Klassennamen unterscheiden**

* beschreibende Klassennamen (.btn-red)
* Kontextbezogene Klassennamen (.btn-submit)
* funktionelle Klassennamen (.btn-primary)

Wann immer möglich, sollte auf funktionelle Klassen gesetzt werden.
Gerade für größere/wachsende Projekte sind sie die bessere Wahl, da sie sich unabhängig von ihrem Kontext wiederverwenden lassen, das Schema ist nachvollziehbar und gut zu erweitern.

```css
// korrekte darstellung wird an Kontext gebunden, 
// dadurch schlechte Wiederverwendbarkeit und wenig intuitiv,
// schlechte selektorperformance
.form li button {
  background-color: blue;
}

// Risiko zu veralten, schlechte Wartbarkeit
.btn-blue {
  background-color: blue;
}

// beschreibt Funktion (vermutlich absenden eines Formulars)
// Klasse lässt sich nur mit Einschränkungen auch auf andere Buttons anwenden
.btn-submit {
  background-color: blue;
}

// Nicely abstracted, very portable, doesn’t risk becoming out of date.
.btn-primary {
  background-color: blue;
}
```
Quellen:
https://cssguidelin.es/#naming
https://erdmann-freunde.de/css-kurs/teil1-css-klassen-benennen/

---
# Following the naming methodologie BEM (not strictly).

![Alternativer Text](https://en.bem.info/ChhNUMI54FMJQEmmBRKqJJUPIJg.svgd "These problems are solved by BEM methodology, a development approach allowing to achieve flexible and maintainable code.")

* using numbers and lowercase Latin characters.
* Individual words within names are separated by a hyphen (-).

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
