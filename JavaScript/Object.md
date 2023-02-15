# Object

## Object()

## Object 构造方法

## 静态方法

获取对象属性方法：

-   `Object.keys()`

### 属性描述符的相关方法

获取对象属性方法：

-   `Object.getOwnPropertyNames()` 包括不可枚举属性

获取属性描述符对象方法：

-   `Object.getOwnPropertyDescriptor()`

定义属性描述符对象方法：

-   `Object.defineProperty()`
-   `Object.defineProperties()`

### 控制对象属性状态的相关方法

-   `Object.preventExtensions()`
-   `Object.isExtensible()`
-   `Object.seal()`
-   `Object.isSealed()`
-   `Object.freeze()`
-   `Object.isFrozen()`

#### 局限性

无法规避继承属性和方法。

## 实例方法

-   `Object.prototype.hasOwnProperty()`
-   `Object.prototype.valueOf()`
-   `Object.prototype.toString()`
-   `Object.prototype.toLocaleString()`

判断对象实例属性是否可枚举的方法：

-   `Object.prototype.propertyIsEnumerable()`

```javascript
var obj = {};
obj.p = 123;

obj.propertyIsEnumerable('p');
```

如果一个属性的 enumerable 设置为 false，下面三个操作不会取到该属性:

-   for…in 循环
-   `Object.keys()`方法
-   `JSON.stringify()`方法

## 属性描述符对象

### 元属性

-   value
-   writable
-   enumerable
-   configurable

### 存取器

-   get
-   set

一旦定义了 get 或者 set 方法，则不能定义 value 属性，并且 writable 必须设置为`false`。

通过这种方式定义存取器，只会定义 configurable 和 enumerable 属性，并且是`true`，如果通过`Object.defineProperty()`和`Object.defineProperties()`方法定义存取器，则是默认值。

```javascript
var obj = {
    get p() {
        return 'getter';
    },
    set p(value) {
        console.log('setter: ' + value);
    }
};
```

### 默认值

这里的默认是指非对象属性模型定义属性方法的默认值。

```javascript
{
    value: undefined,
    writable: true,
    enumerable: true,
    configurable: true, // 控制属性描述对象的可写性（除value的值）
    get: undefined,
    set: undefined
}
```

属性描述符对象为空时的默认值。

```javascript
var obj = {};
Object.defineProperty(obj, 'foo', {});
// {
//   value: undefined,
//   writable: false,
//   enumerable: false,
//   configurable: false
// }
```

## 拷贝

通过 for...in 结合`Object.prototype.hasOwnProperty()`方法过滤继承属性，如果有设置存取器，则还需要`Object.defineProperty()`方法拷贝属性。
