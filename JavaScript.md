# Variables

Variables in JavaScript are **case sensitive**. They should be self-descriptive.

```javascript
// bad
var value = "Isabelle";

// bad
var val = "Isabelle";

// good
var firstName = "Isabelle";
```

Usually the variable (string, boolean, number) as well as object, array, or function is declared with a **camelCase**, where the lowercase words are concatenated, and from the second word, the first letter is uppercase. 

A brief overview about the four case styles:

1. [x] camelCase,
2. [x] RascalCase,
3. [ ] snake_case,
4. [ ] kebab-case (NOT possible).

```javascript
// bad
var firstname = "Isabelle";

// bad
var first_name = "Isabelle";

// bad
var FIRSTNAME = "Isabelle";

// bad
var FIRST_NAME = "Isabelle";

// good
var firstName = "Isabelle";
```

## Boolean

It is common to use a prefix like `is`, `are`, `has` in the names to distinguish a boolean from other variables.

```javascript
// bad
var flag = true;

// bad
var clicked = true;

// good
var isClicked = true;
```

## Constant
Constant is the non-changing variables, which is written in capital letter.

```javascript
var HOURS = 24;
var PI = 3.1415;
```

If a variable has more than one word in its declared name, an underscore `_` is used

```javascript
var TOKEN_PER_DAY = 10;
```

## Global Variable

No special naming conventions for global variable. But it follows some rules:

- declared at the **top** of the file,
- written in **camelCase** if **changable**,
- written in **UPPERCASE** if **constant**.

# Function

Functins in JavaScript are written in **camelCase**. It is better to use **verb** as the first word to tell what the function is doing.

```javascript
// bad
function name (firstName, lastName) {
    return `${firstName} ${lastName}`;
}

// good
function getName (firstName, lastName) {
    return `${firstName} ${lastName}`;
}
```

The verb in the first position ca be anything, for examples, *get*, *push*, *apply*, *post*, *compute*, *fetch*, *delete*, *clear*, and so on.

# Class

## Class Name

A class is name in **PascalCase**.

```javascript
class AuthorInfo {
    constructor (firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
}

var author = new AuthorInfo('Isabelle','Einstein');
```

## Methods

A method in a class is declared with a verb as prefix and with **camelCase**.

```javascript
class AuthorInfo {
    constructor (firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    getName() {
        return `${firstName} ${lastName}`;
    }
}

var author = new AuthorInfo('Isabelle','Einstein');
```

## Private

The private method is declased with **camelCase** and with an underscore `_` in the beginning. A private variable or function is used internally, which means that it shouldn't be used outside the file, for example, should be avoided to be used in an instance of the class.

```javascript
class AuthorInfo {
    constructor (firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.fullName = _getName();
    }

    _getName() {
        return `${firstName} ${lastName}`;
    }
}
var author = new AuthorInfo('Isabelle','Einstein');

// bad
var fullName = author._getName(this.firstName, this.lastName);
```

# Component

In the frontend frameworks **React**, you will find components in PascalCase. Components are not common in JavaScript.

```javascript
// bad
function userProfile(author) {
  return (
    <div>
      <span>First Name: {author.firstName}</span>
      <span>Last Name: {author.lastName}</span>
    </div>
  );
}
 
// good
function UserProfile(author) {
  return (
    <div>
      <span>First Name: {author.firstName}</span>
      <span>Last Name: {author.lastName}</span>
    </div>
  );
}
```

# File

You can name files in JavaScript by using **PascalCase** and **kebab-case**. In React, you will see PascalCase in the frontend applications,

```javascript
- components/
--- user/
----- UserProfile.js
----- UserList.js
----- UserItem.js
--- ui/
----- Dialog.js
----- Dropdown.js
----- Table.js
```

and kebab-case in the backend application

```javascript
- routing/
--- user-route.js
--- messages-route.js
```

