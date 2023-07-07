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

## 三、表格元素



## 四、表格元素

## 五、表单合并

## 六、表单常见属性