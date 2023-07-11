# HTML高级元素

## 一、列表元素

### 1、列表的实现方式

* 事实上现在很多的列表功能采用了不同的方案来实现:
	* 方案一: 使用div元素来实现(比如汽车之家, 知乎上的很多列表)
	* 方案二: 使用列表元素, 使用元素语义化的方式实现;

* 事实上现在很多的网站对于列表元素没有很强烈的偏好, 更加不拘一格,按照自己的风格来布局:
	* 原因是列表元素默认的CSS样式, 让它用起来不是非常方便
	* 比如列表元素往往有很多的限制, ul/ol中只能存放li, li再存放其他元素, 默认样式等;
	* 虽然我们可以通过重置来解决, 但是我们更喜欢自由的div;
* HTML提供了3组常用的用来展示列表的元素
	* 有序列表：ol、li
	* 无序列表：ul、li
	* 定义列表：dl、dt、dd

## 二、常见列表

### 1、有序列表 – ol – li

* ol（ordered list）
	* 有序列表，直接子元素只能是li，不能是其他div之类的
* li（list item）
	* 列表中的每一项

![image-20230707220124626](../../../Coderwhy/pic/image-20230707220124626.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* 自己设定样式，先把默认的样式去除 */
    ol, li {
      padding: 0;
      margin: 0;
      /* 把列表的点去了 */
      list-style: none; 
    }
  </style>
</head>
<body>
  <h1>自己喜欢的电影排名:</h1>
  <ol>
    <li>星际穿越</li>
    <li>大话西游</li>
    <li>盗梦空间</li>
    <li>喜羊羊和灰太狼</li>
    <li>熊出没</li>
  </ol>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</body>
</html>
```



### 2、无序列表 – ul - li

* ul（unordered list）
	* 无序列表，直接子元素只能是li

* li（list item）
	* 列表中的每一项

![image-20230707220233739](../../../Coderwhy/pic/image-20230707220233739.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    ul {
      /* 和ol最大区别 */
      /* list-style-type: decimal; */
      list-style-type: none;
      padding: 0;
      margin: 0;
    }
  </style>
</head>
<body>
  <h1>常见的编程语言:</h1>
  <ul>
    <li>
      <!-- 真实开发使用js遍历 -->
      <span>1.</span>
      JS
    </li>
    <li>Java</li>
    <li>C++</li>
    <li>Python</li>
  </ul>
</body>
</html>
```

### 3、定义列表 – dl – dt - dd

* dl（definition list）
	* 定义列表，直接子元素只能是dt、dd

* dt（definition term）
	* term是项的意思, 列表中每一项的项目名

* dd（definition description）
	* 列表中每一项的具体描述，是对 dt 的描述、解释、补充
	* 一个dt后面一般紧跟着1个或者多个dd

![image-20230707220956065](../../../Coderwhy/pic/image-20230707220956065.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    dl, dt, dd {
      padding: 0;
      margin: 0;
    }
    dt {
      font-size: 20px;
      font-weight: 700;
      margin: 10px 0;
    }

    dd {
      margin: 5px;
    }
  </style>
</head>
<body>
  <!-- 列出前端开发各个阶段 -->
  <h1>前端开发</h1>
  <dl>
    <dt>阶段一：</dt>
    <dd>HTML</dd>
    <dd>CSS</dd>
    <dd>JavaScript</dd>
    <dd>JavaScript DOM</dd>
    <dd>JavaScript BOM</dd>
    <dd>JavaScript高级语法</dd>

    <dt>阶段二：</dt>
    <dd>Node基础</dd>
    <dd>Webpack基础</dd>
    <dd>Git源代码管理</dd>
    <dd>Vue框架实战</dd>
    <dd>React框架实战</dd>
    <dd>小程序+云开发</dd>
    <dd>uniapp + taro</dd>

    <dt>阶段三：课程进阶 </dt>
    <dd>TypeScript</dd>
    <dd>Vue + TypeScript</dd>
    <dd>React + TypeScript</dd>
    <dd>Node/开发脚手架/Node服务器开发/MySQL</dd>
    <dd>Webpack高级/性能优化/Vite/Rollup/gulp</dd>
    <dd>数据结构和算法</dd>
  </dl>
</body>
</html>
```



### 4、案例练习

```
1. 先完成结构
2. 重置样式(body/a/ul)
3. 先整体, 后局部
	顺序: 按照从外往里. 从上往下
4. 去除重复的代码(css)
	将重复的逻辑放到一个单独的class中(.icon)
	不同的代码抽到不同的class(.new .hot)
```

找悬浮hover技巧

![image-20230707223542249](../../../Coderwhy/pic/image-20230707223542249.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="./css/reset.css">
  <!-- 
    1. 先完成结构
    2. 重置样式(body/a/ul)
    3. 先整体, 后局部
      * 顺序: 按照从外往里. 从上往下
    4. 去除重复的代码(css)
      * 将重复的逻辑放到一个单独的class中(.icon)
      * 不同的代码抽到不同的class(.new .hot)
   -->
  <style>
    ul > li {
      margin-top: 18px;
    }

    ul > li > a {
      display: inline-block;
    }

    /* a元素悬浮的时候颜色 */
    ul > li > a:hover {
      color: #f04142;
    }

    /* 局部 */
    /* 选择器一般不超过四个 */
    ul > li .ranking {
      display: inline-block;
      width: 24px;
      height: 24px;
      margin-right: 3px;
      text-align: center;
      line-height: 24px;

      font-weight: 700;
      color: #999;
    }

    /* 伪类: 结构伪类(后续会详细讲解) */
    ul > li:nth-child(1) .ranking {
      color: #f00;
    }
    
    ul > li:nth-child(2) .ranking {
      color: #0f0;
    }
    
    ul > li:nth-child(3) .ranking {
      color: #00f;
    }


    /* 内容相关 */
    ul > li .content {
      display: inline;
    }

    /* 图标相关的 */
    ul > li .icon {
      position: relative;
      top: 2px;
      left: 4px;

      /* i元素行内非替换元素 */
      display: inline-block;
      width: 16px;
      height: 16px;
      background-image: url(../images/new_icon.svg);
    }

    ul > li .new {
      background-image: url(../images/new_icon.svg);
    }

    ul > li .hot {
      background-image: url(../images/hot_icon.svg);
    }

  </style>
</head>
<body>
  
  <ul>
    <li class="item">
      <a href="#">
        <span class="ranking">1</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon"></i>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">2</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon new"></i>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">3</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">4</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon"></i>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">5</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon hot"></i>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">6</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">7</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon"></i>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">8</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon"></i>
      </a>
    </li>
    <li class="item">
      <a href="#">
        <span class="ranking">9</span>
        <div class="content">
          一花一世界明媚春天杜鹃花开满枝头色彩艳丽繁花似锦
        </div>
        <i class="icon hot"></i>
      </a>
    </li>
  </ul>

</body>
</html>
```

![image-20230707224828636](../../../Coderwhy/pic/image-20230707224828636.png)

### 5、继承属性和自己属性

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
      color: red !important;
    }

    /* 自己的为主要的 */
    /* 后代元素自己有设置属性，以后代元素为标准 */
    .container {
      color: #0f0;
    }
  </style>
</head>
<body>
  <div class="box">
    aaaa
    <div class="container">我是container的内容</div>
  </div>
</body>
</html>
```

![image-20230708191554053](../../../Coderwhy/pic/image-20230708191554053.png)



## 三、表格元素

### 1、表格常见的元素

* 编写表格最常见的是下面的元素:

* table
	* 表格

* tr(table row)
	* 表格中的行

* td(table data)
	* 行中的单元格

* 另外表格有很多相关的属性可以设置表格的样式, 但是已经不推荐使用了

![image-20230708192627033](../../../Coderwhy/pic/image-20230708192627033.png)



### 2、重要属性

* 这里我们需要用到一个非常重要的属性:
	* border-collapse CSS 属性是用来决定表格的边框是分开的还是合并的。
	* table { border-collapse: collapse; }
	* 合并单元格的边框

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    table {
      text-align: center;
      /* 折叠属性 */
      border-collapse: collapse;
    }

    td {
      /* 上下都有间距，需要折叠 */
      border: 1px solid #333;
      padding: 8px 16px;
    }

    table tr:nth-child(1) {
      font-weight: 700;
    }
  </style>
</head>
<body>
  <table>
    <tr>
      <td>排名</td>
      <td>股票名称</td>
      <td>股票代码</td>
      <td>股票价格</td>
      <td>股票涨跌</td>
    </tr>
    <tr>
      <td>1</td>
      <td>贵州茅台</td>
      <td>600519</td>
      <td>1800</td>
      <td>5%</td>
    </tr>
    <tr>
      <td>2</td>
      <td>腾讯控股</td>
      <td>0700</td>
      <td>400</td>
      <td>3%</td>
    </tr>
    <tr>
      <td>3</td>
      <td>五粮液</td>
      <td>000858</td>
      <td>160</td>
      <td>8%</td>
    </tr>
    <tr>
      <td>4</td>
      <td>东方财富</td>
      <td>300059</td>
      <td>25</td>
      <td>4%</td>
    </tr>
  </table>
</body>
</html>
```

![image-20230710204311682](../../../Coderwhy/pic/image-20230710204311682.png)

### 3、表格其他元素

* thead
	* 表格的表头

* tbody
	* 表格的主体

* tfoot
	* 表格的页脚

* caption
	* 表格的标题

* th
	* 表格的表头单元格

![image-20230710203612392](../../../Coderwhy/pic/image-20230710203612392.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    table {
      text-align: center;
      /* 折叠属性 */
      border-collapse: collapse;
    }

    td, th{
      /* 上下都有间距，需要折叠 */
      border: 1px solid #333;
      padding: 8px 16px;
    }

    /* table tbody tr:nth-child(1) {
      color: red;
      font-weight: 700;
    } */

    table thead tr:nth-child(1) {
      color: red;
      font-weight: 700;
    }

  </style>
</head>
<body>
  <table>
    <caption>热门股票</caption>
    <thead>
      <tr>
        <th>排名</th>
        <th>股票名称</th>
        <th>股票代码</th>
        <th>股票价格</th>
        <th>股票涨跌</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>贵州茅台</td>
        <td>600519</td>
        <td>1800</td>
        <td>5%</td>
      </tr>
      <tr>
        <td>2</td>
        <td>腾讯控股</td>
        <td>0700</td>
        <td>400</td>
        <td>3%</td>
      </tr>
      <tr>
        <td>3</td>
        <td>五粮液</td>
        <td>000858</td>
        <td>160</td>
        <td>8%</td>
      </tr>
      <tr>
        <td>4</td>
        <td>东方财富</td>
        <td>300059</td>
        <td>25</td>
        <td>4%</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td>5</td>
        <td>其他</td>
        <td>其他</td>
        <td>其他</td>
        <td>其他</td>
      </tr>
    </tfoot>
  </table>
</body>
</html>
```

![image-20230710204249017](../../../Coderwhy/pic/image-20230710204249017.png)



## 四、表格元素

### 1、单元格合并

* 在某些特殊的情况下, 每个单元格占据的大小可能并不是固定的
	* 一个单元格可能会跨多行或者多列来使用;

* 单元格合并分成两种情况:
	* 跨列合并 : 使用colspan
		* 在最左边的单元格写上colspan属性, 并且省略掉合并的td;
	* 跨行合并 : 使用rowspan
		* 在最上面的单元格协商rowspan属性, 并且省略掉后面tr中的td;

![image-20230710204709497](../../../Coderwhy/pic/image-20230710204709497.png)

![image-20230710204724765](../../../Coderwhy/pic/image-20230710204724765.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    table {
      border-collapse: collapse;
      text-align: center;
    }

    td {
      border: 1px solid red;
      padding: 10px 20px;
    }

  </style>
</head>
<body>
  <!-- 
    1、确定“谁”需要跨行或者跨列
    2、确定是跨行还是跨列
    3、跨几行或几列
  -->

  <!-- 跨列演示 -->
  <table>
    <tr>
      <td colspan="2">1-1</td>
      <!-- 多出来需要删除 -->
      <!-- <td>1-2</td> -->
    </tr>
    <tr>
      <td>2-1</td>
      <td>2-2</td>
    </tr>
  </table>

  <br>
  <table>
    <tr>
      <td rowspan="2">1-1</td>
      <td>1-2</td>
    </tr>
    <tr>
      <!-- <td>2-1</td> -->
      <td>2-2</td>
    </tr>
  </table>
</body>
</html>
```

![image-20230710211945313](../../../Coderwhy/pic/image-20230710211945313.png)

### 2、单元格合并练习（结构伪类）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    table {
      border-collapse: collapse;
      text-align: center;
    }

    /* 方式一 */
    /* tr.head {
      font-weight: 700;
      font-size: 20px;
    } */

    /* 方式二 */
    /* table tr:nth-child(1), table tr:nth-child(2) {
      font-weight: 700;
      font-size: 20px;
    } */

    /* 结构伪类选择器：
    n的取值：0和整数
    0, 1, 2, 3, 4,.... 
    -n + a 为前 a行
    */
    table tr:nth-child(-n + 2) {
      font-weight: 700;
      font-size: 20px;
    }

    table tr td[rowspan] {
      font-weight: 700;
      font-size: 20px;
    }

    /* table tr:nth-child(-n + 2), table tr td[rowspan] {
      font-weight: 700;
      font-size: 20px;
    } */
      
    td {
      border: 1px solid red;
      width: 100px;
      height: 30px;
    }
  </style>
</head>
<body>

  <table>
    <!-- <tr class="head"> -->
    <tr>
      <td colspan="6">课程表</td>
      <!-- <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td> -->
    </tr>

    <!-- <tr class="head"> -->
    <tr>
      <td></td>
      <td>星期一</td>
      <td>星期二</td>
      <td>星期三</td>
      <td>星期四</td>
      <td>星期五</td>
      
    </tr>
    <tr>
      <td rowspan="4">上午</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <td rowspan="4">下午</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <td rowspan="2">晚自习</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
    <tr>
      <!-- <td>数学</td> -->
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
      <td>数学</td>
    </tr>
  </table>

</body>
</html>
```

![image-20230710213917331](../../../Coderwhy/pic/image-20230710213917331.png)



## 五、表单属性

### 1、常见的表单元素

* form
	* 表单, 一般情况下，其他表单相关元素都是它的后代元素

* input
	* 单行文本输入框、单选框、复选框、按钮等元素

* textarea
	* 多行文本框

* select、option
	* 下拉选择框

* button
	* 按钮

* label
	* 表单元素的标题

### 2、input元素使用

![image-20230711163912260](../../../Coderwhy/pic/image-20230711163912260.png)

[input使用链接](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>

  <!-- 行内替换元素 -->
  <!-- 两个框需要不同行显示，用div包裹 -->
  <div>
    <input type="text">
  </div>
  <!-- <br> -->
  <div>
    <input type="password">
  </div>
  <div>
    <input type="time">
  </div>
  <div>
    <input type="date">
  </div>
  <div>
    <input type="file">
  </div>  
  <div>
    <!-- 两个效果都一样 -->
    <input type="text" readonly>
    <input type="text" readonly="readonly">
  </div>
  <div>
    <input type="text" disabled>
  </div>
  <div>
    <!-- 刷新网页之后自动聚焦 -->
    <input type="text" autofocus>
  </div>
</body>
</html>
```

![image-20230711165350667](../../../Coderwhy/pic/image-20230711165350667.png)

### 2、布尔属性（boolean attributes）

* 常见的布尔属性有disabled、checked、readonly、multiple、autofocus、selected

* 布尔属性可以没有属性值，写上属性名就代表使用这个属性
	* 如果要给布尔属性设值，值就是属性名本身

```html
<input type="text" disabled autofocus readonly>
  <input type="text" disabled="disabled" autofocus="autofocus" readonly="readonly">
```

### 3、表单按钮

* 表单可以实现按钮效果:
	* 普通按钮（type=button）：使用value属性设置按钮文字
	* 重置按钮（type=reset）：重置它所属form的所有表单元素（包括input、textarea、select）
	* 提交按钮（type=submit）：提交它所属form的表单数据给服务器（包括input、textarea、select）

* 也可以通过按钮来实现，button里面的type属性有reset和submit

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
  <div>
    <button>我是按钮</button>
  </div>

  <!-- 使用input实现按钮的效果 -->
  <form action="">
    <input type="text">
    <input type="date">
    <div>
      <!-- 两个普通按钮实现效果完全一样 -->
      <button>普通按钮</button>
      <input type="button" value="普通按钮">
    </div>
    <!-- 可以对from中其他表单元素进行重置 -->
    <div>
      <input type="reset" value="重置按钮">
      <button type="reset">重置按钮</button>
    </div>

    <!-- 对form中凄然表单元素进行提交（将数据提交给服务器） -->
    <div>
      <input type="submit" value="提交按钮">
      <button type="submit">提交按钮</button>
    </div>
  </form>

</body>
</html>
```

### 4、input和label的关系

* label元素一般跟input配合使用，用来表示input的标题
* label可以跟某个input绑定，点击label就可以激活对应的input变成选中

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
  <div>
    <!-- 点击用户选中后面的框 -->
    <label for="username">
      用户:
    </label>
    <input id="username" type="text">
  </div>

  <div> 
    <!-- 一般input放在label里面 -->
    <label for="password">
      密码: <input id="password" type="password">
    </label>
  </div>

</body>
</html>
```

### 5、radio的使用

* 我们可以将type类型设置为radio变成单选框:
	* name值相同的radio才具备单选功能

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>

  <!-- 在类型为radio的input中，如果name一样，那么两个radio就会互斥 -->
  <form action="/abc">
    <label for="male">
      <input id="male" type="radio" name="sex" value="male">男
    </label>
    <label for="female">
      <input id="female" type="radio" name="sex" value="female">女
    </label>
    <button type="submit">提交按钮</button>
  </form>

  <!-- <input type="submit" value="提交按钮"> -->

</body>
</html>
```



### 6、checkbox的使用

* 我们可以将type类型设置为checkbox变成多选框:
	* 属于同一种类型的checkbox，name值要保持一致

```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
  </head>
  <body>
    
    <form action="/abc">
      <div>
        您的爱好:
        <label for="basketball">
          <input id="basketball" type="checkbox" checked name="hobby" value="basketball">篮球
        </label>
        <label for="football">
          <input id="football" type="checkbox" name="hobby" value="football">足球
        </label>
      </div>
      <input type="submit">
    </form>

  </body>
  </html>
```

### 7、textarea的使用

* textarea的常用属性:
	* cols：列数
	* rows：行数

* 缩放的CSS设置
	* 禁止缩放：resize: none;
	* 水平缩放：resize: horizontal;
	* 垂直缩放：resize: vertical;
	* 水平垂直缩放：resize: both;

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    textarea {
      /* resize: horizontal; */
      resize: none;
    }
  </style>
</head>
<body>
  
  <form action="">
    <label for="info">
      个人描述：
      <textarea name="info" id="info" cols="30" rows="10"></textarea>
    </label>
  </form>

</body>
</html>
```

![image-20230711204153014](../../../Coderwhy/pic/image-20230711204153014.png)

### 8、select和option的使用

* option是select的子元素，一个option代表一个选项

* select常用属性
	* multiple：可以多选
	* size：显示多少项

* option常用属性
	* selected：默认被选中

```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
  </head>
  <body>
    
    <form action="/abc">
      <div>
        您的爱好:
        <label for="basketball">
          <input id="basketball" type="checkbox" checked name="hobby" value="basketball">篮球
        </label>
        <label for="football">
          <input id="football" type="checkbox" name="hobby" value="football">足球
        </label>
      </div>
      <input type="submit">
    </form>

  </body>
  </html>
```

### 9、from常见的属性

* form通常作为表单元素的父元素:
	* form可以将整个表单作为一个整体来进行操作;
	* 比如对整个表单进行重置;
	* 比如对整个表单的数据进行提交;

* form常见的属性如下:

* action
	* 用于提交表单数据的请求URL

* method
	* 请求方法（get和post），默认是get

* target
	* 在什么地方打开URL（参考a元素的target）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
  <form action="http://hongyuancoder.com/abc" method="post" target="_blank">
    <div>
      <label for="username">
        用户: <input id="username" type="text" name="username">
      </label>
    </div>
    <div>
      <label for="password">
        密码: <input id="password" type="password" name="password">
      </label>
    </div>

    <!-- 性别 -->
    <div>
      性别: 
      <label for="male">
        <input id="male" type="radio" name="sex" value="male">男
      </label>
      <label for="female">
        <input id="female" type="radio" name="sex" value="female">女
      </label>
    </div>

    <!-- 爱好 -->
    <div>
      爱好:
      <label for="basketball">
        <input id="basketball" type="checkbox" name="hobby" checked value="basketball">篮球
      </label>
      <label for="football">
        <input id="football" type="checkbox" name="hobby" value="football">足球
      </label>
    </div>

    <!-- 提交按钮 -->
    <button type="reset">重置内容</button>
    <button type="submit">提交内容</button>
  </form>

</body>
</html>
```

![image-20230711210120295](../../../Coderwhy/pic/image-20230711210120295.png)

