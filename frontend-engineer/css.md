# CSS
Cascading Style Sheets (CSS) is a style sheet language used for describing the look and formatting of a document written in a markup language. Although most often used to change the style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any kind of XML document, including plain XML, SVG and XUL. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.
At its most basic level, CSS consists of two building blocks:
- Properties: Human-readable identifiers that indicate which stylistic features (e.g. font, width, background color) you want to change.
- Values: Each specified property is given a value, which indicates how you want to change those stylistic features (e.g. what you want to change the font, width or background color to.)

A property paired with a value is called a CSS declaration. CSS declarations are put within CSS Declaration Blocks. And finally, CSS declaration blocks are paired with selectors to produce CSS Rulesets (or CSS Rules).

An element may be matched by several selectors, therefore several rules may set a given property multiple times. CSS defines which one has precedence over the others and must be applied: this is called the cascade algorithm.

## Simple selectors 

### Type selector
`A`: Selects all elements of type A. Type refers to the type of tag, so div, p and ul are all different element types.

### ID selector
`#id`: Selects the element with a specific id. You can also combine the ID selector with the type selector.

### Class selector
`.classname`: The class selector selects all elements with that class attribute. Elements can only have one ID, but many classes.

`A.className`: You can combine the class selector with other selectors, like the type selector.

### Universal selector
`*`: It allows selecting all elements in a page.
`A  *`: This selects all elements inside of A.

## Combinators

### Descendant Combinator (space)
`A B`: Selects all B inside of A. B is called a descendant because it is inside of another element.

### Comma Combinator
`A, B`: Selects all A and B elements. You can combine any selectors this way, and you can specify more than two.

### Adjacent Sibling Selector
`A + B`: This selects all B elements that directly follow A. Elements that follow one another are called siblings. They're on the same level, or depth.

### General Sibling Selector
`A ~ B`: You can select all siblings of an element that follow it. This is like the Adjacent Selector (A + B) except it gets all of the following elements instead of one.

### Child Selector
`A > B`: You can select elements that are direct children of other elements. A child element is any element that is nested directly in another element.

## Pseudo-classes

### First Child Pseudo-selector
`:first-child`: You can select the first child element. A child element is any element that is directly nested in another element. You can combine this pseudo-selector with other selectors.

### Only Child Pseudo-selector
`:only-child`: You can select any element that is the only element inside of another one.

### Last Child Pseudo-selector
`:last-child`: You can use this selector to select an element that is the last child element inside of another element.

### Nth Child Pseudo-selector
`A:nth-child(n)`: Selects the n-th (Ex: 1st, 3rd, 12th etc.) child element in A element.

### Nth Last Child Pseudo-selector
`A:nth-last-child(n)`: Selects the n-th (Ex: 1st, 3rd, 12th etc.) child element in A element starting from the bottom.

### First of Type Selector
`:first-of-type`: Selects the first element of that type within another element.

### Nth of Type Selector
`:nth-of-type(A)`: Selects a specific element based on its type and order in another element - or even or odd instances of that element.

`div:nth-of-type(2)`: selects the second instance of a div.

`.example:nth-of-type(odd)`: selects all odd instances of a the example class.

`span:nth-of-type(6n+2)`: selects every 6th instance of a span, starting from (and including) the second instance.

### Only of Type Selector
`:only-of-type`: Selects the only element of its type within another element.

### Last of Type Selector
`:last-of-type`: Selects each last element of that type within another element. Remember type refers the kind of tag, so p and span are different types. 

`div:last-of-type`: selects the last div in every element.

### Empty Selector
`:empty`: Selects elements that don't have any other elements inside of them.

### Negation Selector
`:not(X)`: Select all elements that do not match selector "X".

## Attribute selectors

### Attribute Selector
`[attribute]`: Select all elements that have a specific attribute

### Attribute Value Selector
`[attribute="value"]`: Select all elements that have a specific attribute value

### Attribute Starts With Selector
`[attribute^="value"]`: Select all elements with an attribute value that starts with specific characters

### Attribute Ends With Selector
`[attribute$="value"]`: Select all elements with an attribute value that ends with specific characters

### Attribute Wildcard Selector
`[attribute*="value"]`: Select all elements with an attribute value that contains specific characters anywhere

### Attribute ? Selector
`[attribute~="value"]`: Select all elements with an attribute value that it is a whitespace-separated list of words and one of which is exactly "value".

### Attribute ? Selector
`[attribute|="value"]`: Select all elements with an attribute value that can be exactly “value” or can begin with “value” immediately followed by “-” (U+002D). It can be used for language subcode matches

## Pseudo elements
Pseudo-elements are very much like pseudo-classes, but they have differences. They are keywords (this time preceded by two colons (::)) that can be added to the end of selectors to select a certain part of an element. They are:
- ::after
- ::before
- ::first-letter
- ::first-line
- ::selection
- ::backdrop

## CSS statements
CSS Rules are the main building blocks of a style sheet — the most common block you'll see in CSS. But there are other types of block that you'll come across occasionally — CSS rules are one type of so-called CSS statements. An at-rule is a CSS statement beginning with an at sign, '@' (U+0040 COMMERCIAL AT), followed by an identifier and includes everything up to the next semi-colon, ';' (U+003B SEMICOLON), or the next CSS block, whichever comes first.

There are several at-rules, designated by their identifiers, each with a different syntax:
- @charset: Defines the character set used by the style sheet.
- @import: Tells the CSS engine to include an external style sheet.
- @namespace: Tells the CSS engine that all its content must be considered prefixed with an XML namespace.
- Nested at-rules: A subset of nested statements, which can be used as a statement of a style sheet as well as inside of conditional group rules:
  - @media: A conditional group rule which will apply its content if the device meets the criteria of the condition defined using a media query.
  - @supports: A conditional group rule which will apply its content if the browser meets the criteria of the given condition.
  - @document: A conditional group rule which will apply its content if the document in which the style sheet is applied meets the criteria of the given condition. (deferred to Level 4 of CSS Spec)
  - @page: Describes the aspect of layout changes which will be applied when printing the document.
  - @font-face: Describes the aspect of an external font to be downloaded.
  - @keyframes: Describes the aspect of intermediate steps in a CSS animation sequence.
  - @viewport: Describes the aspects of the viewport for small screen devices.

One example:
```css
@media (min-width: 801px) {
  body {
    margin: 0 auto;
    width: 800px;
  }
}
```

### import
The @import CSS at-rule is used to import style rules from other style sheets. These rules must precede all other types of rules, except @charset rules; as it is not a nested statement, @import cannot be used inside conditional group at-rules.

### charset
The @charset CSS at-rule specifies the character encoding used in the style sheet. It must be the first element in the style sheet and not be preceded by any character; as it is not a nested statement, it cannot be used inside conditional group at-rules. If several @charset at-rules are defined, only the first one is used, and it cannot be used inside a style attribute on an HTML element or inside the <style> element where the character set of the HTML page is relevant.
This at-rule is useful when using non-ASCII characters in some CSS properties, like content.
As there are several ways to define the character encoding of a style sheet, the browser will try the following methods in the following order (and stop as soon as one yields a result) :
- The value of the Unicode byte-order character placed at the beginning of the file.
- The value given by the charset attribute of the Content-Type: HTTP header or the equivalent in the protocol used to serve the style sheet.
- The @charset CSS at-rule.
- Use the character encoding defined by the referring document: the charset attribute of the <link> element. This method is obsoleted in HTML5 and must not be used.
- Assume that the document is UTF-8

### Conditional Group Rules
Much like the values of properties, each at-rule has a different syntax. Nevertheless, several of them can be grouped into a special category named conditional group rules. These statements share a common syntax and each of them can include nested statements—either rulesets or nested at-rules. Furthermore, they all convey a common semantic meaning—they all link some type of condition, which at any time evaluates to either true or false. If the condition evaluates to true, then all of the statements within the group will be applied.

## Cascade algorithm
Its most basic level it indicates that the order of CSS rules matter, but it's more complex than that. What selectors win out in the cascade depends on three factors (these are listed in order of weight — earlier ones will overrule later ones):
- Importance: In CSS, there is a special piece of syntax you can use to make sure that a certain rule will always win over all others: !important. Adding this to the end of a property value will give it superpowers.
- Specificity: Specificity is basically a measure of how specific a selector is and how many elements it could match
- Source order: As mentioned above, if multiple competing selectors have the same importance and specificity, the third factor that comes into play to help decide which rule wins is source order, later rules will win over earlier rules.

## Units
- Pixels (px) are referred to as absolute units because they will always be the same size regardless of any other related settings.
- em: 1em is the same as the font-size of the current element (more specifically, the width of a capital letter M.) The default base font-size given to web pages by web browsers before CSS styling is applied is 16 pixels, which means the computed value of 1em is 16 pixels for an element by default. But beware — font sizes are inherited by elements from their parents, so if different font sizes have been set on parent elements, the pixel equivalent of an em can start to become complicated.
- ex, ch: Respectively these are the height of a lower case x, and the width of the number 0. These are not as commonly used or well-supported as ems.
- rem: The rem (root em) works in exactly the same way as the em, except that it will always equal the size of the default base font-size; inherited font sizes will have no effect, so this sounds like a much better option than ems, although rems don't work in older versions of Internet Explorer (see more about cross-browser support in Debugging CSS.)
- vw, vh: Respectively these are 1/100th of the width of the viewport, and 1/100th of the height of the viewport. Again, these are not as widely supported as rems.

## Box model
Every element within a document is structured as a rectangular box inside the document layout, the size and "onion layers" of which can be tweaked using some specific CSS properties. The relevant properties are as follows:
- The *width* and *height* properties set the width and height of the content box, which is the area in which the content of the box is displayed — this content includes both text content sat inside the box, and other boxes representing nested child elements.
  - Note: Other properties exist that allow more subtle ways of handling content box size — setting size constraints rather than an absolute size. This can be done with the properties min-width, max-width, min-height, and max-height.
- *Padding* refers to the inner margin of a CSS box — between the outer edge of the content box and the inner edge of the border. The size of this layer can be set on all four sides at once with the padding shorthand property, or one side at a time with the padding-top, padding-right, padding-bottom and padding-left properties.
- The *border* of a CSS box sits between the outer edge of the padding and the inner edge of the margin. By default the border has a size of 0 — making it invisible — but you can set the thickness, style and color of the border to make it appear. The border shorthand property allows you to set all of these on all four sides at once, for example border: 1px solid black.
- The *margin* surrounds a CSS box, and pushes up against other CSS boxes in the layout. It behaves rather like padding; the shorthand property is margin and the individual properties are margin-top, margin-right, margin-bottom, and margin-left.

![](https://internetingishard.com/html-and-css/css-box-model/css-box-model-73a525.png)

### Changing box behavior
We can override the default box type of HTML elements with the CSS display property. For example, if we wanted to make our `<em>` and `<strong>` elements blocks instead of inline elements, we could:

```css
em, strong {
  background-color: #B2D6FF;
  display: block;
}
```

or we can set `display: inline` for other block elements.

### Margin vs padding
Margins and padding can accomplish the same thing in a lot of situations, making it difficult to determine which one is the “right” choice. The most common reasons why you would pick one over the other are:
* The padding of a box has a background, while margins are always transparent.
* Padding is included in the click area of an element, while margins aren’t.
* Margins collapse vertically, while padding doesn’t.
If none of these help you decide whether to use padding over margin, then don’t fret about it—just pick one. In CSS, there’s often more than one way to solve your problem.

### Margin of inline elements
One of the starkest contrasts between block-level elements and inline ones is their handling of margins. Inline boxes completely ignore the top and bottom margins of an element.
The rationale behind this goes back to the fact that inline boxes format runs of text inside of a block, and thus have limited impact on the overall layout of a page. If you want to play with the vertical space of a page, you must be working with block-level elements.

### Vertical margin collapse
Another quirk of the CSS box model is the “vertical margin collapse”. When you have two boxes with vertical margins sitting right next to each other, they will collapse. Instead of adding the margins together like you might expect, only the biggest one is displayed. To prevent this all you need to do is put another invisible element in between them.

## Specificity
The selector specificity is defined by the CSS2 specification as follows:

- count 1 if the declaration it is from is a 'style' attribute rather than a rule with a selector, 0 otherwise (= a)
- count the number of ID attributes in the selector (= b)
- count the number of other attributes and pseudo-classes in the selector (= c)
- count the number of element names and pseudo-elements in the selector (= d)
- Concatenating the four numbers a-b-c-d (in a number system with a large base) gives the specificity.
- The number base you need to use is defined by the highest count you have in one of the categories. 
- For example, if a=14 you can use hexadecimal base. In the unlikely case where a=17 you will need a 17 digits number base. The later situation can happen with a selector like this: html body div div p ... (17 tags in your selector.. not very likely).

Some examples:
```css
 *             {}  /* a=0 b=0 c=0 d=0 -> specificity = 0,0,0,0 */
 li            {}  /* a=0 b=0 c=0 d=1 -> specificity = 0,0,0,1 */
 li:first-line {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
 ul li         {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
 ul ol+li      {}  /* a=0 b=0 c=0 d=3 -> specificity = 0,0,0,3 */
 h1 + *[rel=up]{}  /* a=0 b=0 c=1 d=1 -> specificity = 0,0,1,1 */
 ul ol li.red  {}  /* a=0 b=0 c=1 d=3 -> specificity = 0,0,1,3 */
 li.red.level  {}  /* a=0 b=0 c=2 d=1 -> specificity = 0,0,2,1 */
 #x34y         {}  /* a=0 b=1 c=0 d=0 -> specificity = 0,1,0,0 */
 style=""          /* a=1 b=0 c=0 d=0 -> specificity = 1,0,0,0 */
```

### Sorting the rules

After the rules are matched, they are sorted according to the cascade rules. WebKit uses bubble sort for small lists and merge sort for big ones. WebKit implements sorting by overriding the ">" operator for the rules:

```c
static bool operator >(CSSRuleData& r1, CSSRuleData& r2)
{
    int spec1 = r1.selector()->specificity();
    int spec2 = r2.selector()->specificity();
    return (spec1 == spec2) : r1.position() > r2.position() : spec1 > spec2;
}
```

# Float
Tere are `left`, `right` and `none` for `float`. Each value indicates how an element should float. When `float` is set, each element will get out of its normal flow and will be shifted to the specified direction, until it gets its container or another floated element. Float affects not only the target element, but also its children.

## Floating an element
The CSS float property gives us control over the horizontal position of an element. By “floating” the sidebar to the left, we’re telling the browser to align it to the left side of the page.
However, this doesn’t just align the sidebar—it also tells surrounding elements that they can flow around the sidebar instead of beginning underneath it.

## Clearing floats
“Clearing” a float is when we tell a block to ignore any floats that appear before it. Instead of flowing around the floated box, a cleared element always appears after any floats. It’s like forcing a box back into the default vertical flow of the page.

# Flexbox
The “Flexible Box” or “Flexbox” layout mode offers an alternative to Floats for defining the overall appearance of a web page. Whereas floats only let us horizontally position our boxes, flexbox gives us complete control over the alignment, direction, order, and size of our boxes.

Flexbox uses two types of boxes that we’ve never seen before: “flex containers” and “flex items”. The job of a flex container is to group a bunch of flex items together and define how they’re positioned.

![](https://internetingishard.com/html-and-css/flexbox/flex-container-and-flex-items-6234bb.png)

Every HTML element that’s a direct child of a flex container is an “item”. Flex items can be manipulated individually, but for the most part, it’s up to the container to determine their layout. The main purpose of flex items are to let their container know how many things it needs to position.

As with float-based layouts, defining complex web pages with flexbox is all about nesting boxes. You align a bunch of flex items inside a container, and, in turn, those items can serve as flex containers for their own items. As you work through the examples in this chapter, remember that the fundamental task of laying out a page hasn’t changed: we’re still just moving a bunch of nested boxes around.

## Flex containers
By giving it a value of flex, we’re telling the browser that everything in the box should be rendered with flexbox instead of the default box model.
This enables the flexbox layout mode—without it, the browser would ignore all the flexbox properties that we’re about to introduce. Explicitly defining flex containers means that you can mix and match flexbox with other layout models.
Flex containers only know how to position elements that are one level deep (i.e., their child elements).

![](https://internetingishard.com/html-and-css/flexbox/enabling-flexbox-dd3b59.png)

## Aligning a flex item
After you’ve got a flex container, your next job is to define the horizontal alignment of its items. That’s what the justify-content property is for. The space-around value spreads its items out across its entire width. The space-between value is similar, but it only adds that extra space between items.

![](https://internetingishard.com/html-and-css/flexbox/flex-justify-content-alignment-ea129c.png)
![](https://internetingishard.com/html-and-css/flexbox/flex-justify-content-distribution-b0ee9c.png)

## Flex container direction
“Direction” refers to whether a container renders its items horizontally or vertically. So far, all the containers we’ve seen use the default horizontal direction, which means items are drawn one after another in the same row before popping down to the next column when they run out of space. By default `flex-direction` is `column`, but it can be `row`.
The `flex-direction` property also offers you control over the order in which items appear via the `row-reverse` and `column-reverse` properties.

![](https://internetingishard.com/html-and-css/flexbox/flex-direction-reverse-532d8f.png)

## Positioning schema
There are several schemas:
- Normal: the object is positioned according to its place in the document. This means its place in the render tree is like its place in the DOM tree and laid out according to its box type and dimensions
- Float: the object is first laid out like normal flow, then moved as far left or right as possible
- Absolute: The layout is defined exactly regardless of the normal flow. The object is put in the render tree in a different place than in the DOM tree
- Relative: the object is positioned like usual and then moved by the required delta
- Fixed: “Fixed positioning” has a lot in common with absolute positioning: it’s very manual, the element is removed from the normal flow of the page, and the coordinate system is relative to the entire browser window. The key difference is that fixed elements don’t scroll with the rest of the page.

The positioning scheme is set by the "position" property and the "float" attribute.
- static and relative cause a normal flow
- absolute and fixed cause absolute positioning

In static positioning no position is defined and the default positioning is used. In the other schemes, the author specifies the position: top, bottom, left, right.

The way the box is laid out is determined by:
- Box type
- Box dimensions
- Positioning scheme
- External information such as image size and the size of the screen

## Z-index
The z-index property lets you control the depth of elements on the page. If you think of your screen as 3D space, negative z-index values go farther into the page, and positive ones come out of the page.

![](https://internetingishard.com/html-and-css/advanced-positioning/css-z-index-c87ef0.png)

Say two DIVs with the same parent, higher z-index will be displayed. It will inherit the z-index property of the parent. Z-index only works on positioned elements (position:absolute, position:relative, or position:fixed). Value can be negative.

---
title: CSS flexbox
category: CSS
layout: 2017/sheet
updated: 2017-08-29
prism_languages: [css]
weight: -3
---

### Simple example

```css
.container {
  display: flex;
}
```

```css
.container > div {
  flex: 1 1 auto;
}
```

### Container

```css
.container {
```
{: .-setup}

```css
  display: flex;
  display: inline-flex;
```

```css
  flex-direction: row;            /* ltr - default */
  flex-direction: row-reverse;    /* rtl */
  flex-direction: column;         /* top-bottom */
  flex-direction: column-reverse; /* bottom-top */
```

```css
  flex-wrap: nowrap; /* one-line */
  flex-wrap: wrap;   /* multi-line */
```

```css
  align-items: flex-start; /* vertical-align to top */
  align-items: flex-end;   /* vertical-align to bottom */
  align-items: center;     /* vertical-align to center */
  align-items: stretch;    /* same height on all (default) */
```

```css
  justify-content: flex-start; /* horizontal alignment - default */
  justify-content: flex-end;
  justify-content: center;
```

```css
}
```
{: .-setup}

### Child

```css
.container > div {
```
{: .-setup}

```css
  /* This: */
  flex: 1 0 auto;

  /* Is equivalent to this: */
  flex-grow: 1;
  flex-shrink: 0;
  flex-basis: auto;
```

```css
  order: 1;
```

```css
  align-self: flex-start;  /* left */
  margin-left: auto;       /* right */
```

```css
}
```
{: .-setup}


## Tricks

### Vertical center

```css
.container {
  display: flex;
}

.container > div {
  width: 100px;
  height: 100px;
  margin: auto;
}
```

### Vertical center (2)

```css
.container {
  display: flex;
  align-items: center;     /* vertical */
  justify-content: center; /* horizontal */
}
```

### Reordering

```css
.container > .top {
 order: 1;
}

.container > .bottom {
 order: 2;
}
```

### Mobile layout


```css
.container {
  display: flex;
  flex-direction: column;
}

.container > .top {
  flex: 0 0 100px;
}

.container > .content {
  flex: 1 0 auto;
}
```

A fixed-height top bar and a dynamic-height content area.

### Table-like

```css
.container {
  display: flex;
}

/* the 'px' values here are just suggested percentages */
.container > .checkbox { flex: 1 0 20px; }
.container > .subject  { flex: 1 0 400px; }
.container > .date     { flex: 1 0 120px; }
```

This creates columns that have different widths, but size accordingly according
to the circumstances.

### Vertical


```css
.container {
  align-items: center;
}
```

Vertically-center all items.

### Left and right

```css
.menu > .left  { align-self: flex-start; }
.menu > .right { align-self: flex-end; }
```
- External information such as image size and the size of the screen
