
# Setup for personal website
1. Install node.js
2. Install Gulp engine
    What is Gulp JS?
      + Built on node.js and npm
      + Built on node streams( continuous flow of data ) that can be manipulated  asynchronously.
      + Facilitates manipulation of files operations through pipelining chain of processing elements output of one to input can setup plug-ins to accomplish tasks hundreds of plug-ins
      + Common tasks plugins (time consuming repetitive)-
        + Minification of styles and scripts
                      (condense white space,comments)
        + Concatenation(many files to one big file)
        + Cache Busing
        + Testing, linting and optimization
        + Development  servers( web server plug-in to run on development server)

## To install Gulp        
+  [Brad Traversy Gulp Crash Course]""(https://github.com/bradtraversy/sass_starter_pack " Brad Traversy")

  ```
        npm install -g gulp
        mkdir exampleapp
        cd exampleapp
        atom ..
        nmp init (creates json file)
        install gulp locally - npm install --save-dev gulp
            #  ( stored in json file as "devDependencies")
  ```

## To create working directory-- all /src/scss and /src/js and files will be copied from /dest/css and /dest/js
      create new folder /src
      create new file gulpFile.js
      create new files to copy html    from /src to dest
      create new file src/ index.html      ! using emmet
      create second src/about.html

## To automate common manual tasks
  1. CopyHTML

   -will be using gulp.src() and gulp.dest() using gulp commands
  2. Minify to optimise image
        ```
        npm install -save
        npm install --save-dev gulp-imagemin
        const gulp = require('gulp');
        const imagemin = require('gulp-imagemin');
        ```
  3. Minify js // reduced whitespace

  4. use Uglify // javascript parser
        ```
        npm install --save-dev gulp-uglify
        const uglify=require(gulp-uglify)
        gulp minify
        ```

  5. Gulp sass_starter_pack
      ```
      npm install --save-dev gulp-sass
      ```

  6. concatenate files // group files together
  ```
      npm install --save-dev gulp-concat
  ```
      
  7. browsersyn // instant updated on browser on save()


  + References
    +  [Brad Traversy Gulp Crash Course](https://www.youtube.com/watch?v=1rw9MfIleEg " Brad Traversy")

    + [Install SASS using Gulp engine](https://www.youtube.com/watch?v=rmXVmfx3rNo "Brad Traversy")


3. Install ruby and ruby gems
