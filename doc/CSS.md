### 2. CSS

#### 2.1. Bonnes pratiques

##### 2.1.1. Nomenclature

1. Utiliser des classes uniquement pas des ID pour associer un style.
Les id # sont uniques par conséquents ne sont pas réutilisables. Elles servent d'ancres dans la page ou pour associer des interactions javascript.

2. Séparation du style et de la DOM (separation of concern).
La classe ne nomme pas le style elle nomme l'objet au quel on va appliquer un style.

Mauvaise pratique
HTML:
```
<a href="#alert" class="red">Atttention ...</a>
```
CSS :
```
.red {
	color: #00F;
}
```

Bonne pratique

HTML:
```
<a href="#alert" class="lien-important" >Atttention ...</a>
```
CSS :
```
.lien-important {
	color: #00F;
}
```

####### CSS Orientté objet

*OOCSS (Object Oriented CSS)*
http://oocss.org

- noms de classes courts
- classes réutilisables
- contextualisation
- Modules et templates élémentaires
- Grille fluide

Exemple ("media" module)

HTML: 
```
<div class="media attribution">

  <a href="http://twitter.com/stubbornella" class="img">
    <img src="http://stubbornella.com/profile_image.jpg" alt="me" />
  </a>

  <div class="bd">
    @Stubbornella 14 minutes ago
  </div>

</div>
```

CSS: 
```
/* ====== media ====== */
.media {margin:10px;}
.media, .bd {overflow:hidden; _overflow:visible; zoom:1;}
.media .img {float:left; margin-right: 10px;}
.media .img img{display:block;}
.media .imgExt{float:right; margin-left: 10px;}
```

Inconvénients:
- Classes gigognes (imbriquées) rend analyse du CSS plus lent.
- Maintenance difficile
	- Conflits possibles
	- Surcharge souvent nécessaire

###### BEM = Block, Element, Modifier
http://bem.info/
http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/

- Nomenclature orienté objet 
- Tire profit des préprocesseurs CSS
- Rend compte des héritages
- Facilite la maintenance et l'évolution du site

```
.block {}
.block__element {}
.block--modifier {}
```

Exemple

CSS: 
```
.media {}
.media__img {}
.media__img--rev {}
.media__body {}
```

HTML: 
```
<div class="media">
    <img src="logo.png" alt="Foo Corp logo" class="media__img--rev">
    <div class="media__body">
        <h3 class="alpha">Welcome to Foo Corp</h3>
        <p class="lede">Foo Corp is the best, seriously!</p>
    </div>
</div>
```

*CSS Lint* http://csslint.net
Util pour vérifier en permance que les bonne pratiques sont bien suivies et que le code est lisible.

##### 2.1.2. Architecture
- Rénitialiser les style des éléments HTML (css reset)
- Identifier des modules: blocs de contenu au style et aux fonctionnalités similiaires entre les pages ou dasn une même page
- Intégrer un guide stylistique (Style Guide)
- Séparer les variables dans un même plusieurs fichiers (ex: vars.scss, colors.scss, fonts.scss, breakpoints.scss)
- Une feuille de style pa module
- Une feuille de style par page
- Les espacements verticaux (vertical rythme) devrais toujours être exprimés en <b>em</b> ou <b>rem</b> car relatifs à la taille du texte.</li>
- Les espacements horizontaux devrais toujours être exprimés en % pour des containers et en <b>em</b> ou <b>rem</b> pour du texte.</li>

[KSS](http://warpspire.com/kss/styleguides/)
Permet de générer un style d'après la documentation du code
```
/*
A button suitable for giving stars to someone.

:hover             - Subtle hover highlight.
.stars-given       - A highlight indicating you've already given a star.
.stars-given:hover - Subtle hover highlight on top of stars-given styling.
.disabled          - Dims the button to indicate it cannot be used.

Styleguide 2.1.3.
*/
a.button.star{
  ...
}
a.button.star.stars-given{
  ...
}
a.button.star.disabled{
  ...
}
```

![style-guide-medium](./app/images/slides/styleguide_medium.png)
![style-guide-2](./app/images/slides/styleguide-2.png)

#### 2.2. CSS Tools and library

##### 2.2.1. Sass : Préprocesseur CSS
Sass: Syntactically Awesome Style Sheets
http://sass-lang.com/

![sass logo](../app/images/slides/logo-sass.svg)

##### 2.2.2. Librairies


##### 2.2.3. Fameworks CSS

* [Compass](http://compass-style.org/) -Ruby gem, +sprite generator, -lent
* [Bourbon.io](http://bourbon.io/) 
* [Inuit CSS](https://github.com/inuitcss) http://terabytenz.github.io/inuit.css-kitchensink/
* [Zurb Foundation](http://foundation.zurb.com/)
* [Bootstrap](http://getbootstrap.com/)

![compass logo](../app/images/slides/compass.png)
![bourbon logo](../app/images/slides/bourbon-logo.png)
![sass logo](../app/images/slides/inuit-css.png)
![zurb](../app/images/slides/frameworks-zurb-foundation-180x180.png)
![bootstrap logo](../app/images/slides/bootstrap2_logo.png)



#### 2.3. CSS avancés
##### Pseudo selecteurs
##### Formes géométriques
##### Animation
##### Media Queries

##### Flex-box
http://css-tricks.com/snippets/css/a-guide-to-flexbox/

##### transform
http://thewebrocks.com/demos/3D-css-tester/
http://desandro.github.io/3dtransforms/

#### 2.4. Ressources
[SMACSS](http://smacss.com)
[CSS-Tricks](css-tricks.com)
[Can I Use](http://caniuse.com/)
http://thewebrocks.com/demos/3D-css-tester/
