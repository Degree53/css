# Degree 53 (Sassy) CSS Style .Guide {

*A mostly reasonable approach to CSS*


## Table of Contents

  1. [General Rules](#general-rules)
  1. [Spacing](#spacing)
  1. [Formatting](#formatting)
  1. [SASS Specific](#sass-Specific)

## General Rules

  - Don't use `#id's` in your CSS. Use `.classes` to allow for the maximum level of reusability.

  - Don't add vendor prefixes manually. Use `@mixins` or [autoprefixer](https://github.com/ai/autoprefixer) which allows you to write your CSS rules without vendor prefixes (in fact, forget about them entirely).

**[⬆ back to top](#table-of-contents)**

## Spacing

  - Use soft tabs set to 4 spaces.

    ```scss
    // bad
    .selector {
    ∙∙color: red;
    }

    // bad
    .selector {
    ∙color: red;
    }

    // good
    .selector {
    ∙∙∙∙color: red;
    }
    ```

  - Place 1 space after `:` in property declarations, with no space before.

    ```scss
    // bad
    .selector {
        color:red;
    }

    // bad
    .selector {
        color : red;
    }

    // good
    .selector {
        color: red;
    }
    ```

  - Place 1 space after commas in lists.

    ```scss
    // bad
    .selector {
        color: rgba(0,0,0,.1);
    }

    // good
    .selector {
        color: rgba(0, 0, 0, .1);
    }
    ```

  - Place 1 space before the leading brace.

    ```scss
    // bad
    .selector{
        // ...stuff...
    }

    // good
    .selector {
        // ...stuff...
    }
    ```

  - Place line breaks between rulesets.

    ```scss
    // bad
    .selector {
        // ...stuff...
    }
    .selector--other {
        // ...stuff...
    }

    // good
    .selector {
        // ...stuff...
    }

    .selector--other {
        // ...stuff...
    }
    ```

  - When grouping selectors, keep individual selectors to a single line.

    ```scss
    // bad
    .selector--one, .selector--two, {
        // ...stuff...
    }

    // good
    .selector--one,
    .selector--two {
        // ...stuff...
    }
    ```

  - Each declaration should appear on its own line for more accurate error reporting.

    ```scss
    // bad
    .selector {background-color: #000; color: #fff;}

    // good
    .selector {
        background-color: #000;
        color: #fff;
    }
    ```

**[⬆ back to top](#table-of-contents)**

##Formatting

  - Code should be lowercase.

    ```scss
    // bad
    .Selector {
        color: #E5E5E5;
    }

    // good
    .selector {
        color: #e5e5e5;
    }
    ```

  - Use hex color codes `#000` unless using `rgba()`.

  - Use 3 character hexadecimal notation where possible.

    ```scss
    // bad
    .selector {
        background-color: #ffffff;
        color: #ff0000;
    }

    // good
    .selector {
        background-color: #fff;
        color: #f00;
    }
    ```

  - Avoid specifying units for zero values.

    ```scss
    // bad
    .selector {
        margin: 0px;
    }

    // good
    .selector {
        margin: 0;
    }
    ```

  - Don't write leading zeros for numeric values with a decimal point.

    ```scss
    // bad
    .selector {
        margin: 0.5em;
    }

    // good
    .selector {
        margin: .5em;
    }
    ```

  - Use shorthand properties where possible, preferring the shortest form.

    ```scss
    // bad
    .selector {
        padding-bottom: 2em;
        padding-left: 1em;
        padding-right: 1em;
        padding-top: 0;
    }

    // good
    .selector {
        padding: 0 1em 2em;
    }

    // bad
    .selector {
        margin: 1em 1em 1em 1em;
        padding: 1em 2em 1em 2em;
    }

    // good
    .selector {
        margin: 1em;
        padding: 1em 2em;
    }
    ```

  - Alphabetize declarations to achieve consistent code in a way that is easy to remember and maintain. Sublime Text will do this for you if you hilight the declaration and hit F9.

    ```scss
    // bad
    .selector {
        text-align: center;
        text-indent: 2em;
        border: 1px solid;
        border-radius: 4px;
        color: black;
        background: fuchsia;
    }

    // good
    .selector {
        background: fuchsia;
        border-radius: 4px;
        border: 1px solid;
        color: black;
        text-align: center;
        text-indent: 2em;
    }
    ```

  - Use single `''` rather than double `""` quotation marks for attribute selectors or property values.

    ```scss
    // bad
    .selector {
        font-family: "open sans", arial, sans-serif;
    }

    // good
    .selector {
        font-family: 'open sans', arial, sans-serif;
    }
    ```

  - Indent all block content to reflect hierarchy.

    ```scss
    // bad
    @media screen {

    html {
        background: #fff;
        color: #444;
    }

    }

    // good
    @media screen {

        html {
            background: #fff;
            color: #444;
        }

    }
    ```

**[⬆ back to top](#table-of-contents)**

##SASS Specific

  - Variablize all common values

    ```scss
    $brand-primary: #2c9c54;
    $brand-secondary: darken($brand-primary, 20%);
    $brand-error: #f00;
    ```

  - Prefer `//` comments over `/* */` as they don't get rendered in the final generated CSS.

    ```scss
    // bad
    /* This is a comment that gets rendered */

    // good
    // This comment never gets rendered
    ```

  - Write `@extend` statements first in rule sets, followed by "regular" property declarations, then `@include` statements and finally nested rule sets. Nothing goes after the nested stuff.

    ```scss
    .fatal-error {
        @extend %error;
        color: $brand-error;
        @include transition(all .3s ease);

        p {
            // ...stuff...
        }
    }
    ```

  - Always use placeholder selectors in `@extend`.

    ```scss
    // bad
    .fatal {
        @extend .error;
    }

    // good
    .fatal {
        @extend %error;
    }
    ```

  - Place `@else` statements on the same line as the preceding curly brace.

    ```scss
    // bad
    @if {
        // ...stuff...
    }
    @else {
        // ...stuff...
    }

    // good
    @if {
        // ...stuff...
    } @else {
        // ...stuff...
    }
    ```

  - Functions, mixins, and variables should be declared with all lowercase letters and hyphens instead of underscores.

    ```scss
    // bad
    $myVar: 10px;

    @mixin myMixin() {
        // ...stuff...
    }

    // good
    $my-var: 10px;

    @mixin my-mixin() {
        // ...stuff...
    }
    ```

  - Separate rule, function, and mixin declarations with empty lines.

    ```scss
    // bad
    p {
        margin: 0;
        em {
            // ...stuff...
        }
    }
    a {
        // ...stuff...
    }

    // good
    p {
        margin: 0;

        em {
            // ...stuff...
        }
    }

    a {
        // ...stuff...
    }
    ```

**[⬆ back to top](#table-of-contents)**

# }
