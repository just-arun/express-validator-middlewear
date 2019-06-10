# express-validator-middlewear
this is an util for express validator
```js
app.use(expressValidator({
    errorFormatter: function (param, msg, value) {
        var namespace = param.split('.')
        , root = namespace.shift()
        , formParam = root;
        
        while(namespace.length){
            formParam += `[${namespace.shift()}]`;
        }
        return {
            param: formParam,
            msg  : msg,
            value: value
        }
    }
}));

```
