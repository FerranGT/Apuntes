#CSS3 cascading style sheets

Hoja de estilo en cascada. Lenguaje usado para definir y crear la presentación de un documento estructurado escrito en HTML o XML 

La idea es separar la estructura de un documento de su presentación.

#SELECTORS

The most common selectors: type, class, and ID selectors.

**Type Selectors**

Type selectors target elements by their element type.For example, should we wish to target all division elements, <div>, we would use a type selector of div.

CSS -> div { ... }

The type selector has the lowest **specificity** weight and holds a point value of **0-0-1**. 

**Class Selectors**

Class selectors allow us to select an element based on the element’s class attribute value. Class selectors are a little more specific than type selectors, as they select a particular group of elements rather than all elements of one type.

Class selectors allow us to apply the same styles to different elements at once by using the same class attribute value across multiple elements.

class = cdata-list [CS]
This attribute assigns a class name or set of class names to an element. Any number of elements may be assigned the same class name or names. Multiple class names must be separated by white space characters.

HTML -> <div class="awesome">...</div>
CSS -> .awesome { ... }

The class selector has a medium **specificity** weight and holds a point value of **0-1-0**. 

**ID Selectors**

ID selectors are even more precise than class selectors, as they target only one unique element at a time. Just as class selectors use an element’s class attribute value as the selector, ID selectors use an element’s id attribute value as a selector.

Regardless of which type of element they appear on, id attribute values can only be used once per page. If used they should be reserved for significant elements.

id = name [CS]
This attribute assigns a name to an element. This name must be unique in a document.

HTML -> <div id="shayhowe">...</div>
CSS -> #shayhowe { ... }

<body id="index" class="home"> // we can use both of them or mutiples classe
<body class ="garden pool home">

ID selector has a high **specificity** weight and holds a point value of **1-0-0**


**Common Selectors Overview**

**Example**   **Classification**   **Explanation**

h1            **Type Selector**    Selects an element by it’s type

.tagline      **Class Selector**   Selects an element by the class attribute value, which may be reused multiple times per page

//#intro      **ID Selector**      Selects an element by the ID attribute value, which is unique and to only be used once per page


**Child Selectors Overview**

**Example**   **Classification**          **Explanation**

article h2    **Descendant Selector**     Selects an element that resides anywhere within an identified ancestor element

article > p   **Direct Child Selector**   Selects an element that resides immediately inside an identified parent element


**Sibling Selectors Overview**

**Example**  **Classification**             **Explanation**

h2 ~ p       **General Sibling Selector**   Selects an element that follows anywhere after the prior element, in which both elements share the same parent

h2 + p       **Adjacent Sibling Selector**  Selects an element that follows directly after the prior element, in which both elements share the same parent


**Attribute Selectors Overview**

**Example**            **Classification**               **Explanation**

a[target]              **Attribute Present Selector**   Selects an element if the given attribute is present

a[href="www.msn.com/"] **Attribute Equals Selector**    Selects an element if the given attribute value exactly matches the value stated

a[href*="login"]       **Attribute Contains Selector**  Selects an element if the given attribute value contains at least once instance of the value stated

a[href^="https://"]    **Attribute Begins With Selector** Selects an element if the given attribute value begins with the value stated

a[href$=".pdf"]        **Attribute Ends With Selector**  Selects an element if the given attribute value ends with the value stated

a[rel~="tag"]          **Attribute Spaced Selector**     Selects an element if the given attribute value is whitespace-separated with one word being exactly as stated

a[lang|="en"]          **Attribute Hyphenated Selector** Selects an element if the given attribute value is hyphen-separated and begins with the word stated


**Pseudo-classes Overview**

Pseudo-classes are similar to regular classes in HTML however they are not directly stated within the markup, instead they are a dynamically populated as a result of users actions or the document structure. The most common pseudo-class, and one you’ve likely seen before, is :hover. Notice how this pseudo-class begins with the colon character, :, as will all other pseudo-classes.


**Example**            **Classification**               **Explanation**

a:link                 **Link Pseudo-class**            Selects a link that has not been visited by a user

a:visited              **Link Pseudo-class**            Selects a link that has been visited by a user

a:hover                **Action Pseudo-class**          Selects an element when a user has hovered their cursor over it

a:active               **Action Pseudo-class**          Selects an element when a user has engaged it

a:focus                **Action Pseudo-class**          Selects an element when a user has made it their focus point

input:enabled          **State Pseudo-class**           Selects an element in the default enabled state

input:disabled         **State Pseudo-class**           Selects an element in the disabled state, by way of the disabled attribute

input:checked          **State Pseudo-class**           Selects a checkbox or radio button that has been checked

input:indeterminate    **State Pseudo-class**           Selects a checkbox or radio button that neither been checked or unchecked, leaving it in an indeterminate state

li:first-child         **Structural Pseudo-class**      Selects an element that is the first within a parent

li:last-child          **Structural Pseudo-class**      Selects an element that is the last within a parent

div:only-child         **Structural Pseudo-class**      an element that is the only element within a parent

p:first-of-type        **Structural Pseudo-class**      an element that is the first of it’s type within a parent

p:last-of-type         **Structural Pseudo-class**      an element that is the last of it’s type within a parent

img:only-of-type       **Structural Pseudo-class**      an element that is the only of it’s type within a parent

li:nth-child(2n+3)     **Structural Pseudo-class**      an element that matches the given number or expression, counting all elements from the beginning of the document tree

li:nth-last-child(3n+2) **Structural Pseudo-class**     an element that matches the given number or expression, counting all elements from the end of the document tree

p:nth-of-type(3n)      **Structural Pseudo-class**      an element that matches the given number or expression, counting only elements of it’s type from the beginning of the document tree

p:nth-last-of-type(2n+1) **Structural Pseudo-class**    an element that matches the given number or expression, counting only elements of it’s type from the end of the document tree

section:target         **Target Pseudo-class**          Selects an element whose ID attribute value matches that of the URI fragment identifier

div:empty              **Empty Pseudo-class**           Selects an element that does not contain any children or text nodes

div:not(.awesome)      **Negation Pseudo-class**        Selects an element not represented by the stated argument


**Pseudo-elements Overview**

Pseudo-elements are dynamic elements that don’t exist in the document tree, and when used within selectors these pseudo-elements allow unique parts of the page to be stylized. One important point to note, only one pseudo-element may be used within a selector at a given time.


**Example**            **Classification**               **Explanation**

.alpha:first-letter    **Textual Pseudo-elements**      Selects the first letter of text within an element

.bravo:first-line     **Textual Pseudo-elements**       Selects the first line of text within an element

div:before            **Generated Content Creates**     a pseudo-element inside the selected element at the beginning

a:after               **Generated Content Creates**     a pseudo-element inside the selected element at the end

::selection           **Fragment Pseudo-element**       Selects the part of a document which has been selected, or highlighted, by a users actions



**The Cascade**

Within CSS, all styles cascade from the top of a style sheet to the bottom, allowing different styles to be added or overwritten as the style sheet progresses.

```p {
  background: orange;
  font-size: 24px;
}
p {
  background: green;
}
```

Because the paragraph selector that sets the background color to green comes after the paragraph selector that sets the background color to orange, it will take precedence in the cascade. All of the paragraphs will appear with a green background. The font size will remain 24 pixels because the second paragraph selector didn’t identify a new font size.

**Combining Selectors & Spaces Within Selectors**

Within the combined selector, .hotdog p.mustard, there is a space between the hotdog class selector and the paragraph type selector but not between the paragraph type selector and the mustard class selector. The use, and omission, of spaces makes a large difference in selectors.

Since there isn’t a space between the paragraph type selector and the mustard class selector that means the selector will only select paragraph elements with the class of mustard. If the paragraph type selector was removed, and the mustard class selector had spaces on both sides of it, it would select any element with the class of mustard, not just paragraphs.

The best practice is to not prefix a class selector with a type selector. Generally we want to select any element with a given class, not just one type of element. And following this best practice, our new combined selector would be better as .hotdog .mustard.

Looking at our combined selectors from before, the first selector, .hotdog p, had both a class selector and a type selector. Knowing that the point value of a class selector is 0-1-0 and the point value of a type selector is 0-0-1, the total combined point value would be 0-1-1, found by adding up each kind of selector.

The second selector, .hotdog p.mustard, had two class selectors and one type selector. Combined, the selector has a specificity point value of 0-2-1. The 0 in the first column is for zero ID selectors, the 2 in the second column is for two class selectors, and the 1 in the last column is for one type selector.


#Complex Selectors



#How Are Elements Displayed?

Block-level elements occupy any available width, regardless of their content, and begin on a new line. Inline-level elements occupy only the width their content requires and line up on the same line, one after the other. Block-level elements are generally used for larger pieces of content, such as headings and structural elements. Inline-level elements are generally used for smaller pieces of content, such as a few words selected to be bold or italicized.

**BLOCK ELEMENTS**

A block element is rendered, as the name indicates, as an actual block. The block-element is as wide as it can possibly be, a rectangular that does not break across lines, and the width and height of the element can be regulated. Block-elements may contain inline elements and other block-elements.
Block-level elements begin on a new line, stacking one on top of the other, and occupy any available width. Block-level elements may be nested inside one another and may wrap inline-level elements. We’ll most commonly see block-level elements used for larger pieces of content, such as paragraphs.

**INLINE ELEMENTS**

The inline elements are treated as a part of the flow of the document and the size should normally not be changed manually. Only inline elements may be contained with inline-elements. And to make even more confusing, inline elements are the only elements that may be contained within a paragraph-element, even though the <p>-element is a block-element.
Inline-level elements do not begin on a new line. They fall into the normal flow of a document, lining up one after the other, and only maintain the width of their content. Inline-level elements may be nested inside one another; however, they cannot wrap block-level elements. We’ll usually see inline-level elements with smaller pieces of content, such as a few words.

The <p></p> element is a block-element, whereas the <b>-element is an inline-element. (b stands for bold and changes the appearance of the text)



A <div> is a block-level element that is commonly used to identify large groupings of content, and which helps to build a web page’s layout and design. A <span>, on the other hand, is an inline-level element commonly used to identify smaller groupings of text within a block-level element.


**Graceful Degradation** is a widely used term which ideology is basically using the latest technologies first, and then fix anything that needs fixing for older browsers. We do this on a daily basis: most of us code for Firefox first, then fix Internet Explorer. That is Graceful Degradation in the practice.

**Progressive Enhancement** refers to the habit of building first for the less capable, outdated browser and then enhance for the latest technologies. We, too, use this on a daily basis. For example, most of the times we code a website we start with the markup and then apply an external CSS file where we add all the styling. That is Progressive Enhancement in the practice.
Both technologies usually go hand in hand and have been part of the ways we do things for years. It’s just the terms that are not that well-known. And now, both of these practices need to evolve due to the new languages that are approaching. If you want to go deeper into both of these terms, check a related article on accessites.org.


#Displaying List

The quickest way to display a list on a single line is to give the <li> elements a display property value of **inline** or **inline-block**. Doing so places all the <li> elements within a single line, with a single space between each list item.

More often than not, we’ll use the inline-block property value rather than the inline property value. The inline-block property value allows us to easily add vertical margins and other spacing to the <li> elements, whereas the inline property value does not.

When changing the display property value to inline or inline-block, the list item marker, be it a bullet, number, or other style, is removed.



#Floating List

Changing the display property value to inline or inline-block is quick; however, it removes the list item marker. If the list item marker is needed, floating each <li> element is a better option than changing the display property.

Setting all <li> elements’ **float** property to left will horizontally align all <li> elements directly next to each other without any space between them. When we float each <li> element, the list item marker is displayed by default and will actually sit on top of the <li> element next to it. To prevent the list item marker from being displayed on top of other <li> elements, a horizontal margin or padding should be added.

As when floating any element, this breaks the flow of the page. We must remember to clear our floats—most commonly with the clearfix technique—and return the page back to its normal flow. With clear both.

**Display**

A value of **inline** will make that element an inline-level element.

The **inline-block** value. Using this value will allow an element to behave as a block-level element, accepting all box model properties. However, the element will be displayed in line with other elements, and it will not begin on a new line by default.

Value of **none** will completely hide an element and render the page as if that element doesn’t exist. Any elements nested within this element will also be hidden.

**Box Sizing**

box-sizing property, which allows us to change exactly how the box model works and how an element’s size is calculated. The property accepts three primary values: **content-box**, **padding-box**, and **border-box** each of which has a slightly different impact on how the box size is calculated.

#FLOAT

float property is used on multiple elements at the same time, it provides the ability to create a layout by floating elements directly next to or opposite each other, as seen in multiple-column layouts.

The float property accepts a few values; the two most popular values are left and right, which allow elements to be floated to the left or right of their parent element.

```img {
  float: left;
}
```

For reference, when an element is floated, it will float all the way to the edge of its parent element. If there isn’t a parent element, the floated element will then float all the way to the edge of the page.

When we float an element, we take it out of the normal flow of the HTML document. This causes the width of that element to default to the width of the content within it. Sometimes, such as when we’re creating columns for a reusable layout, this behavior is not desired. It can be corrected by adding a fixed width property value to each column. Additionally, to prevent floated elements from touching one another, causing the content of one to sit directly next to the content of the other, we can use the margin property to create space between elements.

Here, we are extending the previous code block, adding a margin and width to each column to better shape our desired outcome.


```section {
  float: left;
  margin: 0 1.5%;
  width: 63%;
}
aside {
  float: right;
  margin: 0 1.5%;
  width: 30%;
}
```

To prevent content from wrapping around floated elements, we need to clear, or contain, those floats and return the page to its normal flow. We’ll proceed by looking at how to clear floats, and then we’ll take a look at how to contain floats.

**Clearing Floats**

Clearing floats is accomplished using the clear property, which accepts a few different values: the most commonly used values being left, right, and **both**


**Position property**

The position property identifies how an element is positioned on a page and whether or not it will appear within the normal flow of a document. This is used in conjunction with the box offset properties—top, right, bottom, and left—which identify exactly where an element will be positioned by moving elements in a number of different directions.

By default every element has a position value of **static**, which means that it exists in the normal flow of a document and it doesn’t accept any box offset properties. The static value is most commonly overwritten with a **relative** or **absolute** value, which we’ll examine next.

The **relative** value for the position property allows elements to appear within the normal flow a page, leaving space for an element as intended while not allowing other elements to flow around it; however, it also allows an element’s display position to be modified with the box offset properties.
When we position the element using the box offset properties, the element overlaps the element below it rather than moving that element down as the margin or padding properties would.

```div {
  height: 100px;
  width: 100px;
}
.offset {
  left: 20px;
  position: relative;
  top: 20px;
}
```


The **absolute** value for the position property is different from the relative value in that an element with a position value of absolute will not appear within the normal flow of a document, and the original space and position of the absolutely positioned element will not be preserved.

Additionally, absolutely positioned elements are moved in relation to their closest relatively positioned parent element. Should a relatively positioned parent element not exist, the absolutely positioned element will be positioned in relation to the <body> element.

```section {
  position: relative;
}
div {
  position: absolute;
  right: 20px;
  top: 20px;
}
```

With relatively positioned elements, the box offset properties identify in which direction an element would be moved in relation to itself. With absolutely positioned elements, the box offset properties identify in which direction an element will be moved in relation to its closest relatively positioned parent element.


1. position:static
The default positioning for all elements is position:static, which means the element is not positioned and occurs where it normally would in the document.
Normally you wouldn't specify this unless you needed to override a positioning that had been previously set.

```#div-1 {
 position:static;
}
```

2. position:relative
If you specify position:relative, then you can use top or bottom, and left or right to move the element relative to where it would normally occur in the document.

```#div-1 {
 position:relative;
 top:20px;
 left:-40px;
}
```

div-1 still occupies that original space in the document, even though we have moved it.

3. position:absolute
When you specify position:absolute, the element is removed from the document and placed exactly where you tell it to go.



#Responsive

Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop.

Responsive web design is broken down into three main components, including **flexible layouts**, **media queries**, and **flexible media**.

**Flexible layouts**

Is the practice of building the layout of a website with a flexible grid, capable of dynamically resizing to any width. Flexible grids are built using relative length units, most commonly percentages or em units. These relative lengths are then used to declare common grid property values such as width, margin, or padding.

**Flexible Grid**

The formula is based around taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element.

     **target ÷ context = result**


The goal is to have have the section on the left and the aside on the right, with equal margins between the two.Normally the markup and styles for this layout would look a bit like the following.

Html

```<div class="container">
  <section>...</section>
  <aside>...</aside>
</div>
```

css

```.container {
  width: 538px;
}
section,
aside {
  margin: 10px;
}
section {
  float: left;
  width: 340px;
}
aside {
  float: right;
  width: 158px;
}
```

Using the flexible grid formula we can take all of the fixed units of length and turn them into relative units. In this example we’ll use percentages but em units would work equally as well. Notice, no matter how wide the parent container becomes, the section and aside margins and widths scale proportionally.


```.container {
}
section,
aside {
  margin: 1.858736059%; /*  10px ÷ 538px = .018587361 */
}
section {
  float: left;
  width: 63.197026%;    /* 340px ÷ 538px = .63197026 */   
}
aside {
  float: right;
  width: 29.3680297%;  /* 158px ÷ 538px = .293680297 */
}
```


#Media Queries**

Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example.


**Initializing Media Queries**

There are a couple different ways to use media queries, using the @media rule inside of an existing style sheet, importing a new style sheet using the @import rule, or by linking to a separate style sheet from within the HTML document. Generally speaking it is recommend to use the @media rule inside of an existing style sheet to avoid any additional HTTP requests.

HTML
<!-- Separate CSS File -->
<link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">

CSS
/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}

Each media query may include a media type followed by one or more expressions. Common media types include all, screen, print, tv, and braille. The HTML5 specification includes new media types, even including 3d-glasses.

**Logical Operators**: **and**, **not**, and **only**.

``@media all and (min-width: 800px) and (max-width: 1024px) {...}``

``@media not screen and (color) {...}``

``@media only screen and (orientation: portrait) {...}``

**Media Features** 

```@media all and (min-width: 320px) and (max-width: 780px) {...}

@media all and (orientation: landscape) {...}

@media all and (min-device-aspect-ratio: 16/9) {...}

@media only screen and (-webkit-min-device-pixel-ratio: 1.3), only screen and (min-device-pixel-ratio: 1.3) {...}

@media print and (min-resolution: 300dpi) {...}
```

Ex:

```@media all and (max-width: 420px) {
  section, aside {
    float: none;
    width: auto;
  }
}
```

**Mobile First**

The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.

A breakout of mobile first media queries might look at bit like the following.

```/* Default styles first then media queries */
@media screen and (min-width: 400px)  {...}
@media screen and (min-width: 600px)  {...}
@media screen and (min-width: 1000px) {...}
@media screen and (min-width: 1400px) {...}
```

```/* Default media */
body {
  background: #ddd;
}
/* Media for larger devices */
@media screen and (min-width: 800px) {
  body {
    background-image: url("bg.png") 50% 50% no-repeat;
  }
}
```


**Viewport** meta tag

use a little assistance though, particularly around identifying the viewport size, scale, and resolution of a website

**Viewport Height & Width**

``<meta name="viewport" content="width=device-width">``

**Viewport Scale**

``<meta name="viewport" content="initial-scale=2">``

**Viewport Resolution**

``<meta name="viewport" content="target-densitydpi=device-dpi">``

**Combining Viewport Values**

``<meta name="viewport" content="width=device-width, initial-scale=1">``

In CSS

```@viewport {
  width: device-width;
  zoom: 1;
}
```


**Flexible Media**

One quick way to make media scalable is by using the max-width property with a value of 100%. Doing so ensures that as the viewport gets smaller any media will scale down according to its containers width.

```img, video, canvas {
  max-width: 100%;
}
```


**Flexible Embedded Media**

HTML

```<figure>
  <iframe src="https://www.youtube.com/embed/4Fqg43ozz7A"></iframe>
</figure>
```

CSS

```figure {
  height: 0;
  padding-bottom: 56.25%; /* 16:9 */
  position: relative;
  width: 100%;
}
iframe {
  height: 100%;
  left: 0;
  position: absolute;
  top: 0;
  width: 100%;
}
```


#FLEXBOX

The Flexbox Layout (Flexible Box) module (currently a W3C Last Call Working Draft) aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and/or dynamic (thus the word "flex").

The main idea behind the flex layout is to give the container the ability to alter its items' width/height (and order) to best fill the available space (mostly to accommodate to all kind of display devices and screen sizes). A flex container expands items to fill available free space, or shrinks them to prevent overflow.

Most importantly, the flexbox layout is direction-agnostic as opposed to the regular layouts (block which is vertically-based and inline which is horizontally-based). While those work well for pages, they lack flexibility (no pun intended) to support large or complex applications (especially when it comes to orientation changing, resizing, stretching, shrinking, etc.).

Note: Flexbox layout is most appropriate to the components of an application, and small-scale layouts, while the Grid layout is intended for larger scale layouts.

**Properties for the Parent (flex container)**

**display**

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```.container {
  display: flex; /* or inline-flex */
}
```

**flex-direction**

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

row (default): left to right in ltr; right to left in rtl
row-reverse: right to left in ltr; left to right in rtl
column: same as row but top to bottom
column-reverse: same as row-reverse but bottom to top

**flex-wrap**

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property. Direction also plays a role here, determining the direction new lines are stacked in.

```.container{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

nowrap (default): single-line / left to right in ltr; right to left in rtl
wrap: multi-line / left to right in ltr; right to left in rtl
wrap-reverse: multi-line / right to left in ltr; left to right in rtl

**flex-flow** (Applies to: parent flex container element)

This is a shorthand flex-direction and flex-wrap properties, which together define the flex container's main and cross axes. Default is row nowrap.

``flex-flow: <‘flex-direction’> || <‘flex-wrap’``

**justify-content**

This defines the alignment along the main axis. It helps distribute extra free space left over when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

```.container {
  justify-content: flex-start | flex-end | center | space-between | space-around;
}
```

flex-start (default): items are packed toward the start line
flex-end: items are packed toward to end line
center: items are centered along the line
space-between: items are evenly distributed in the line; first item is on the start line, last item on the end line
space-around: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren't equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.

**align-items**

This defines the default behaviour for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross-axis (perpendicular to the main-axis).

```.container {
  align-items: flex-start | flex-end | center | baseline | stretch;
}
```

flex-start: cross-start margin edge of the items is placed on the cross-start line
flex-end: cross-end margin edge of the items is placed on the cross-end line
center: items are centered in the cross-axis
baseline: items are aligned such as their baselines align
stretch (default): stretch to fill the container (still respect min-width/max-width)

**align-content**

This aligns a flex container's lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.

Note: this property has no effect when there is only one line of flex items.

```.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

flex-start: lines packed to the start of the container
flex-end: lines packed to the end of the container
center: lines packed to the center of the container
space-between: lines evenly distributed; the first line is at the start of the container while the last one is at the end
space-around: lines evenly distributed with equal space around each line
stretch (default): lines stretch to take up the remaining space


**Properties for the Children (flex items)**

**order**

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

```.item {
  order: <integer>;
}
```

**flex-grow**

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).

```.item {
  flex-grow: <number>; /* default 0 */
}
```

Negative numbers are invalid.

**flex-shrink**

This defines the ability for a flex item to shrink if necessary.

```.item {
  flex-shrink: <number>; /* default 1 */
}
```

Negative numbers are invalid.

**flex-basis**

This defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The auto keyword means "look at my width or height property" (which was temporarily done by the main-size keyword until deprecated). The content keyword means "size it based on the item's content" - this keyword isn't well supported yet, so it's hard to test and harder to know what its brethren max-content, min-content, and fit-content do.

```.item {
  flex-basis: <length> | auto; /* default auto */
}
```

If set to 0, the extra space around content isn't factored in. If set to auto, the extra space is distributed based on its flex-grow value.

**flex**

This is the shorthand for flex-grow, flex-shrink and flex-basis combined. The second and third parameters (flex-shrink and flex-basis) are optional. Default is 0 1 auto.

```.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

It is recommended that you use this shorthand property rather than set the individual properties. The short hand sets the other values intelligently.

**align-self**

This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

Please see the align-items explanation to understand the available values.

```.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

Note that float, clear and vertical-align have no effect on a flex item.

[Datasheet] (http://apps.workflower.fi/css-cheats/?name=flexbox)

.container {
display: flex;
display: inline-flex;
flex-direction: row;
flex-direction: row-reverse;
flex-direction: column;
flex-direction: column-reverse;
flex-wrap: nowrap;
flex-wrap: wrap;
flex-wrap: wrap-reverse;
justify-content: flex-start;
justify-content: center;
justify-content: flex-end;
justify-content: space-between;
justify-content: space-around;
align-items: flex-start;
align-items: center;
align-items: flex-end;
align-items: stretch;
align-items: baseline;
align-content: flex-start;
align-content: center;
align-content: flex-end;
align-content: space-between;
align-content: space-around;
align-content: stretch;
}

.item {
order: 0;
flex-grow: 0;
flex-grow: 1;
flex-shrink: 0;
flex-shrink: 1;
flex-basis: auto;
align-self: auto;
align-self: flex-start;
align-self: center;
align-self: flex-end;
align-self: baseline;
align-self: stretch;
}


#EFFECTS & ANIMATION

**@font-face**

Allows the use of online fonts.

```@font-face {
  font-family: "FontName";//1
  src: url('fontfile.eot');//2
  src: url('fontfile.eot?iefix') format('eot'),//3
  url('fontfile.svg#FontName') format('svg'),//4
  url('fontfile.ttf') format('truetype'),//5
  url('fontfile.woff') format('woff');//6
}
```

1 The name of the font for the further usage in the stylesheet at the font-family property. If the font should be assigned to all <h2> headlines for example you have to write h2 { font-family: "FontName", sans-serif }. Can be choosen freely.

2 Optional. The eot fontfile. Can be omitted if you don`t want to support Internet Explorer prior to version 9 (including semicolon).

3 Optional. Can also be omitted for Internet Explorer < 9. ?iefix prevents IE6 from interpreting all of the following. If the whole IE family (6 to 9) should be supported, 2 and 3 are needed.

4 Optional. Can be omitted if iPad versions prior to iOS 4.2 shouldn’t be supported. FontName is the same as at 1.

5 The ttf fontfile. Necessary to support (Mobile) Safari and Opera.

6 The woff fontfile for all modern browsers (best choice).

**text-overflow**

Controls how text is displayed when it is longer than its containing area.

``text-overflow: clip``

The default behavior of words within a text paragraph, which are longer than its container. They simply overflow its boundaries. This is closely related to the overflow property. As soon as it is set to hidden, the text gets clipped, at auto the container becomes scrollable until the end of the text is reached.

``text-overflow: ellipsis`

As soon as overflow is set to hidden longer words get clipped at the end and abbreviated with the ellipsis character. Only works in combination with the mentioned overflow value.

**overflow-wrap**

Enables words to wrap even if they are longer than their container.

``overflow-wrap: normal`

The default behaviour of a word that has no positions to wrap (space or slash) and is longer than its container is to simply overflow it.

Wrapping enabled

``overflow-wrap: break-word``

Now the word doesn’t overflow the container but rather breaks as soon as it reaches its boundaries.

**box-shadow**

Is used to assign one or more shadows to an element.

Multiple shadows can be assinged comma separated.

``box-shadow: inset 4px 4px 16px 10px #000``

Lets see the 6 parameters:

1 Optional. When set the shadow is drawn inside the element and will be no drop shadow. When both the offset values are positive the shadow runs from top left to bottom right. When negative it starts at the bottom right corner (not depicted).

2 The horizontal offset of the shadow (x-axis). If positive the shadow is drawn to the right side of the element, if negative it is drawn to the left side.

3 The vertical offset of the shadow (y-axis). If positive the shadow is drawn below the element, if negative it is drawn above.

4 Optional. The blur radius defines how big and how much blurred the shadow is. The larger this value, the lighter the shadow. Negative values are not allowed. If not set the shadow’s edges are sharp (which corresponds to a value of 0).

5 Optional. The spread distance makes the shadow bigger in all directions. The shadow is expanded by the given value. Negative values cause the shadow to contract (not depicted).

6 The color of the shadow. rgba/hsla color values are possible.

**text-shadow**
Is used to assign one or more shadows to text.

Multiple shadows can be assinged comma separated.

text-shadow: 4px 4px 14px #969696

Lets see the 4 parameters:

1 The horizontal offset of the shadow (x-axis). If positive the shadow is drawn to the right side of the text, if negative it is drawn to the left side.

2 The vertical offset of the shadow (y-axis). If positive the shadow is below the text, if negative it is drawn above.

3 Optional. The blur radius defines how big and how much blurred the shadow is. The larger this value, the lighter the shadow. Negative values are not allowed. If not set the shadow’s edges are sharp (which corresponds to a value of 0).

4 The color of the shadow. rgba/hsla color values are possible.

**border-radius**
Is used to round the corners of an element that has the border or background property set.

``border-radius: 8px / 13px``

1 The radius of the quarter circles that form the shapes of the corners.
2(Optional, separated by a slash) The vertical radius, which results in a quarter ellipse when different from the horizontal radius.

Four values given

``border-radius: 8px 13px 10px 5px``

1 Top left corner.
2 Top right corner.
3 Bottom right corner.
4 Bottom left corner.

Three values given

``border-radius: 8px 13px 5px``

1 Top left corner.
2 Top right AND bottom left corner.
3 Bottom right corner.

Two values given

``border-radius: 8px 13px``

1 Top left AND bottom right corner.
2 Top right AND bottom left corner

One value given

``border-radius: 8px``

1 All four corners rounded equally.

Elliptical corners, two values given

With the addition of a slash it is possible to set the horizontal and vertical radii separately.

``border-radius: 8px / 13px``

1 All horizontal radii set equally.
2 All vertical radii set equally

Elliptical corners, four values given

Three and four values on each side of the slash follow the notation given above (without slash).

border-radius: 8px 13px / 10px 5px

1 Horizontal radii for top left AND bottom right corners.
2 Horizontal radii for top right AND bottom left corners.
3 Vertical radii for top left AND bottom right corners.
4 Vertical radii for top right AND bottom left corners.

**opacity**
Sets the transparency of an element, that is how much the background shines through. In contrast to rgba it changes the transparency of the whole element instead of just the color.

opacity: 0.1

1 Sets the element to an opacity of 0.1 (10%). 0 stands for fully transparent and 1 for opaque (solid). The zero before the comma can be omitted.


**Filters**

This is a new feature that can be used on both HTML elements and images, but I think it's best used on images and can create nice effects on image galleries.

The value of the property can be either decimal or percentage. 100% or 1.0 will make the image full greyscaled, 0% or 0 will add no effect of greyscale to the image. Someone could be in pixels as blur, or a degree values as hue rotate

.grayscale {
    -webkit-filter: grayscale(1);
    filter: grayscale(1);
}

.sepia {
    -webkit-filter: sepia(1);
    filter: sepia(1);
}

.saturate {
    -webkit-filter: saturate(4);
    filter: saturate(4);
}

.hue-rotate {
    -webkit-filter: hue-rotate(90deg);
    filter: hue-rotate(90deg);
}

.invert {
    -webkit-filter: invert(.8);
    filter: invert(.8);
}

.opacity {
    -webkit-filter: opacity(.5);
    filter: opacity(.5);
}

.brightness {
    -webkit-filter: brightness(.5);
    filter: brightness(.5);
}

.contrast {
    -webkit-filter: contrast(3);
    filter: contrast(3);
}

.blur {
    -webkit-filter: blur(5px);
    filter: blur(5px);
}

.tint { // sepia + hue-rotate
    -webkit-filter: sepia(1) hue-rotate(200deg);
    filter: sepia(1) hue-rotate(200deg);
}

.multiple-filters { //saturation + sepia
    -webkit-filter: contrast(1.4) saturate(1.8) sepia(.6);
    filter: contrast(1.4) saturate(1.8) sepia(.6);
}

.inkwell { //instagram-ish
    -webkit-filter: grayscale(1) brightness(0.45) contrast(1.05);
    filter: grayscale(1) brightness(0.45) contrast(1.05);
}





