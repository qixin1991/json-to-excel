# json-to-excel

fork from [rikkertkoppes/json2xls](https://github.com/rikkertkoppes/json2xls)

# Different

- cols add width property
- delete express middleware cause i use [koajs](http://koajs.com)

# Usage

Download the json data as excel file.

```
    var router = require('koa-router')();
    router.get('/download', function* (){
        var xls = json2xls(results);
        this.type = 'application/vnd.openxmlformats';
        this.set('Content-Type', 'application/vnd.openxmlformats');
        this.set("Content-Disposition", "attachment; filename= download-json-to-excel.xlsx");
        var buffer = new Buffer(xls,'binary');
        this.body = buffer;
    });
```