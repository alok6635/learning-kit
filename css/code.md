**# child & descendant selector**

```
<div class="parent">
      <p>para 1 in  div</p>
      <p>para 2 in  div</p>
      <h2><p>para 3 in div</p> </h2>
    </div>

CSS descendant -
.parent p {
        background: red;
      }

CSS Child-
.parent p {
        background: blue;
      }
```

**# adjacent sibling**
```
<div>
   <p>Paragraph 1 in the div.</p>
</div>
    <p>Paragraph 2. After a div.</p>
    <p>Paragraph 3. After a div.</p>
<div>
    <p>Paragraph 4 in the div.</p>
</div>
    <p>Paragraph 5. After a div.</p>
    <p>Paragraph 6. After a div.</p>

CSS- div + P{
        background: blue;
}
```
**# general sibling**
```
<div>
      <p>Paragraph 1 in the div.</p>
    </div>
    <p>Paragraph 2. After a div.</p>
    <p>Paragraph 3. After a div.</p>
    <div>
      <p>Paragraph 4 in the div.</p>
    </div>
    <p>Paragraph 5. After a div.</p>
    <p>Paragraph 6. After a div.</p>
     <span>heloo</span>
     <p>Paragraph 7. After a div.</p>
CSS-
div ~ p {
    color:red
}
```

**# pseudo-class selectors**
* enabled & disabled-
```
<form action="">
  <input type="text" value="alok"><br>
  <input type="text" value="kumar" disabled="disabled">
</form>

input[type=text]:enabled{
background: yellowgreen;
}
input[type=text]:disabled{
  background: red;
}
```

* Checked-
```
<form action="">
  <input type="radio" value="female" name="gender"> Female<br>
  <input type="checkbox" value="Bike"> I have a bike<br>
</form>

Css-
input:checked{
  height: 20px;
  width: 20px;
}
```

* focus-
```
<form>
  First name: <input type="text" name="firstname"><br>
  Last name: <input type="text" name="lastname">
</form>
CSS-
input:focus {
  background-color: yellow;
}
```
* not-

```
<h1>This is a heading</h1>
   <p>This is a paragraph.</p>
   <p>This is another paragraph.</p>
   <div>This is some text in a div element.</div>

CSS-
p {
    color:red;
  }
:not(p) {
    color:blue;
```

* nth last-child-
  
```
<p>The first paragraph.</p>
<p>The second paragraph.</p>
<p>The third paragraph.</p>
<p>The fourth paragraph.</p>

CSS-
p:nth-last-child(2) {
  background: red;
}
```
* nth-last-of-type-

```
<p>The first paragraph.</p>
<p>The second paragraph.</p>
<p>The third paragraph.</p>
<p>The fourth paragraph.</p>
CSS-
p:nth-last-of-type(2) {
  background: red;
}
```
* only-child-
```
<div><p>This is a paragraph.</p></div>
<div><span>This is a span.</span><p>This is a paragraph.</p></div>
CSS-
p:only-child {
  background: #ff0000;
}
```

**# psuedo elements**
* first-line & first-letter-
  
```
<p class="parent">
You can combine the ::first-letter and ::first-line pseudo-elements to add a special effect to the first letter and the first line of a text!</p>
<p>Note - 1. first-line,first letter pseudo-element can only be applied to block-level elements.</p>
Css-
.parent::first-letter{
color: red;
font-size: 40px;
}
.parent::first-line{
  color: blue;
}
```

* marker-
```
<ol>
  <li>one item</li>
  <li>two item</li>
  <li>three item</li>
</ol>
Css-
ol ::marker{ 
  color: red;
  font-size: 23px;
}
```
* selection-
```
<div class="selection">select  content to the mouse then change color</div>
Css-
.selection::selection{
  color: red;
  background: yellow;
}
```


**# attribute selectors**

*## 1.[attribute]-
 [attribute] selector is used to select elements with a specified attribute.
```
    <div class="att_selector1">
      <a href="https://www.w3schools.com">w3schools.com</a>
      <a href="http://www.disney.com" target="_blank">disney.com</a>
      <a href="http://www.wikipedia.org" target="_top">wikipedia.org</a>
    </div>
Css-
        .att_selector1 a[target] {
          background-color: yellow;
        }
```    
* 2.[attribute="value"]- 

```
   <div class="att_selector2">
      <a href="https://www.w3schools.com">w3schools.com</a>
      <a href="http://www.disney.com" target="_blank">disney.com</a>
      <a href="http://www.wikipedia.org" target="_top">wikipedia.org</a>
    </div>
 Css-  .att_selector2 a[target="_blank"] {
          background-color: palevioletred;
        }   
```

* 3.[attribute~="value"]-
```
    <div class="att_selector3">
      <p>
        All images with the title attribute containing the word "flower" get a
        yellow border.
      </p>
      <img
        src="../assets/img/klematis.jpg"
        title="klematis flower"
        width="150"
        height="113"
      />
      <img src="../assets/img/img4.jpg" title="flower" width="224" height="162" />
      <img
        src="../assets/img/img_flwr.gif"
        title="tree"
        width="200"
        height="358"
      />
      </div>
Css-
          .att_selector3 [title~="flower"] {
          border: 5px solid yellow;
        }

```

* 4.[attribute|="value]-
```
 <div class="att_selector4">
<h1 class="top-header">Welcome</h1>
<p class="top-text">Hello world!</p>
<p class="topcontent">Are you learning CSS?</p>
    </div>
Css-
  .att_selector4 [class|=top]{
        background: yellow;
    }    

```

* 5.[attribute^="value"]-
```
<div class="att_selector5">
    <h1 class="top-header">Welcome</h1>
<p class="top-text">Hello world!</p>
<p class="topcontent">Are you learning CSS?</p>
</div>
Css-
.att_selector5 [class^="top"] {
  background: orange;
}
```

* 6.[attribute$="value"]-
```
<div class="att_selector6">
    <div class="first_test">The first div element.</div>
<div class="second">The second div element.</div>
<div class="my-test">The third div element.</div>
<p class="mytest">This is some text in a paragraph.</p>
</div>
Css-
.att_selector6 [class$="test"] {
  background: green;
}
```
* 7.[attribute*="value"]-
```
<div class="att_selector7">
    <div class="first_test">The first div element.</div>
<div class="second">The second div element.</div>
<div class="my-test">The third div element.</div>
<p class="mytest">This is some text in a paragraph.</p>
</div>
Css-
    [class*="te"] {
      background: yellow;
    }
```

**# positions**


* static-
```
 <div class="demo">
   </div>
.demo{
    width: 100px;
    height: 100px;
    background: red;
    position: static;
    left:30px;
  }   
```

* Relative-
```
 <div class="demo">
    <p>aaaaaaaaaaaaaaaaaa</p>
   </div>
  p{
    position: relative;
    left: 100px;
  }

```
* Absoulte-
```
<p>kkkkkkkkkkkkkkk</p>
<p>kkkkkkkkkkkkkkk</p>
<p>kkkkkkkkkkkkkkk</p>
   <div>
    <p>aaaaaaaaaaaaaaaaaa</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p class="absoulte">wwwwwwwwwwwwwwwwwww</p>
    <p>aaaaaaaaaaaaaaaaaa</p>
   </div>
Css-
div{
  position: relative;
}
.absoulte{
    position: absolute;
    top:140px;
    background: green;
  }
```
* Fixed-
body is always relative in fixed position property
```
<h3>hhhhhhhhhhh1</h3>
<h3>hhhhhhhhhhh2</h3>
<h3>hhhhhhhhhhh3</h3>
<h3>hhhhhhhhhhh4</h3>
   <div>
    <p>aaaaaaaaaaaaaaaaaa</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p>ssssssssssssssssss</p>
    <p class="fixed">wwwwwwwwwwwwwwwwwww</p>
    <p>aaaaaaaaaaaaaaaaaa</p>
   </div>
   Css-
  .fixed{
    position: fixed;
    top:240px;
    background: red;
  }

```
* Sticky-

 ```
 <div class="sticky">I am sticky I can not move top and bottom please scrool the data</div>

    <div style="padding-bottom  :1000px">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe nemo possimus dolorum nostrum minima, asperiores porro voluptatem? Maxime magni fugit, ut tempore, dolores architecto vero quidem, inventore ab veniam non.</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe nemo possimus dolorum nostrum minima, asperiores porro voluptatem? Maxime magni fugit, ut tempore, dolores architecto vero quidem, inventore ab veniam non.</p>
    </div>
   </div>
 Css-
 div.sticky {
  position: sticky;
  top: 70px;
  padding: 5px;
  background-color: #cae8ca;
  border: 2px solid #4CAF50;
}
```



**# z-index**


	
```
	<div class="demo"></div>
        <div class="demo1"></div>
.demo {
            width: 50px;
            height: 50px;
            background-color: red;
            margin-bottom: 5px;
        }
        .demo1 {
            width: 50px;
            height: 50px;
            background-color: blue;
            position: absolute;
            top: 10px;
            z-index: -1;
        }
```


**# overflow**

```
* visible-

<div class="visible">You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.
    </div>
.visible{
      background-color: coral;
      width: 200px;
      height: 65px;
      overflow: visible;
      margin-bottom: 55px;
            }
* hidden-

<div class="hidden">You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.
        </div>
.hidden {
    background-color: coral;
    width: 200px;
    height: 55px;
    overflow: hidden;
}

* scroll-
   <div class="scroll">This text is really long and the height of its container is only 100 pixels. Therefore, a scrollbar is added to help the reader to scroll the content. Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi. Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet doming id quod mazim placerat facer possim assum. Typi non habent claritatem insitam; est usus legentis in iis qui facit eorum claritatem.
</div>
.scroll{
  background: #4CAF50;
  width: 50%;
  height: 100px;
  overflow: scroll;
    }

* auto-
<div class="auto">You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.
</div>
.auto{
  background-color: coral;
  width: 200px;
  height: 65px;
  overflow: auto; 
    }
```

**# transition**
```
<div></div>
CSS-
div{
    width: 100px;
    height: 100px;
    background: red;
    transition: width 2s, transform 1s;
}
div:hover {
    width: 300px;
    height: 300px;
    transform: rotate(180deg);
    background: gray;
  }
```

**given two div. div 1 have 1 para and div 2 have 2 para.change the color of div 1 para no using any class & id of parent div**

```
 <div>
    <p>aaaaaaaaaaaaaaaaaa</p>
   </div>
   <div>
    <p>ssssssssssssssss</p>
    <p>dddddddddddddddddddddd</p>
   </div>

Css-
p:only-of-type {
  background: red;
} 
```

**define the box sizing and what is the default value of box sizing.given a div width(1000px * 50px) & padding 10px & border 5px what effect is width of div using box-sizing or without box-sizing.**

```
* without box sizing-
      <div class="demo"></div>
Css-
.demo{
    width: 1000px;
    height: 50px;
    padding: 10px;
    border: 5px solid green;
    background: red;
}
Note:- width of the div is 1030px 

*  box sizing-
      <div class="demo"></div>
    Css- 
    .demo{
    width: 1000px;
    height: 50px;
    padding: 10px;
    border: 5px solid green;
    background: red;
    box-sizing:border-box;
}
Note-width of the div is 1000px.
```

* given the 6 div and manage 3 div in one row & 3 div in next row using by grid & flex.
```
<div class="container">
    <div class="item">one</div>
    <div class="item">two</div>
    <div class="item">three</div>
    <div class="item">four</div>
    <div class="item">five</div>
    <div class="item">six</div>
   </div>
Css-* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.item {
  background: red;
  padding: 10px;
}
.container {
  width: 100vw;
  height: 100vh;
  display: grid;
  gap: 5px 10px;
  /* grid-template-rows: auto auto; */
  /* grid-template-rows: 100px 100px;*/
  /* grid-template-rows: 1fr 1fr; */
  /* grid-template-columns: auto auto; */
  /* grid-template-columns: 100px 100px 100px; */
  /* grid-template-columns: 1fr 1fr 1fr; */
  grid-template-rows: repeat(2,1fr);
  grid-template-columns: repeat(3,1fr);
}

```
* given the 6 div  create a layout a header is first row & footer is thrid row and middle row have two part left part is sidebar right part divide in two row. top row is full width and bottom row have two coloum.
```
<div class="container">
    <div class="item header">Header</div>
    <div class="item sidebar">sidebar</div>
    <div class="item content1">content1</div>
    <div class="item content2">content2</div>
    <div class="item content3">content3</div>
    <div class=" item footer">footer</div>
   </div>
Css-
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.item {
  background: aqua;
  padding: 10px;
}
.container {
  width: 100vw;
  height: 100vh;
  display: grid;
  gap: 5px 10px;
  grid-template-rows: repeat(4,1fr);
  grid-template-columns: repeat(3,1fr);
}
.header{
  grid-column-start: 1;
  grid-column-end: 4;
}
.footer{
  grid-column-start: 1;
  grid-column-end: 4;
}
.sidebar{
grid-row-start: 2;
grid-row-end: 4;
}
.content1{
  grid-column-start: 2;
  grid-column-end: 4;
}
```
