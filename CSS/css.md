css-tricks.com/examples/HSLaExplorer

Not all properties are inherited - for example, `border` is not.

```css
body {
    font-size: 10px;
}

.thumbnail-title {
    display: block;
    margin: 0px;
    padding: 4px 10px:

    background: rgb(96, 125, 139);
    color: rgb(202, 238, 255);

    font-size: 18px;
}
```

* remove underlines by changing the `text-decoration` property for the anchor tags

* pair element selector with with an attribute selector:
```css
a[href="#"] {
    /* style decoration */
}
```
this selector would match only those anchor elements whose `href` attribute has a value of #

* You can use attribute selectors on their own:
```css
[href] {
    /* */
}
```

* favor class selectors over other kinds of selectors
* you can add multiple class names to an element
### Making images Fit the Window
You set the width to 100%, which constrains it to the width of its container.  This means that as you widen the browser window, the images get proportionally larger.

Images are `display: inline` by default.  They are subject to similar rendering rules text.  When text is rendered, the letters are drawn along a common baseline.  Some characters, such as p, q, and y, have a descender - the tail that drops below the baseline.  To accomodate them, there is some whitespace included below the baseline. 

Setting the display property to `block` removes the whitespace because there is not neeed to accomodate any text (or any other `display: inline` elements that might be rendered alongside the image).

### Color
For more capable browsers a fourth value can specify the opacity or transparency of the specified color, from 0.0 (fully transparent) to 1.0 (fully opaque).  The opacity is officially known as the alpha value - hence the A in RGBA.  The RGBA value of the body's background color is `(149, 194, 215, 1)`

### Relationship Selectors
* descendent selectors
* child selectors
* sibling selectors
* adjacent sibling selectors

Relationship selector syntax includes two selectors (like class or element selectors) joined by a symbol called a combinator that determines the targeted relationship between them.  
    * the browser reads selector syntax from right to left.

A descendent selector targets any element of one specified type that is the descendent of another specified type.  For example, to select any span element that is the descendent of the body element, the syntax would be:
```css
body span {
    /* style declaration */
}
```

Child selectors target elements of a specified type that are the immediate children of another specified element.  Child selector syntax uses the combinator >.  To use child selector syntax to target all the `spans`:
```css
li > span {
    /* */
}
```

Reading from right to left, this selector targets any `span` that is the immediate child of a `li` element.

Sibling selector syntax uses the combinator ~.  This syntax targets elements with the same parent.  

```css
header ~ ul {

}
```
This selector targets any ul that is preceded by a header with the same parent element.  

Adjacent sibling selector, targets elements that are immediately preceded by a sibling of the specified type.

```css
li + li {

}
```
This syntax would select all li elements immediately preceded by a sibling li.  The result is that the declared styles would be applied to the second through li- but not the first, because it is not immediately preceded by another li.

* `@font-face` - lets you give a custom name to a family of fonts that you can then use in the rest of your styles.
* [Snippets](https://flight-manual.atom.io/using-atom/sections/snippets/)

Class selectors and attribute selectors have the same degree of specificity, and both have a higher specificity than element selectors.  The highest degree of specificity goes to ID selectors.  If you give an element an `id` attribute, you can write an ID selector that is more specific than any other selector.

```css
<li class="thumbnail-item" id="barry-otter">
```
To use the ID in a selector, you prefix it with #:
```css
.thumbnail-item {
    background: blue;
}

#barry-otter {
    background: green;
}

li {
    background: red;
}
```
