---
title: TS Summary
---

内部模块 - 命名空间

外部模块 - 模块

```jsx
// 一个模块中 如果要导出多个变量可以使用
export {add, min, ...function}
import {add, min} from 'filePath'

//如果该模块中只导出一个对象
export default Person
import Person from 'filePath'

// .js文件重命名为.ts 一些模块不能被识别，可以转换为ts的导入方式，或者声明
//js的写法
var foo = require("foo");
foo.doStuff();

//ts的语句
import foo = require("foo");
foo.doStuff();

//cmd规范导出模块
function foo() {
    // ...
}
module.exports = foo;
//使用ts的写法
function foo() {
    // ...
}
export = foo;
```

- `调用时 “!”` 的用法
    
    ```jsx
    declare var foo: string[] | null;
    foo.length;  // error - 'foo' is possibly 'null'
    foo!.length; // okay - 'foo!' just has type 'string[]'
    ```
    

- 用好枚举

```jsx

```