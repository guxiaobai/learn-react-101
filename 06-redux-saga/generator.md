## Generator

* next方法可以带一个参数，该参数就会被当作上一个yield表达式的返回值

```
function run(generator){
  var myGen = generator();


  function handle(yielded){
    if(!yielded.done) {
      yielded.value.then(function(data){
        return handle(myGen.next(data))
      })
    }
  }

 return  handle(myGen.next())
}

function* gen(){
  var posts = yield $.getJSON('https://');
  var users = yield $.getJSON('https://');
}

run(gen);
```


### 参考资料

* [co](https://github.com/tj/co)
* [Generator 函数的语法](http://es6.ruanyifeng.com/#docs/generator)
* [Generator 函数的异步应用](http://es6.ruanyifeng.com/#docs/generator-async)
