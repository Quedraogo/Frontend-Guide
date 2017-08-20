---
title: Frontend Guide
---
## Folder Structure

```xml

Prototype/
|- assets/
|    |- fonts/
|    |- images/
|    |- js/
|    |- scss/
|- components/
|    |- Utils/
|    |- Atoms/
|    |- Molecules/
|    |- Organisms/
|    |- Templates/
|    |- Pages/
|- docs/
|    |- index.md
|    |- getting-started.md
|    |- ...
|- public/
|    |- css/
|    |- fonts/
|    |- img/
|    |- js/
|- .editorconfig
|- gulpfile.js
|- package.json

```


## The Component Folder (Atomic Design Structure)

```xml
components/
|- Utils/
|- Atoms/
|- Molecules/
|- Organisms/
|- Templates/
|- Pages/
```

- **Utils**
This folder will need to define the foundation, i.e., a set of global classes, mixins, variables and styles that can be used anywhere and anytime.
It holds some global definitions like the reset, global variables, as well as Sass tools and helpers that shall be reused across the project.

```xml
Utils/
|- base/
|    |- normalize.scss
|    |- global.scss
|- functions/
|- mixins/
|- variables.scss
```

---

- **Atoms**
Atoms are the basic building blocks. Atoms can also include more abstract elements like color palettes, fonts and even more invisible aspects of an interface like animations.

```xml
Atoms/
|- fonts/
|- forms/
|    |- input
|    |- label
|    |- placeholder
|- icons/
|- images/
|    |- stage/
|    |- article/
|- text/
|    |- abstract/
|    |- heading/
|    |- text/
|    |    |- blockquote/
|    |    |- list/
|    |    |- paragraph/
|    |    |- spacing/
|    |    |- table/
|- ...
```

---

- **Molecules**
Molecules are relatively simple groups of UI elements functioning together as a unit. 
For example, a form label, search input, and button can join together to create a search form molecule. 
These molecules take on their own properties and serve as the backbone of our design system.

```xml

Molecules/
|- button/
|    |- button.config.yml
|    |- button.hbs
|    |- button.js
|    |- button.scss
|    |- button.doc.md
|- forms/
|    |- form-control/
|    |    |- form-control.config.yml
|    |    |- form-control.hbs
|    |    |- form-control.js
|    |    |- form-control.scss
|    |    |- form-control.doc.md
|    |- input-group/
|    |    |- ...
|    |- selectbox/
|    |    |- ...
|    |- ...
|- link/
|    |- link.config.yml
|    |- link.hbs
|    |- link.scss
|- navigation/
|    |- breadcrumb/
|    |- main-nav/
|    |- meta-nav/
|    |- pager/
|    |- ...
|- functionals/
|    |- collapse/
|    |- modal/
|- ...

```

---
- **Organisms**
Organisms are relatively complex UI components composed of
groups of molecules and/or atoms and/or other organisms, such as a header or a footer.

```xml

Organisms/
|- header/
|- footer/
|- forms/
|    |- contact-form/
|    |- login-form/
|    |- search-form/
|- modules/
|    |- accordion/
|    |- card/
|    |- linklist/
|    |- slider/
|    |- tab/
|- ...

```

---

- **Templates**
Templates are page-level objects that place components into a layout and articulate the design’s underlying content structure.
To build on our previous example, we can take the header organism and apply it to a homepage template.

```xml

Templates/
|- homepage/
|- list-view/
|- single-view/
|- ...

```

---

- **Pages**
Finally, a page apply real content to templates and articulate variations to demonstrate the final UI and test the resilience of the design system. Pages allow us to test and see how all the elements fit together.

```xml

Pages/
|- Homepage
|- Doorpages
|- Suchergebnisseite
|- Einzelsicht
|- ...

```
