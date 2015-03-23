#gulp 文档
### gulp使用
    第一步：安装全局gulp
    
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

  
