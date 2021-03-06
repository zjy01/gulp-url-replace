## gulp-url-replace
> gulp构建中用来替换 js，css，img等资源的路径，通常用于从开发文件夹搬运到生产文件夹

### 博客
[gulp尝试开发](http://blog.zjy.space/2016/03/10/gulp%E5%B0%9D%E8%AF%95%E5%BC%80%E5%8F%91/)

### 安装
```shell
npm install gulp-url-replace --save-dev
```

### 使用
```js
var gulp = require('gulp');
var replace = require('gulp-url-replace')
gulp.task('move', function(){
    gulp.src('./*.html')
    .pipe(replace({
                      'lib/': '<%= stHost %>/node/public/lib/',
                      'img/':'<%= stHost %>/node/public/img/',
                      'css/': '<%= stHost %>/node/public/css/',
                      'js/': '<%= stHost %>/node/public/js/',
                  }))
    .pipe(gulp.dest("../production/views/"))
})
```

### API
gulp-url-replace can be called with a object  
<pre>replace({ "oldPath":"newPath"[,"oldPath2":"newPath2",...]})</re>

#### oldPath
type: String  
The string to search for

#### newPath
type: String  
The string to replace the search
