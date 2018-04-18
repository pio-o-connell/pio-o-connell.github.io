
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
  ```
    npm install -g browser-sync
  ```

  + References
    +  [Brad Traversy Gulp Crash Course](https://www.youtube.com/watch?v=1rw9MfIleEg " Brad Traversy")

    + [Install SASS using Gulp engine](https://www.youtube.com/watch?v=rmXVmfx3rNo "Brad Traversy")


````javascript
    const gulp = require('gulp.js');
    const browserSync = require('browser-sync').create();
    const imageMin=require('gulp-imagemin');
    const uglify=require('gulp-uglify');
    const sass=require('gulp-sass');
    const concat=requrie('gulp-concat')
    // Logs message
    gulp.task('message' ,function(){
      return console.log('Gulp is running...');
    });
````
    // to invoke  from console gulp message
    // gulp.task define tasks
    //gulp.src points to files to use
    //gulp.dest point to folder to outpuf
    //gulp.watch watch files and folders for changes

    ///Compile SASS
    gulp.task('sass', function(){
      return gulp.src(['src/scss/*.scss'])
        .pipe(sass())
        .pipe(gulp.dest('src/css'))
        .pipe(browserSync.stream());
    });
    
    //Watch & Server
    gulp.task('serve',['sass'],function(){
      browserSync.init({
        server: './src'
      });
      gulp.watch(['src/scss/*.scss'],['sass']);
      gulp.watch(['src/scss/*.html']).on('change',browserSync.reload)
    });
    // to invoke  from console gulp
    gulp.task('default', function(){
      gulp.task('copyHTML', function(){
       gulp.src('src/*.html')
      .pipe(gulp.dest('dest'))

    });



    //minify images
    gulp.task('imageMin', () =>    // change to Imagemin
    	gulp.src('src/images/*')
    		.pipe(imagemin())
    		.pipe(gulp.dest('dist/images'))
    );

    //minify javasctipy using uglify
    gulp.task('Minify', function(){
       gulp.src(['src/js/*.js'])
        .pipe(uglify())
        .pipe(gulp.dest('dist/js'))
        .pipe(browserSync.stream());
    });


    // Compile sass
    gulp.task('sass', function(){
       gulp.src('src/sass/*.scss')
        .pipe(sass().)on('error',sass.logerror))
        .pipe(gulp.dest('dist/css'));
    });

    // concatenate files to Main.js
    gulp.task('scripts', function(){
       gulp.src('src/js/*.js')
        .pipe(concat('main.js')))
        ..pipe(uglify());   // remove minify from default
        .pipe(gulp.dest('dist/js'));
    });

    /

     // gulp.task('minify;') type gulp
    // Defult task   -- can put ,minify here
    // remoed minified sctipy beause want to minify concatted files
    gulp.task('default', ['serve','message','copyHTML','imageMin','sass','scripts']);

    ///

































3. Install ruby and ruby gems
