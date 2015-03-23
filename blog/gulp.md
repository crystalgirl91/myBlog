#gulp 文档
## gulp使用
###搭建gulp环境
1.npm安装全局gulp

    >> npm  install --global gulp
    
2.npm安装本地gulp

    >> npm install --save-dev gulp       /*--save-dev：将安装写入package.json配置文件*/
    或者：npm install gulp
    
3.创建gulpfile.js文件

    var gulp = require("gulp");
    var jshint = require("jshint");
    gulp.task("test",function(){
        return gulp.src("*/.js")
                .pipe(jshint())
                .pipe(gulp.dest("min.js"));
    });
    gulp.task("default",["test"])
    
4.执行gulpfile.js文件

    >> gulp
通过这四个步骤，gulp将会根据gulpfile.js中的任务，对整个项目进行流管理。gulp还有很多[插件]：href="https://github.com/gulpjs/gulp/tree/master/docs/recipes"，可以实现许多功能。比如：
     
### gulp.src(globs[, options])
找到globs匹配的文件，返回可以被piped使用的流

    gulp.src("client/templates/*.jade")
      .pipe(jade())
      .pipe(minify())
      .pipe(gulp.dest('build/minified_templates'))
    
####globs：数组或者字符串

文件名通配

####options：对象

####options.buffer：

类型：布尔值，默认值：true

如果设置它的值为false,则返回的内容则是流而不是缓存文件，当处理很大的文件的时候这个特性很有用。

####options.read

类型：布尔值，默认值：true

如果设置为false,则返回的内容为空并且不可读。

####options.base

类型：字符串，默认值：

  
