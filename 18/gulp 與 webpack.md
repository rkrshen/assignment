Gulp 環境安裝
1. 安裝node.js
https://nodejs.org/en/
https://nodejs.org/zh-tw/

如果是gulp3 請安裝node 8.11的版本
如果是gulp4 請安裝node lts的版本

2. 專案資料夾建立
建立 MyProject

安裝gulp
全域 global 安裝

npm install gulp-cli -g
mac =>sudo
window 用管理者權限安裝
確認版本指令


node -v //node 版本
 npm -v // npm 版本
 gulp -v // gulp 版本
 gulp --tasks //查詢目前結構


4. gulp 開發檔案設置 設置

{
  "name": "ed101gulp", //專案名稱
  "version": "1.0.0", //專案版本
  "description": "", // 專案描述
  "main": "gulpfile.js",// 加載文件require('moduleName');
  "dependencies": {},// 該項目使用哪些模組
  "devDependencies": {}, // 該項目使用哪些模組
  // 執行指令
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/sexfat/ed101gulp.git"
  },
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/sexfat/ed101gulp/issues"
  },
  "homepage": "https://github.com/sexfat/ed101gulp#readme"
}


gulp.task	執行工作
gulp.src	執行資料來源
gulp.dest	執行結果位置
gulp.watch	監視執行過程中，資料是否變更


gulp console.log
gulp.task('hello', function () {
  //do
  console.log('hello world 你好');
});

gulp.task('move', function () {
  //do
  return gulp.src('*.html') //來源
    .pipe(gulp.dest('dest/')) //目的地
})






壓縮Css

npm install gulp-clean-css --save-dev


const cleanCSS = require('gulp-clean-css');


gulp.task('minify_css', function () {
  //do
  return gulp.src('css/*.css') //來源
    .pipe(cleanCSS({
      compatibility: 'ie8'
    }))
    .pipe(gulp.dest('dest/css')) //目的地
})

合併Css檔案
npm install --save-dev gulp-concat


const concat = require('gulp-concat');


gulp.task('concat', ['sass'], function () {
  //do
  return gulp.src('css/*.css') //來源
    .pipe(concat('all.css')) //合併
    .pipe(cleanCSS({
      compatibility: 'ie8'
    })) //壓縮
    .pipe(gulp.dest('dest/css')) //目的地
})


Sass

sudo npm install --unsafe-perm node-sass gulp-sass --save-dev


const sass = require('gulp-sass');


gulp.task('sass', function () {
  return gulp.src('./sass/*.scss') //來源
    .pipe(sass().on('error', sass.logError)) //sass轉譯
    .pipe(gulp.dest('./dest/css')); //目的地
});



SourceMap 讓 css 文件可以追朔 sass

npm i gulp-sourcemaps  --save-dev


var sourcemaps = require('gulp-sourcemaps');


gulp.task('sass', function () {
    return gulp.src('./dev/sass/*.scss') //來源
        .pipe(sourcemaps.init())
        .pipe(sass().on('error', sass.logError)) //轉譯sass
        .pipe(cleanCSS({
            compatibility: 'ie8'
        })) // 壓縮css
        .pipe(sourcemaps.write())
        .pipe(gulp.dest('./dist/css')); //目的地
});

HTML 合併

npm install --save-dev gulp-file-include


const fileinclude = require('gulp-file-include');


gulp.task('fileinclude', function () {
  return gulp.src(['*.html']) //來源
    .pipe(fileinclude({
      prefix: '@@',
      basepath: '@file'
    }))
    .pipe(gulp.dest('./dest')); //目的地
});