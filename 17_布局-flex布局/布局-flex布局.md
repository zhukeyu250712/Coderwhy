# CSS Flex布局

## 一、认识flex布局

### 1、认识flexbox

* Flexbox翻译为弹性盒子:
	* **弹性盒子**是一种用于按行或按列布局元素的一维布局方法 ;
	* 元素可以膨胀以填充额外的空间, 收缩以适应更小的空间;
	* 通常我们使用Flexbox来进行布局的方案称之为flex布局(flex layout);

* flex布局是目前web开发中使用最多的布局方案：
	* flex 布局（Flexible 布局，弹性布局）;
	* 目前特别在移动端可以说已经完全普及;
	* 在PC端也几乎已经完全普及和使用, 只有非常少数的网站依然在用浮动来布局;

* 为什么需要flex布局呢?
	* 长久以来，CSS 布局中唯一可靠且跨浏览器兼容的布局工具只有 floats 和 positioning。
	* 但是这两种方法本身存在很大的局限性, 并且他们用于布局实在是无奈之举;

### 2、原先的布局存在的痛点

* 原来的布局存在哪些痛点呢? 举例说明: 
	* 比如在父内容里面垂直居中一个块内容。
	* 比如使容器的所有子项等分可用宽度/高度，而不管有多少宽度/高度可用。
	* 比如使多列布局中的所有列采用相同的高度，即使它们包含的内容量不同。

### 3、flex布局的出现

* 所以长久以来, 大家非常期待一种真正可以用于对元素布局的方案:于是flex布局出现了;

* flexbox在使用时, 我们最担心的是它的兼容性问题:
	* 我们可以在caniuse上查询到具体的兼容性

![image-20230829201835754](../../../Coderwhy/pic/image-20230829201835754.png)



## 二、flex布局的理解

### 1、flex布局的重要概念

* 两个重要的概念：
	* 开启了 flex 布局的元素叫 flex container
	* flex container 里面的直接子元素叫做 flex item

* 当flex container中的子元素变成了flex item时, 具备一下特点:
	* flex item的布局将受flex container属性的设置来进行控制和布局;
	* flex item不再严格区分块级元素和行内级元素;
	* flex item默认情况下是包裹内容的, 但是可以设置宽度和高度;

* 设置 display 属性为 flex 或者 inline-flex 可以成为 flex container
	* flex： flex container 以 block-level 形式存在
	* inline-flex： flex container 以 inline-level 形式存在

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      /* 
      flex:块级盒子的 flex-container 
      inline-flex : 了解，行内级盒子的flex-container 
      */
      display: flex;
      /* display: inline-flex; */
      background-color: #f00;
    }
  </style>
</head>
<body>

  aaa
  <div class="box">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>
  bbb

</body>
</html>
```

![image-20230829214259545](../../../Coderwhy/pic/image-20230829214259545.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      /* 
      flex:块级盒子的 flex-container 
      inline-flex : 了解，行内级盒子的flex-container 
      */
      display: flex;
      /* display: inline-flex; */
      background-color: #f00;

      flex-wrap: wrap;

      width: 200px;
      height: 200px;
      
    }

    .item {
      width: 60px;
      height: 60px;
      background-color: orange;
    }

  </style>
</head>
<body>

  <!-- aaa -->
  <div class="box">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
    <div class="item">7</div>
    <div class="item">8</div>
    <div class="item">9</div>
  </div>
  <!-- bbb -->

</body>
</html>
```

![image-20230829214329111](../../../Coderwhy/pic/image-20230829214329111.png)

### 2、flex布局的模型

![image-20230829202046188](../../../Coderwhy/pic/image-20230829202046188.png)



## 三、flex-container属性

### 1、flex相关的属性

![image-20230829214020291](../../../Coderwhy/pic/image-20230829214020291.png)

### 2、flex-direction

* flex items 默认都是沿着 main axis（主轴）从 main start 开始往 main end 方向排布
	* flex-direction 决定了 main axis 的方向，有 4 个取值
	* row（默认值）、row-reverse、column、column-reverse

![image-20230829214117135](../../../Coderwhy/pic/image-20230829214117135.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;

      display: flex;

      /* 
      修改主轴的方向 
      row-reverse: row的反转
      column: 列变成主轴的方向
      column-reverse: 列主轴进行反转
      */
      /* flex-direction: row-reverse; */
      /* flex-direction: column; */
      flex-direction: column-reverse;

    }

    .item {
      width: 120px;
      height: 120px;

      background-color: #f00;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
    <div class="item item4">4</div>
    <div class="item item5">5</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230829214721193](../../../Coderwhy/pic/image-20230829214721193.png)

### 3、flex-wrap

* flex-wrap 决定了 flex container 是单行还是多行
	* nowrap（默认）：单行
	* wrap：多行
	* wrap-reverse：多行（对比 wrap，cross start 与 cross end 相反）

![image-20230829214825493](../../../Coderwhy/pic/image-20230829214825493.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;

      display: flex;

      /* nowrap:默认值不换行 */
      /* flex-wrap: nowrap; */
      flex-wrap: wrap;
      /* flex-wrap: wrap-reverse; */
    }

    .item {
      width: 120px;
      height: 120px;

      background-color: #f00;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
    <div class="item item4">4</div>
    <div class="item item5">5</div>
    <div class="item item6">6</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230829220221638](../../../Coderwhy/pic/image-20230829220221638.png)

### 4、flex-flow

* flex-flow 属性是 flex-direction 和 flex-wrap 的简写。
	* 顺序任何, 并且都可以省略;

![image-20230829220612243](../../../Coderwhy/pic/image-20230829220612243.png)

### 5、justify-content

**justify-content 决定了 flex items 在 main axis 上的对齐方式**

* flex-start（默认值）：与 main start 对齐
* flex-end：与 main end 对齐
* center：居中对齐
* space-between：
	* flex items 之间的距离相等
	* 与 main start、main end两端对齐
* space-around：
	* flex items 之间的距离相等
	* flex items 与 main start、main end 之间的距离是 flex items 之间距离的一半
* space-evenly：
	* flex items 之间的距离相等
	* flex items 与 main start、main end 之间的距离 等于 flex items 之间的距离

![image-20230830131647544](../../../Coderwhy/pic/image-20230830131647544.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      /* padding: 0 10px; */
      box-sizing: border-box;
      
      display: flex;

      /* 切换justify-content */
      /* flex-end：让元素和main end对齐 */
      /* center：居中对齐 */

      /* justify-content: flex-end; */
      /* justify-content: flex-start; */
      /* justify-content: center; */

      /* space-between : 
        flex item 之间的距离相等；
        与main start和main end两端对齐
        两端各放一个元素，其他多余的元素一定要空间等分
      */
      /* justify-content: space-between; */

      /* space-around：两端也有间距，两端的间距是items之间的间距的一半*/
      /* justify-content: space-around; */

      /* space-evenly:两端也有空隙，并且所有的空间都进行等分 */
      justify-content: space-evenly;

    }

    .item {
      width: 120px;
      height: 120px;
      background-color: #f00;
      /* margin-left: 20px; */
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
    <div class="item item3">3</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830131735171](../../../Coderwhy/pic/image-20230830131735171.png)

### 6、align-item

**align-items 决定了 flex items 在 cross axis 上的对齐方式**

* normal：在弹性布局中，效果和stretch一样
* stretch：当 flex items 在 cross axis 方向的 size 为 auto 时，会

自动拉伸至填充 flex container

* flex-start：与 cross start 对齐
* flex-end：与 cross end 对齐
* center：居中对齐
* baseline：与基准线对齐

![image-20230830134556976](../../../Coderwhy/pic/image-20230830134556976.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      /* padding: 0 10px; */
      box-sizing: border-box;
      
      display: flex;

      /* align-items: center; */
      /* align-items: flex-start; */
      /* align-items: flex-end; */
      /* align-items: baseline; */

      /* 
      当flex item在cross axis方向的size为auto时，会自动拉伸至填充 flex container
      */
      align-items: stretch;
      /* align-items: normal; */
    }

    .item {
      width: 120px;
      /* height: auto; */
      /* height: 120px; */
    }

    .item1 {
      height: 80px;
      font-size: 30px;
    }

    .item2 {
      height: 150px;
      font-size: 40px;
    }

    .item3 {
      height: 60px;
      font-size: 12px;
    }

  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1x</div>
    <div class="item item2">2x</div>
    <div class="item item3">3x</div>
    <div class="item item4">4x</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830134636193](../../../Coderwhy/pic/image-20230830134636193.png)

### 7、align-content

**align-content 决定了多行 flex items 在 cross axis 上的对齐方式，用法与 justify-content 类似**

* stretch（默认值）：与 align-items 的 stretch 类似
* flex-start：与 cross start 对齐
* flex-end：与 cross end 对齐
* center：居中对齐
* space-between：
	* flex items 之间的距离相等
	* 与 cross start、cross end两端对齐
* space-around：
	* flex items 之间的距离相等
	* flex items 与 cross start、cross end 之间的距离是 flex items 之间距离的一半
* space-evenly：
	* flex items 之间的距离相等
	* flex items 与 cross start、cross end 之间的距离 等于 flex items 之间的距离

![image-20230830134930529](../../../Coderwhy/pic/image-20230830134930529.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
      flex-wrap: wrap;

      justify-content: space-between;
      /* align-content: flex-start; */
      /* align-content: center; */
    }

    .item {
      width: 120px;
      /* height: auto; */
      height: 120px;
      /* margin-bottom: 10px; */
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1x</div>
    <div class="item item2">2x</div>
    <div class="item item3">3x</div>
    <div class="item item4">4x</div>
    <div class="item item1">1x</div>
    <div class="item item2">2x</div>
    <div class="item item3">3x</div>
    <div class="item item4">4x</div>
    <div class="item item4">4x</div>
    <div class="item item4">4x</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830140137669](../../../Coderwhy/pic/image-20230830140137669.png)



## 四、flex-item属性

### 1、order

**order 决定了 flex items 的排布顺序**

* 可以设置任意整数（正整数、负整数、0），值越小就越排在前面
* 默认值是 0

![image-20230830152203179](../../../Coderwhy/pic/image-20230830152203179.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
    }

    .item {
      width: 120px;
      height: 120px;
    }

    .item1 {
      order: 5;
    }
    .item2 {
      order: 9;
    }
    .item3 {
      order: 3;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830152244833](../../../Coderwhy/pic/image-20230830152244833.png)

### 2、align-self 

**flex items 可以通过 align-self 覆盖 flex container 设置的 align-items**

* auto（默认值）：遵从 flex container 的 align-items 设置
* stretch、flex-start、flex-end、center、baseline，效果跟 align-items 一致

![image-20230830152336360](../../../Coderwhy/pic/image-20230830152336360.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
      align-items: center;
    }

    .item {
      width: 120px;
      height: 120px;
    }

    .item1 {
      order: 5;
      height: 90px;

      align-self: flex-start;
    }
    .item2 {
      order: 3;
      height: 150px;
    }
    .item3 {
      order: 9;
      height: 120px;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830175323449](../../../Coderwhy/pic/image-20230830175323449.png)

### 3、flex-grow

* flex-grow 决定了 flex items 如何扩展(拉伸/成长)
	* 可以设置任意非负数字（正小数、正整数、0），默认值是 0
	* 当 flex container 在 main axis 方向上有剩余 size 时，flex-grow 属性才会有效
* 如果所有 flex items 的 flex-grow 总和 sum 超过 1，每个 flex item 扩展的 size 为
	* flex container 的剩余 size  *  flex-grow  /  sum

![image-20230830175412837](../../../Coderwhy/pic/image-20230830175412837.png)

* flex items 扩展后的最终 size 不能超过 max-width \ max-height

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
    }

    .item {
      width: 120px;
      height: 120px;

      flex-grow: 1;
    }

    .item1 {
      flex-grow: 2;
      /* max-width: 150px; */
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830180735874](../../../Coderwhy/pic/image-20230830180735874.png)

### 4、flex-shrink

* flex-shrink 决定了 flex items 如何收缩(缩小)
	* 可以设置任意非负数字（正小数、正整数、0），默认值是 1
	* 当 flex items 在 main axis 方向上超过了 flex container 的 size，flex-shrink 属性才会有效

* 如果所有 flex items 的 flex-shrink 总和超过 1，每个 flex item 收缩的 size为
	* flex items 超出 flex container 的 size * 收缩比例 / 所有 flex items 的收缩比例之和

* flex items 收缩后的最终 size 不能小于 min-width \ min-height

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
    }

    .item {
      width: 120px;
      height: 120px;

      flex-shrink: 0;
    }

    .item1, .item2 {
      flex-shrink: 1;
      min-width: 50px;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item3">4</div>
    <div class="item item4">5</div>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830183138682](../../../Coderwhy/pic/image-20230830183138682.png)

### 5、flex-basis

* flex-basis 用来设置 flex items 在 main axis 方向上的 base size
	* auto（默认值）、具体的宽度数值（100px）

* 决定 flex items 最终 base size 的因素，从优先级高到低
	* max-width \ max-height \ min-width \ min-height
	* flex-basis
	* width \ height
	* 内容本身的 size

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
    }

    .item {
      width: 120px;

      /* 基础尺寸 */
      flex-basis: 120px;
      height: 120px;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">
      2 ajnifajfjZjiassjfakjfnakjfankfjka
    </div>
    <div class="item item3">3</div> 
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830184320378](../../../Coderwhy/pic/image-20230830184320378.png)

### 6、flex属性

* flex 是 flex-grow || flex-shrink || flex-basis 的简写,flex 属性可以指定1个，2个或3个值。

![image-20230830212601186](../../../Coderwhy/pic/image-20230830212601186.png)

* 单值语法: 值必须为以下其中之一:
	* 一个无单位数(<number>): 它会被当作<flex-grow>的值
	* 一个有效的宽度(width)值: 它会被当作 <flex-basis>的值
	* 关键字none，auto或 initial.

* 双值语法: 第一个值必须为一个无单位数，并且它会被当作 <flex-grow> 的值。
	* 第二个值必须为以下之一：
		* 一个无单位数：它会被当作 <flex-shrink> 的值。
		* 一个有效的宽度值: 它会被当作 <flex-basis> 的值。

* 三值语法:
	* 第一个值必须为一个无单位数，并且它会被当作 <flex-grow> 的值。
	* 第二个值必须为一个无单位数，并且它会被当作 <flex-shrink> 的值。
	* 第三个值必须为一个有效的宽度值， 并且它会被当作 <flex-basis> 的值。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      height: 500px;
      background-color: orange;
      
      display: flex;
    }

    .item {
      width: 120px;
      height: 120px;

      /* flex-grow  flex-shrink flex-basis */
      /* none: 0 0 auto */
      /* auto: 1 1 auto */
      /* flex: auto; */

      flex: 1 1 10px;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">
      2 ajnifajfjZjiassjf
    </div>
    <div class="item item3">3</div> 
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830213453832](../../../Coderwhy/pic/image-20230830213453832.png)

### 7、思考: 如下布局如何解决对齐问题

![image-20230830213547599](../../../Coderwhy/pic/image-20230830213547599.png)

#### 方案1：计算每个部分

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      background-color: orange;
      
      display: flex;
     
      flex-wrap: wrap;
    }

    .item {
      width: 110px;
      height: 110px;

      margin-right: 20px;
    }

    .item:nth-child(4n) {
      margin-right: 0;
    }
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830214432069](../../../Coderwhy/pic/image-20230830214432069.png)

#### 方案2：加的 span / i / strong / div 数目为 item列数减2

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      width: 500px;
      background-color: orange;
      
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
    }

    .item {
      width: 110px;
      height: 110px;

      /* margin-right: 20px; */
    }

    .container > span {
      width: 110px;
      /* height: 10px;

      background-color: red; */
    }

    /* .item:nth-child(4n) {
      margin-right: 0;
    } */
  </style>
</head>
<body>
  
  <div class="container">
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <div class="item item1">1</div>
    <div class="item item2">2</div>
    <div class="item item3">3</div> 
    <!-- 加的 span/i/strong/div 数目为 item列数减2  -->
    <span></span>
    <span></span>
  </div>

  <script src="./js/itemRandomColor.js"></script>

</body>
</html>
```

![image-20230830215416292](../../../Coderwhy/pic/image-20230830215416292.png)

#### 方案3：grid布局