# Specificity
* [How is specificity calculated?](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
Specificity is the means by which browsers decide which CSS property values are the most relevant to an element and, therefore, will be applied.  It is based on the matching rules which are composed of different sorts of CSS selectors.

* CSS rule: directly targeted elements will always take precedence over rules which an element inherits from its ancestor.

The following list of selector types increases by specificity:
* Type selectors (e.g., `h1`) and pseudo-elements (e.g., `::before`).
* Class selectors (e.g., `.example`), attributes selectors (e.g., [type="radio"]) and pseudo-classes (e.g., `:hover`).
* ID selectors (e.g., `#example`).

Universal selector (*), combinators (+, >, ~, ' ', ||) and negation pseudo-class (`:not()`) have no effect on specificity. (The selectors declared inside `:not()` do, however.)

Inline styles added to an element (e.g., `style="font-weight: bold;"`) always overwrite any styles in external stylesheets, and thus can be thought of as having the highest specificity.

* When an important rule is used on a style declaration, this declaration overrides any other declarations.

#### Using `!important`, however, is bad practice and should be avoided because it makes debugging more difficult by breaking the natural cascading in your stylesheets. 

#### Only use `!important` on page-specific CSS that overrides foreign CSS (from external libraries, like Bootstrap or normalize.css).

#### Never use `!important` on site-wide CSS.

#### Both inline styles and !important are considered very bad practice, but sometimes you need the latter to override the former.

* in a specificity tie, the last rule defined wins.
