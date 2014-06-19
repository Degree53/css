# Degree 53 (Sassy) CSS Style .Guide {

*A mostly reasonable approach to CSS*


## Table of Contents

  1. [Spacing](#spacing)
  1. [Formatting](#formatting)

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
    .selector {color: #fff; background-color: #000;}

    // good
    .selector {
        color: #fff;
        background-color: #000;
    }
    ```

##Formatting

  - Use hex color codes `#000` unless using `rgba()`.

  - Use 3 character hexadecimal notation where possible.

    ```css
    // bad
    .selector {
        color: #ff0000;
        background-color: #ffffff;
    }

    // good
    .selector {
        color: #f00;
        background-color: #fff;
    }
    ```

**[⬆ back to top](#table-of-contents)**

# }
