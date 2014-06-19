# Degree 53 (Sassy) CSS Style .Guide {

*A mostly reasonable approach to CSS*


## Table of Contents

  1. [Spacing](#spacing)
  1. [Formatting](#formatting)
  1. [SASS Specific](#sass-Specific)

## Spacing

  - Use soft tabs set to 4 spaces

    ```css
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

  - Place 1 space after : in property declarations

    ```css
    // bad
    .selector {
        color:red;
    }

    // good
    .selector {
        color: red;
    }
    ```

  - Place 1 space before the leading brace.

    ```css
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

    ```css
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

    ```css
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

    ```css
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

    ```css
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

    ```css
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

    ```css
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

    ```css
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

    ```css
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

    ```css
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

  - Use single ('') rather than double ("") quotation marks for attribute selectors or property values.

    ```css
    // bad
    .selector {
        font-family: "open sans", arial, sans-serif;
    }

    // good
    .selector {
        font-family: 'open sans', arial, sans-serif;
    }
    ```

##SASS Specific

  - Prefer `//` comments over `/* ... */` as they don't get rendered in the final generated CSS.

    ```css
    // bad
    /* This is a comment that gets rendered */

    // good
    // This comment never gets rendered
    ```



**[⬆ back to top](#table-of-contents)**

# }
