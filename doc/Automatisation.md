### Automatisation des opérations

#### Install node and npm

NodeJs by Joyent

npm: **N**ode **P**ackage **M**anager

https://gist.github.com/isaacs/579814

```
npm init
npm search
npm list (-g)
npm install (-g) (--save) (--save-dev)
npm uninstall (-g) (--save) (--save-dev)
npm prune (--production)
```

```npm install momentjs --save```

#### Bower
[[../app/images/slides/bower-logo.png | height = 100px ]]

#### Grunt
http://gruntjs.com/

![grunt logo](../app/images/slides/grunt.png =100x50)
{:.grunt-logo height="100px"}

Voudez installer grunt et grunt-cli globalement sur votre environnement
```
npm install -g grunt
npm install -g grunt-cli
```

Gruntfile.js
```
module.exports = function(grunt) {

  // Project configuration.
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    uglify: {
      options: {
        banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n'
      },
      build: {
        src: 'src/<%= pkg.name %>.js',
        dest: 'build/<%= pkg.name %>.min.js'
      }
    }
  });

  // Load the plugin that provides the "uglify" task.
  grunt.loadNpmTasks('grunt-contrib-uglify');

  // Default task(s).
  grunt.registerTask('default', ['uglify']);

};
```

Voici une liste de tâches grunt les plus courament utilisées

- load-grunt-tasks
- grunt-autoprefixer
- grunt-concurrent
- grunt-contrib-clean
- grunt-contrib-concat
- grunt-contrib-connect
- grunt-contrib-copy
- grunt-contrib-cssmin
- grunt-contrib-htmlmin
- grunt-contrib-imagemin
- grunt-contrib-jshint
- grunt-contrib-uglify
- grunt-contrib-watch
- grunt-mocha
- grunt-modernizr
- grunt-newer
- grunt-rev
- grunt-sass
- grunt-svgmin
- grunt-usemin
- grunt-wiredep
- jshint-stylish
- time-grunt

#### Gulp
#### Exemples (grunt)
#### [Yeoman](http://yeoman.io/)