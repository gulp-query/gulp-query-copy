## gulp-query-copy
Plugin for [gulp-query](https://github.com/gulp-query/gulp-query)

This plugin provides copy, rename and combine files.

```
npm install gulp-query gulp-query-copy
```

### Example
Paste the code into your `gulpfile.js` and configure it
```javascript
let build = require('gulp-query')
  , copy = require('gulp-query-copy')
;
build((query) => {
    query.plugins([copy])
      .copy(['src/css/table.css','src/css/alert.css'],"css/styles.scss")
      
      .copy('src/fonts/**/*',"fonts/",'fonts')
    
      .copy({
        from: 'src/images/**/*',
        to: "images/",
        name: 'images'
      })

    ;
});
```
And feel the freedom
```
gulp
gulp --production // For production (minification)
gulp copy // Only for copy
gulp copy:fonts
...
```

### Options
```javascript
.copy({
  from: 'src/images/**/*', // ['src/images/**/*', 'src/images2/**/*']
  to: "images/",
  name: 'task_name' // For gulp copy:task_name 
})
```