
--------------

<details>
	
<summary>Interview Ques</summary>

* difference b/w align-item, vertical-align, justify-content.
* difference between display inline and inline-block.
* all ready we have b and i tag in xhtml but why used to new tag like-strong & em.
* i have create a page and write the media Query but page is not run what's it reason.
* data Attributes in html
* google font is not available in the machine how to use it.
* table row spacing & table padding. and create a table.
* difference b/w px,em,rem.
* difference b/w (>,+,~) in psuedo-class.
* what is css preprocesser.
* what is html entities.
* how to insert fav icon in our website.
* map tag in html.
   * map tag is used to define an image map.image map is an image with clickable areas. required name attribute of the map tag is 
       associated with the img's usemap attribute and creates a relationship between the image and the map.
*  difference between Absolute and Relative URLs
   * absolute URLs are typically used to link to resources on different websites.
   * relative URLs specify the location of a resource in relation to the current document. Full url is not required.They are used when 
     linking to resources within the same website.
* what is a fragment identifier in a URL.
   * fragment identifier is used to navigate to a specific section of the same webpage.Fragment identifier is preceded by a # 
        (hash)symbol.
* What is the purpose of the <base> element in html.
   *  base element in HTML is used to specify a base URL for relative URLs within a document.base element is typically placed 
       within the head section.
* what is the colspan attribute in html.
    *  The colspan attribute is used to merge multiple cells horizontally into a single cell. colspan attribute is applicable to <th> 
       and <td> only.
*  block & inline level element.
*  define doctype in html.
*  When doctype is not define in html.
*  why we use html5 & css3.
*  define html5 tags and html layout.
*  define combinator and write the css (~,+,) type combinator.
*  define  the pseudo class & use the n-th child.
*  define the Pseudo element.
*  define margin and padding.
*  define the position.tell us the absoulte and fixed position.
*  define the flex and explain the justify-content & align-items & vertical-align.
*  define radio button and checkbox.
*  What is by means by semantic tag.
*  difference is the popup, popover,tooltip.
    * tooltip- show a short text to respondents when they hover over a word or icon.
    * popover- use popovers to show a longer text or when you want to have a link to an external web page.it is shown when the 
               respondent clicks on a word or icon.popovers are a type of popup.
      NOTE- popups, dialogs, tooltips, and popovers — are displayed on top of the interface covering the content entirely or partially.
      * popup- a small window or banner that appears in the foreground while browsing a website.
*  grid model in bootstrap.
*  container width in bootstrap.
*  tell me cross browsing.
*  how many method of grid manage.
*  difference first-child & first-of-type.
 </details>

----------------

<details>
<summary>machine test</summary>

* how to use para itallic without using i and em tag used only css.
        * Ans- font-style:italic
* create a parent div and 5 child div and some differnt size contents all childs.set the horizontally and height is the same for all child.
* create the 10 box in horizontal when do the responsive show only 2.7 boxes.
* create the 6 div and manage 3 div in one row & 3 div in next row using by grid & flex.
* create a div width 200px height 100px and set to a div diagonally center to the window.(using flex,grid,translate)
* create two div parent and child.parent (200px*200px) & child(50*50).do the center horizontal & vertically or diagonally center.using flex,grid,translate.
* create a li and then do the 3rd li color is red. add no any class of (li,ul) & no add any extra div.
* create two div.div one have one para & div two have two para.change the color of div 1 para no using any class & id of parent div.
* define the box sizing and what is the default value of box sizing.given a div width(1000px* 50px) & padding 10px & border 5px what effect is width of div 
   using box-sizing or without box-sizing.
* i have three para but first para have no any text i want to first para background red no using and class & id.
    * using empty pseudo class.
*  i have three para i want to first para color is red no use any class & id.
   *  using first-of-type pseudo class.
     
  /// revision pending
* create a tooltip
* given two images showing in the desktop & mobile devices one is show & one is hide.
* given two images one image show in the desktop & one show in the mobile. 
* we have created a hover in the desktop & how to show in the mobile device.
* I have a 9 para i want to 3,6,9 para color is red.
* i have a only one div i want to horizonatlly center.
* i have two div one parent & one child i want to center it.
* i have four div one parent and three child.i want to change the color of 3rd child without using id & class.
</details>

-------------

<details>
<summary>flex</summary>

 **# flex v/s grid**
* flex is a one-dimensional layout for arranging items rows or columns.grid is two-dimensional layout manage rows and columns at the same time.


**# properties used in parent element.**

```
flex
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
gap,row-gap,column-gap
```
  
* flex -  placed to items accoding to main(horizontally) axis.it is used to parent element.using flex change a div height then all divs takes the same height.
* flex-direction-  placed to items accoding to axis.
 ```
    row(default)
    row-reverse
    column
    column-reverse.
```
* flex-wrap -
```
nowrap(default)
wrap
wrap-reverse.
```
  
* flex-flow - shorthand property for flex-direction and flex-wrap properties.
  
<details>
<summary>demo</summary>
 
```
<div class="flex-container">
   <div>1</div>
  <div>2</div>
  <div>3</div>  
  <div>4</div>
  <div>5</div>
  <div>6</div>  
</div>
.flex-container {
  display: flex;
  flex-flow: row-reverse wrap;
}
.flex-container > div {
  background-color: #f1f1f1;
  width: 100px;
  margin: 10px;
  text-align: center;
  font-size: 30px;
}
```
</details>
 
* justify-content - placed to items accoding to main axis(horizontaly).
  
```
    flex-start(default)
    flex-end
    center
    space-between
    space-around
    space-evenly
  ```

![image](https://github.com/alok6635/study-kit-2024/assets/96730792/e58a563d-032a-4056-9d0b-56ca2312dd32)

  
* align-items -  placed to items accoding to cross axis(vertically).
  ```
   stretch(default)
   flex-start
   start-end
   center
   base-line
  ```

![image](https://github.com/alok6635/study-kit-2024/assets/96730792/ca0c2d9e-a8bc-47f8-bfde-e8bc8c0fe3e4)

* align-content-  align-content property is used to align the flex lines.
```
center
space-between
space-around
space-evenly
flex-start
flex-end

```
![image](https://github.com/alok6635/study-kit-2024/assets/96730792/74c20f1e-d546-4111-9d02-54ee0935c95d)

<details>
<summary>center</summary>
	
```
<div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>  
        <div>4</div>
        <div>5</div>
        <div>6</div>  
        <div>7</div>
        <div>8</div>
        <div>9</div>  
        <div>10</div>
        <div>11</div>
        <div>12</div>  
      </div>
.main {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
    height: 400px;
}  
  .main > div {
    background-color: #f1f1f1;
    width: 200px;
    margin: 10px
  }	
```
</details>


**# properties used in the child element**

```
order
flex-grow
flex-shrink
flex-basis
align-self
flex
```

* flex-order-  order property specifies the order of the flex items.order value must be a number, default value is 0.
<details>
<summary>order</summary>
	
```
<div class="main">
  <div style="order: 3">1</div>
  <div style="order: 2">2</div>
  <div style="order: 4">3</div>
  <div style="order: 1">4</div>
</div>	
.main{
    display: flex;
}
.main div{
    width: 50px;
    height: 50px;
    background: antiquewhite;
    margin: 0 5px;
}
```
</details>

* flex-grow-  flex-grow property specifies how much a flex item will grow relative to the rest of the flex 
               items.value must be a number, default value is 0.
<details>
<summary>flex-grow</summary>
	
```
 <div class="main">
        <div style="flex-grow: 1">1</div>
        <div style="flex-grow: 1">2</div>
        <div style="flex-grow: 2">3</div>
        <div style="flex-grow: 6">4</div>
      </div>
.main{
    display: flex;
}
.main div{
    width: 50px;
    height: 50px;
    background: antiquewhite;
    margin: 0 5px;
}
```	
</details>

* flex-shrink- flex-shrink property specifies how much a flex item will shrink relative to the rest of the flex items.
               value must be a number, default value is 1.
  * it is not understud to me.
<details>
<summary>flex-shrink</summary>
	
```
<div class="main">
<div>1</div>
<div>2</div>
<div style="flex-shrink: 3">3</div>
<div>4</div>
<div>5</div>
</div>
.main{
    display: flex;
}
.main div{
    width: 50px;
    height: 50px;
    background: antiquewhite;
    margin: 0 5px;
}
```	
</details>
	
* flex-basis-  flex-basis property specifies the initial length of a flex item.
<details>
<summary>flex-basis</summary>
	
```
<div class="main">
<div>1</div>
  <div>2</div>
  <div style="flex-basis: 200px">3</div>
  <div>4</div>
  <div>5</div>
</div>
.main{
    display: flex;
}
.main div{
    width: 50px;
    height: 50px;
    background: antiquewhite;
    margin: 0 5px;
}
```
</details>

* align-self-  align-self property specifies the alignment for the selected item inside the flexible container.align-self property overrides the default alignment 
                 set by the container's align-items property.
  
```
align-self- center
align-self- start
align-self- end
```

<details>
<summary>align-self</summary>
	
```
<div class="main">
<div>1</div>
  <div>2</div>
  <div style="align-self: center">3</div>
  <div>4</div>
  <div>5</div>
</div>
.main{
    display: flex;
    height: 100px;
}
.main div{
    width: 50px;
    background: antiquewhite;
    margin: 0 5px;
}
```
</details>
  
* flex- note:flex property is a shorthand property for the flex-grow, flex-shrink, and flex-basis properties

<details>
<summary>flex</summary>
	
```
 <div class="main">
        <div>1</div>
        <div>2</div>
        <div style="flex: 0 0 200px">3</div>
        <div>4</div>
      </div>
.main{
    display: flex;
}
.main div{
    width: 50px;
    background: antiquewhite;
    margin: 0 5px;
    height: 50px;
}
```
	
</details>

</details>

--------------

<details>
<summary>grid</summary>

**# properties for the parent element**

```
grid
inline-grid
grid-template-columns
grid-template-rows
grid-auto-columns
grid-auto-rows
justify-content
justify-items
align-content
align-items

```
* grid- generates a block level grid.
<details>
<summary>grid </summary>
	
```
  <div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </section>
    </div>
.main {
    display: grid;
  }
 .main div {
    background-color: aliceblue;
    margin: 5px;
  }
  
```
</details>

* inline-grid-  generates a inline-level grid.
<details>
<summary>inline-grid </summary>
	
```
 <div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </section>
    </div>
.main {
    display: inline-grid;
  }
 .main div {
    background-color: aliceblue;
    margin: 5px;
    padding: 20px;
  }
```

</details>

<details>
<summary>grid-template-columns & rows </summary>

```
 <div class="main">
        <div class="item item1">Item 1</div>
        <div class="item item2">Item 2</div>
        <div class="item item3">Item 3</div>
        <div class="item item4">Item 4</div>
        <div class="item item5">Item 5</div>
        <div class="item item6">Item 6</div>
        <div class="item item7">Item 7</div>
        <div class="item item8">Item 8</div>
        <div class="item item9">Item 9</div>
      </div>
.main >div{
    background: blue;
    border: 2px solid black;
    padding: 10px;
}
.main{
  max-width: 1300px;
  border: 1px solid red;
  margin:  0 auto;
 display: grid;
  /* grid-template-columns: 100px 100px 100px; */
  /* grid-template-columns: 1fr 1fr 1fr; */
   grid-template-columns: repeat(3,1fr);
   grid-template-rows: 100px 50px 150px;
}

@@ what is fr-
 fr is a fractional unit.
ex- container width=3000px
5 fr=3000px
1 fr=600px
```
</details>



* justify-content
```
start
center
end
stretch
space-between
space-around
space-evenly
```
<details>
<summary>justify-content</summary>

```
 <div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
        <div>5</div>
        <div>6</div>
        <div>7</div>
        <div>8</div>
    </div>
</div>
.main >div{
    background: blue;
    border: 2px solid black;
    padding: 10px;

}
.main{
  display: grid;
  grid-template-columns: repeat(4, 40px);
 justify-content: center;
}
```
</details>

* justify-items
```
stretch- default
start
end
center

```
<details>
	<summary>justify-items</summary>

```
 <div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </section>
    </div>
.main {
    display: grid;
  justify-items: center;
  grid-template-columns: 1fr 1fr;
  margin: 10px;
  }
 .main div {
    background-color: aliceblue;
    margin: 5px;
    padding: 20px;
  }
``` 
</details>

* align-content
```
stretch- default
start
center
end
space-between
space-around
space-evenly
```

 <details>
<summary>align-content</summary>
	 
```
 <div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </section>
    </div>
.main {
    display: grid;
    align-content: center;
    grid-template-columns: 1fr 1fr;
    margin: 10px;
    height: 300px;
  }
 .main div {
    background-color: aliceblue;
    margin: 5px;
    padding: 20px;
  }
```

 </details>

* align-items
```
stretch- default
start
center
end
```
<details>
<summary>align-items</summary>	

```
 <div class="main">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </section>
    </div>
.main {
    display: grid;
  align-items: center;
  grid-template-columns: 1fr 1fr;
  height: 400px;
}
 .main div {
    background-color: aliceblue;
    margin: 5px;
    padding: 20px;
  }
``` 
</details>

  
* grid-gap
  * track- gap between two rows & column


**### Properties for the Children element**
* grid-column-start
* grid-column-end
* grid-row-start
* grid-row-end
* justify-self
* align-self
* place-self

</details>

--------

<details>
<summary>positions</summary>	


* static- default
  * Static positioned elements are not affected by the top, bottom, left, and right properties.
* relative
  *  An element with position: relative; is positioned relative to its normal position.
* absolute
  * an element with position: absolute; is positioned relative to the nearest positioned ancestor. 
* fixed
  * an element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the 
   page is scrolled.
* sticky
  * An element with position: sticky; is positioned based on the user's scroll position.a sticky element toggles between relative 
   and fixed, depending on the scroll position.

**# difference b/w position absoulte & relative** 
**# difference b/w position fixed & sticky** 

https://www.youtube.com/watch?v=gOHqGT2RUt0  
    
</details>

---------

<details>
	
<summary>css selectors </summary>

* simple selectors- class,id,tag,universal.
* combinator selectors- relationship between the selectors.
* pseudo-class selectors
* pseudo-elements selectors
* attribute selectors

**# Combinator selectors**   

* child selector(>)
   * child selector selects all elements that are the children of a specified element.
* descendant selector(space)
   * descendant selector matches all elements that are descendants of a specified element.
* adjacent sibling selector(+)
   * used to select an element that is directly after another specific element.
* general sibling selector (~)
   * selects all elements that are next siblings of a specified element.

**# pseudo-class selectors**
* pseudo-class is used to define a special state of an element.
  
```
   first-child ,first-of-type, last-child, last-of-type, nth-child, nth-last-child, nth-last-of-type, nth-of-type,  
   only-of-type, only-child, empty,hover, active, focus, enabled, disabled, checked, visited, target, link, not(selector),
```

**# Pseudo-element selectors**
* used to style specified parts of an element.
  
```
first-line, first-letter, after, before, marker, selection
```
* marker pseudo-element selects the markers of list items.
* selection pseudo-element matches the portion of an element that is selected by a user.\


**# attribute selectors**

* [attribute] 
* [attribute="value"] 
* [attribute~="value"] 
* [attribute|="value"] 
* [attribute^="value"] 
* [attribute$="value"] 
* [attribute*="value"] 

</details>

---------

**# box model**
* box model is a box that wraps around every html element.it consists of margins, borders, padding, and the actual content.

---------

**# box sizing**
* box-sizing property allows us to include the padding and border in an element's total width and height.default property of box- 
 sizing- content-box.
* if we have a div and not using the box-sizing border-box and gives the padding of the div then width is increase od the div but using 
  the  box-sizing border-box the width is not increase of the div.
```
width od div= 320px
+ 20px (left + right padding)
+ 10px (left + right border)
+ 0px (left + right margin)
=350px
```
---------

**# css Opacity**
* transparency of an element.opacity property can take a value from 0.0 - 1.0. The lower value, the more transparent:

---------


**# visibilty hidden v/s display none**
* visibilty remove opacity but element contains the space and hidden remove the element and remove the space.

---------


**# Margin**
* Margins are used to create space around elements, outside of any defined borders.set the margin property to auto to horizontally center the element within its container.top and bottom margins of elements are sometimes collapsed into a single margin that is equal to the largest of the two margin.

---------

**# Padding**
* Padding is used to create space around an element's content, inside of any defined borders.

---------

**# z-index**
* z-index property specifies the stack order of an element.it can have a positive or negative stack order. it is not allow parent child 
 relation. it's apply siblings.


---------


**# overflow**
* overflow property specifies to add scrollbars when the content of an element is too big to fit in the specified area.
* visible,hidden,scroll,auto


---------


**# css 2D transforms methods**
* transforms allow you to move, rotate, scale, and skew elements
* translate- moves an element from its current position (according to parameters given for the X-axis and the Y-axis)
* rotate- rotates an element clockwise or counter-clockwise according to a given degree.
* scale- increases or decreases the size of an element (according to the parameters given for the width and height).
* skew- method skews an element along the X and Y-axis by the given angles.
  * skewX- method skews an element along the X-axis by the given angle.
  * skewY- method skews an element along the Y-axis by the given angle
* matrix- matrix method combines all the 2D transform methods into one. take six parameters Ex- matrix(scaleX(), skewY(), skewX(), 
          scaleY(), translateX(), translateY())
---------

**# css 3d transforms methods**
* rotateX,rotateY,rotateZ()
  
---------

**# css transitions**
*  transitions allows you to change property values smoothly, over a given duration.
    * transition-delay
    * transition-duration
    * transition-property
    * transition-timing-function

---------
**# css animations**
* animation lets an element gradually change from one style to another.
* @keyframes
* animation-name
* animation-duration
* animation-delay
* animation-iteration-count
* animation-direction
* animation-timing-function
* animation-fill-mode
  
----------

**# media query**

* mobile devices(portrate)- 320px-480px
* Tablets or iPad: 480px - 768px
* Laptop or small-size screen: 768px -1024px
* Desktop or large-size screen: 1024px -1200px
* Extra-large size device: 1200px and more

<details>
<summary>Code</summary>

```
* tablet portrate-

@media (max-width:1200px){
    .demo{
        background: red }}

* tablet landscape-

@media (max-width:950px){
    .demo{
        background: pink }}

* mobile landscape-

@media (max-width:767px){
    .demo{
        background: black }}

* mobile portrate-

@media(max-width:450px){
 .demo{
        background: black }}
```
</details>

----------


**# background shorthand property**
* background-color
* background-image
* background-repeat
* background-attachment
* background-position
  

-------------

<details>
<summary>Html</summary>	

**# html history**
* www-Invented by Tim Berners LEE(1989).html-Invented by Tim Berners LEE(1991)

**# doctype in html**
* doctype declaration defines that this document is an html5 document.it is very short, and case-insensitive.

**# html**
* html is a markup language it is used to create web pages to present the content on the world wide web. html documents are made up two 
  things: content and tags.

**# head element**
* head element contains meta information about the html page.
	
**# meta**
* meta specify the character set,page description, viewport settings.it used for search engine optimization to tell the search engine 
  about the page contents.

**# meta data in html** 
* html metadata is data about the html document. meta data is not displayed. metadata typically define the document title, character 
  set, styles, scripts, and other meta information.

**# title**
* title specifies a title for the html page.(which is show in the title bar or html page.title is important for seo.search engine 
  algorithms to decide the order when listing pages in search results.

**# base**
* base element specifies the base URL and/or target for all relative URLs in a page.base tag must have either an href or a target 
  attribute present, or both.

**# body**
* body element defines the document's body, and is a container for all the visible contents, such as headings,paragraphs,images, 
  hyperlinks,tables,lists, etc.

**# html tags and html elements**
* html element is the root element of an html page.elements are defined by a starting tag,some content and a closing tag.
* tags are the primary component of the html that defines how the content will be structured.

**# attributes**
* attributes provide additional information about html elements.

**# attributes of <a> tags**
* a tag defines a hyperlink.href attribute- href attribute specifies the url of the page the link goes to.
  
**# attributes of image tags**
* src attribute specifies the path to the image.width and height,alt attribute specifies an alternate text for an image.
* two ways to specify the url in the src attribute.absolute url-links to an external image that is hosted on another website.relative 
  url-links to an image that is hosted within the website.

**# style attribute**
* it can used to all tags for using the inline css.
  
**# lang Attribute of html tag**
* we should always include the lang attribute inside the html tag. to declare the language of the Web page.
  
**# title Attribute**
* title attribute defines some extra information about an element.

**# hyperlink in html.and difference b/w <a> & link tag.**
* a tag to specify the links in a webpage.a creates a path between two sections or two different html web pages.
* target attribute- open an url into a new tab in the browser upon a click.we need to add target attribute.
    * self- default, blank-opens in a new window or tab, parent- opens in a parent frame, top- opens in a full-body window.
* link is three ways- active- red & underlined, visited– purple & underlined, unvisited–blue & underlined.
* link tag defines a link between a document and an external resource.rel is by default attribute link tag. 
  
**# container tag and an empty tags.**
* container tags is opening tag some content and a closing tag.ex-<h1></h1>
* empty tags are the tags that do not have any content and closing tag.br,hr,img.

**# void elements**
* br,hr,img,meta etc.br tags are used to enter a new line into the html contents.hr defines a thematic break in an html page, and used 
  to separate content in a page.

**# difference b/w div & span**
* div,span element is used as a container.span is inline tag and div is block level tag.no required attributes, but style, class and id 
  are common.

**# difference b/w id & class attribute of html elements**
* class can use multiple (.) but id is unique (#)

**# html block and inline elements**
* every element have a default value.block-level element always starts on a new line and takes up the full width available.block level 
  element has a top and a bottom margin, whereas an inline element does not.ex-article,aside,blockquote
* inline element does not start on a new line and it only takes up as much width as necessary.ex-b,strong,span,br,em,img,sub,sup,input
  label,textarea,button.
  
**# formatting tags**
* b, strong, i, em, sub, sup, mark, ins, big, small, del.

**# list**
* a group of related items in lists.
  
**unordered list**
* unordered(bulleted) list starts with the ul tag.each list item starts with the li tag.
  
**ordered list**
* list items will be marked with numbers or alphabetical by default.
  
**description lists**
* description list is a list of terms, with a description of each term.
* dl tag defines the description list.dt tag defines the term(name) & the dd tag describes each term
* list-style-type property is used to define the style of the list item marker.
```
disc-sets the list item marker to a bullet(default).
circle-sets the list item marker to a circle.
square-sets the list item marker to a square.
```

**# entities**
* some characters are reserved like ‘<’, ‘>’, ‘/’, etc.

**# iframes**
* iframe is used to display a web page within a web page.

**# forms**
* form is used to collect the user inputs.form is a container of different input types like button,checkbox,number,text,password,submit.

**# form elements**
* label, input, textarea, button, select, datalist, fieldset, legend, output, option, optgroup.

**input types**
* text, textarea, checkbox, radio, submit, button. 

**# input attributes**
* placeholder, value, disabled, readonly, required, autofocus, autocomplete, min & max, maxlength, pattern, step, multiple, size, 
  height and width, list Attribute
  
**# forms attribute**
* action- defines the action to be performed when the form is submitted.
* method- specifies http method to be used when submitting the form data.http method when submitting form data is get,post.
* autocomplete- specifies whether a form should have autocomplete on or off.autocomplete is on, the browser automatically complete 
                  values based on values that the user has entered before.
* novalidate- it is a boolean attribute.when present,it specifies that the form-data(input) should not be validated when submitted.
* target- specifies where to display the response that is received after submitting the form.target attribute can have one of values.
         * blank-displayed in a new window or tab
         * self-displayed in the current window
         * parent-displayed in the parent frame
         * top-displayed in the full body of the window.

**# input form attributes**
* form, formaction, formenctype, formmethod, formtarget, formnovalidate, novalidate Attribute.

**# table tag**
* defines arrange data into rows and columns.
     * table element to define a table.tr define table row.td define table data.th define table heading.caption element to define a 
        table caption.

**# html layout**
* header- Defines a header for a document or a section.
* nav- Defines a set of navigation links
* section- Defines a section in a document
* article- Defines an independent, self-contained content
* aside- Defines content aside from the content (like a sidebar)
* footer- Defines a footer for a document or a section
* details- Defines additional details that the user can open and close on demand
* summary- Defines a heading for the details element.


**# semantic elements**
* a semantic element clearly describes its meaning to both the browser and the developer.ex-header,footer,form,table,article,details,
  section, summary,nav,time.
* non-semantic elements-tells nothing about its content. ex- div,span.
  

**# What is xhtml**

Syntax: XHTML has a stricter syntax than HTML, meaning that it must follow XML rules for proper formatting and structure. HTML, on the other hand, is more flexible in its syntax.
Document Type Definition (DTD): XHTML requires a DTD to be specified, which defines the rules for the structure of the document. HTML does not require a DTD.
Case sensitivity: XHTML is case sensitive, meaning that elements and attributes must be in lower case. HTML is not case sensitive.
Empty Elements: In XHTML, all empty elements must be closed, such as <br /> or <img src="image.jpg" alt="image" />. In HTML, some empty elements can be left open, such as <br> or <img src="image.jpg" alt="image">.
Attribute values: In XHTML, all attribute values must be quoted, while in HTML they can be either quoted or unquoted.
Error handling: XHTML has more strict error handling, with errors resulting in the page not being displayed properly. HTML is more forgiving of errors and will still display the page even if there are mistakes in the code.
Future compatibility: XHTML is designed to be compatible with future technologies and devices, while HTML may not be as compatible in the future.
* HTML does not support namespaces.XHTML supports namespaces, allowing for the integration of other XML languages.
* HTML allows for the use of deprecated attributes.XHTML does not allow the use of deprecated attributes and requires all attributes to be lowercase.
* HTML will continue to be supported by web browsers.XHTML support by web browsers is limited and it is now largely replaced by HTML5.

**# blockquote for quotations**
* blockquote element defines a section that is quoted from another source.q tag defines a short quotation.
  
**# abbr for abbreviations**
* abbr tag defines an abbreviation or an acronym-HTML,CSS,Dr.
  
**# cite for work title**
* cite tag defines the title of a creative work-a book, a poem, a song, a movie, a painting, a sculpture.
* Note: a person's name is not the title of a work.text in the <ite element usually renders in italic.
  
**# bdo for bi-directional override**
* bdo stands for bi-directional override.it is used to override the current text direction.
    
</details>

----------------

<details>
<summary>global css industy</summary>

```
::Table Of Content
1.) @FontFace Style
2.) Global TypoGraphy
3.) Forms Element
4.) Button & Link Element
5.) Helping Classes
6.) Header Section
7.) Footer Section
8.) Responsive CSS
	8.1) Media query  for tablet Portrate
	8.2)  Media query  for tablet landscape
	8.3) Media query  for Mobile Portrate
	8.4) Media query  for mobile landscape

1.) @FontFace Style
2.) Global TypoGraphy

* {
	-moz-box-sizing: border-box;
	box-sizing: border-box;
	-webkit-box-sizing: border-box;
}
img {
	max-width: 100%;
	height: auto;
	display: block;
}
.flex {
	display: flex;
}
.space-between-flex {	
	display: flex;	
	justify-content: space-between;	
}
a{
    text-decoration: none;
}
.align-center {
	text-align: center;
}
.btn {
    display: inline-block;
    color: #ffffff;
    background: #99c339;
    padding: 10px 92px;
    font-size: 15.07px;
    font-weight: 600;
    border-radius: 7px;
}
[class^="icon-"], .after-icon:after, .before-icon:before {
	background: url(../images/sprite.png) no-repeat;
	background-size: 250px auto;
}
.after-icon:after, .before-icon:before {
	content: '';
	position: absolute;
	left: 0px;
}
.absoulte{
    position: absolute;
    left: 0;
    top: 0;
}
.container{
    max-width: 1095px;
    margin: 0 auto;
}
h1,h2{
    font-size: 10px;
    color: #333333;
    font-weight: 600;
}
h3{
    font-size: 25px;
    color: #7a7a7a;
    font-weight: 400;
}
h4{
    font-size: 12.5px;
    font-weight: 700;
}
h5{
    font-size: 20px;
    font-weight: 300;
}
p{
    font-weight: 300;
    color: #012c40;
    line-height: 1.2 ;
    font-size: 17.5px;
}
body{
    font-size: 10px;
    color: #012c40;
    font-weight: 300;
}
6.) Header Section Start*/
6.) Header Section End*/
7.) Footer Section Start*/
7.) Footer Section End*/
-------------------------------------------
8.1) Media query  for tablet Portrate
-------------------------------------------
@media (max-width:1200px) {
   }
-------------------------------------------
8.2) Media query  for tablet Landscape
-------------------------------------------
@media (max-width:950px) {
   }
-------------------------------------------
8.3) Media query  for Mobile Portrate
-------------------------------------------
@media (max-width:767px) {
   }
-------------------------------------------
8.3) Media query  for Mobile Landscape
-------------------------------------------
@media (max-width:450px)  {
}

</details>


#### tooltip
```
<div class="tooltip">Hover over me
<span class="tooltiptext">Tooltip text</span>

css-
.tooltip {
  position: relative;
}

.tooltiptext {
  width: 120px;
  background-color: black;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;
  visibility: hidden;
  position: absolute;
}
.tooltip:hover .tooltiptext {
  visibility: visible;
}

```

</details>
</details>


  
```
display:flex
display:grid
display:float
display:inline-block
display:table-cell
```

* how to decrease website loading time.
```
Optimize Images
Minimize HTTP Requests
Enable Browser Caching
Minify HTML, CSS, and JavaScript
Use Content Delivery Networks (CDNs)
Reduce Third-Party Scripts
Optimize Fonts
```
* define image slicing.
* marque tag.
* Difine- display none & visiblity hidden.
```
it is used to create scrolling or moving text or images horizontally or vertically in the web page.
```

* html project handling.
```
sotware base coding & developing code from scratch.
Project Structure
Version Control
HTML Structure
Organize css
Responsive Design
Performance Optimization
```
* map area tag in html5.
* difference b/w placeholder & value.
* base tag of html.
```
base element specifies the base URL and/or target for all relative URLs in a page.
base tag must have either an href or a target attribute present, or both.
```
* difference in hover and focus.
* difference b/w div and aside.
* difference b/w input and textarea.
* a img is a logo and a slider and footer have some icons in social media .whitch contains in (jpg and png).
* one image have upload (png & jpg file).and img quality have perfect two's img .who's priority is high (jpg,png) 
* difference b/w jpg png svg gif img.
```
* jpg- 
Compressed 
Transparency-Does not support transparency. It has a solid background.
* png-
 images that require high quality and transparency.
* svg-
Compression: SVG is a vector format, which means it's based on mathematical equations and can be scaled without loss of quality.
Transparency: SVG supports transparency and can have elements with transparent backgrounds.
 scalable graphics and vector illustrations

* gif-
Compression- GIF uses lossless compression for simple images but can also use lossy compression for animations.
Transparency: Supports transparency with one color designated as transparent (usually used for simple transparency like a single-color background).
 simple animations and images with limited colors
```
* What are data attributes.
```
data attributes are used to store custom data directly inside htmlpages. they can be easily acessed via css and javascript. 
commom example- data-dismies,data-target,data-toggle etc.
```
* form validation js and css

  
**# difference input attribute disabled v/s read-only**
* disabled and readonly stop a user from editing an input field, but they do it in their own way. A disabled input field is like a 
  ghost, it's there but can't be interacted with, and its value is not included during form submission. Readonly, however, can be 
  interacted with (though not edited), and its value is included during form submission.


**# figure vs figcaption**
* figure tag specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.
* figcaption tag defines a caption for a figure element.figcaption element can be placed as the first or as the last child of a figure 
  element.


**# differ select & datalist**
 select defines a drop-down list.by default first item in the drop-down list is selected.
datalist- specifies a list of pre-defined options for an input element.
users will see a drop-down list of the pre-defined options as they input data.list attribute of the input element must refer to the id attribute of the datalist element.

**# fieldset & legend**

filedset- element is used to group related data in a form.
legend- tag is used to  a caption for the fieldset element.

**# figure and figcaption elements**
* figure specifies self-contained content like illustrations,diagrams,photos,code listings.
* figcaption defines a caption for a figure element.figcaption can be placed as the first or as the last child of a figure element.


**# difffer b & strong, i & em tag**
i- makes text italic
em- makes text italic but with added semantics importance.
b-bold
strong- marks the text as important


**# Bootstrap**
flow- container > row >  column 
* container-fluid is not takes margin in any device. but normal containers takes margins in small devices.
* can not define column inside column. define row then used column.







