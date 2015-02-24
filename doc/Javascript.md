### 2. Javascript
#### 2.i Code patterns
#### 2.ii Literal Object
#### 2.iii Prototype
#### 2.iv Functions
##### Callback
##### Memoization

##### Promise

Promises have been around for a while in the form of libraries, such as:

- Q
- when
- WinJS
- RSVP.js

The above and JavaScript promises share a common, standardised behaviour called Promises/A+. If you're a jQuery user, they have something similar called Deferreds. However, Deferreds aren't Promise/A+ compliant, which makes them subtly different and less useful, so beware. jQuery also has a Promise type, but this is just a subset of Deferred and has the same issues.

#### 2.v. Bonnes pratiques
##### Modulariser
http://addyosmani.com/writing-modular-js/

###### Closure
###### CommonJS
###### AMD pattern
http://requirejs.org/docs/whyamd.html 

##### Compression du code
##### Quelques notions d’optimisation
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management

Eviter les manipulations de DOM
écriture mais aussi lecture

1. Changer la DOM en batch

MAL
```js
// This will incurr 5 screen refreshes
jQuery('#dialog-window').width(600).height(400).css('position': 'absolute')
                       .css('top', '200px').css('left', '200px');
```

BON
```js
// Let jQuery handle the batching
jQuery('#dialog-window').css({
     width: '600px',
     height: '400px',
     position: 'absolute',
     top: '200px',
     left: '200px'
);
```

Mieux
```js
// Or even better use a CSS class.
jQuery('#dialog-window').addClass('mask-aligned-window');
```

2. Templating
- http://ejohn.org/blog/javascript-micro-templating/
- http://www.html5rocks.com/en/tutorials/webcomponents/template/
- http://plugins.jquery.com/loadTemplate/
- Mustache
- Handlebars

En résumé

- Garder la DOM simple
- Construire la DOM séparément puis l'insérer dans la page
- Garder des références aux éléments de DOM courament manipulés
- Supprimer les écouteurs d'events inutilisés
- Attention aux events répétitif (scroll etc.) _.debounce
- Use ```push()```, ```pop()```, ```shift()```, ```join()``` même sur les ``string```

mais aussi
- https://developers.google.com/speed/articles/optimizing-javascript
- http://desalasworks.com/article/javascript-performance-techniques/
- http://api.jquery.com/promise/

##### Tests automatisés

#### 2.vi. Javascript Tools
##### Debug
##### Libraries / Frameworks
- https://github.com/components Liste les incontournables du deévelopeur frontend moderne
- Angular.js



#### 2.vii. Ressources

##### Livres
* [Javascript Patterns](http://shop.oreilly.com/product/9780596806767.do)
* [Eloquent Javascript](http://search.oreilly.com/?q=eloquent+javascript)
* [essential js design patterns](http://addyosmani.com/resources/essentialjsdesignpatterns/book/)

##### Sites web
* [Can I Use](http://caniuse.com/)
* http://www.html5rocks.com/en/
* [developer.mozilla.org - Closure](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* Promises: http://www.html5rocks.com/en/tutorials/es6/promises/
* [developer.mozilla.org - Memory_Management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management)
* http://ejohn.org/blog/javascript-micro-templating/
* http://www.html5rocks.com/en/tutorials/webcomponents/template/
* http://plugins.jquery.com/loadTemplate/

##### Vidéos
* [JS must watch](https://github.com/bolshchikov/js-must-watch)
* [Dev on Stage - Youtube playlist](https://www.youtube.com/playlist?list=PL8l7YtFPKywaQ_VhZSeElM8D1JWpJKtKV)
* [Lunch and learn - Youtube playlist](https://www.youtube.com/playlist?list=PL8l7YtFPKywYaDTg7yFDytHBX-BpH8cDM)
