# Naming Convention in PHP

## General

PHP keywords are in lowercase. The constants  `true`, `false`, `null` etc. are in lowercase.

Aviod Unnecessary Variables
```php
# bad
<?php
    $name = trim($_POST['name']);
    echo $name;
?>

# good
<?php
    echo trim($_POST['name']);
?>
```

## Variables

Do **NOT** use case to differentiate between different variables. As other programming language, the name should be **self-descriptive**, using either complete words or understandable abbreviations. The variables are usually declared with **camelCase**.

```php
$firstName = "Isabelle";
```
The global variables can be distinguished with a prefix `g`.

### Constant

The constants are in **capital**. Note that the constant needs no `$` as a prefix. The defining of constants is usually through the function `define(name,value,case-sensitive)`. Inside the Class definition, constant is declared with `const` instead of using `define()` function.

```php
<?php
// Using "define('MY_VAR', 'default value')" INSIDE a class definition does not work as expected. You have to use the PHP keyword 'const' and initialize it with a scalar value -- boolean, int, float, string (or array in PHP 5.6+) -- right away. 

// only work outside Class
define("PI","3.14");
define("SITE_URL","https://strawberryfamily.de");
echo SITE_URL;  // no $ in the prefix

// work inside Class
class AuthorInfo
{
    const MAX_PEOPLE = 100;
}
echo AuthorInfo::MAX_PEOPLE;
?>
```

Do not name the constant with `__` in prefix and subfix according to this [php official documentation](https://www.php.net/manual/en/language.constants.php), since the format `__VARIABLE__` is preserved for further use.

```php
<?php
// bad
define("__NAME__","Isabelle");
?>
```

## Classes

Classes are named with **camelCase** or **PascalCase**. Both are accepted and popular in `PHP`.

```php

<?php

class AuthorInfo
{
    #<to do>
}

?>
```

## Functions

Unlike Javascript, the functions are name with **snake_case**.

```php
function create_account ()
{
    #<to do>
}
```

Same as variables, functions with `__` prefix are preserved as magical functionality in PHP, for example, `__get()`, `__autoload()`.
