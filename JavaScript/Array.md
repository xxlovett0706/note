# Array

## Array() 和 Array 构造方法

两者相同，并不推荐使用。

```javascript
var arr = new Array();
```

**推荐使用数组字面量。**

```javascript
var arr = [1, 2, 3];
```

## 静态方法

-   `Array.isArray()`

## 实力方法

-   `Array.prototype.valueOf()`
-   `Array.prototype.toString()`

### 修改当前数组方法

#### 栈方法

-   `Array.prototype.push()`
-   `Array.prototype.pop()`

#### 队列方法

-   `Array.prototype.shift()`
-   `Array.prototype.unshift()`

#### 替换方法

-   `Array.prototype.splice()`

#### 排序方法

-   `Array.prototype.sort()`

#### 反转方法

-   `Array.prototype.reverse()`

#### 遍历方法

-   `Array.prototype.forEach()`

### 返回字符串方法

-   `Array.prototype.join()`

### 返回新数组方法

#### 提取方法

-   `Array.prototype.slice()`

#### 合并方法

-   `Array.prototype.concat()`

#### 遍历方法

-   `Array.prototype.map()`

#### 过滤方法

-   `Array.prototype.filter()`

### 断言方法

-   `Array.prototype.some()`
-   `Array.prototype.every()`

### 累计方法

-   `Array.prototype.reduce()`
-   `Array.prototype.reduceRight()`

### 获取元素首次出现位置方法

-   `Array.prototype.indexOf()`
-   `Array.prototype.lastIndexOf()`
