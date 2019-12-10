# Les bases



**Comparaisons de $x avec des fonctions PHP**

| Expression | [gettype\(\)](https://www.php.net/manual/fr/function.gettype.php) | [empty\(\)](https://www.php.net/manual/fr/function.empty.php) | [is\_null\(\)](https://www.php.net/manual/fr/function.is-null.php) | [isset\(\)](https://www.php.net/manual/fr/function.isset.php) | [boolean](https://www.php.net/manual/fr/language.types.boolean.php) : _f\($x\)_ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| _$x = "";_ | [chaîne de caractères](https://www.php.net/manual/fr/language.types.string.php) | **`TRUE`** | **`FALSE`** | **`TRUE`** | **`FALSE`** |
| _$x = null;_ | [NULL](https://www.php.net/manual/fr/language.types.null.php) | **`TRUE`** | **`TRUE`** | **`FALSE`** | **`FALSE`** |
| _var $x;_ | [NULL](https://www.php.net/manual/fr/language.types.null.php) | **`TRUE`** | **`TRUE`** | **`FALSE`** | **`FALSE`** |
| $x est indéfini | [NULL](https://www.php.net/manual/fr/language.types.null.php) | **`TRUE`** | **`TRUE`** | **`FALSE`** | **`FALSE`** |
| _$x = array\(\);_ | [array](https://www.php.net/manual/fr/language.types.array.php) | **`TRUE`** | **`FALSE`** | **`TRUE`** | **`FALSE`** |
| _$x = array\('a', 'b'\);_ | [array](https://www.php.net/manual/fr/language.types.array.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = false;_ | [boolean](https://www.php.net/manual/fr/language.types.boolean.php) | **`TRUE`** | **`FALSE`** | **`TRUE`** | **`FALSE`** |
| _$x = true;_ | [boolean](https://www.php.net/manual/fr/language.types.boolean.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = 1;_ | [entier](https://www.php.net/manual/fr/language.types.integer.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = 42;_ | [entier](https://www.php.net/manual/fr/language.types.integer.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = 0;_ | [entier](https://www.php.net/manual/fr/language.types.integer.php) | **`TRUE`** | **`FALSE`** | **`TRUE`** | **`FALSE`** |
| _$x = -1;_ | [entier](https://www.php.net/manual/fr/language.types.integer.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = "1";_ | [chaîne de caractères](https://www.php.net/manual/fr/language.types.string.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = "0";_ | [chaîne de caractères](https://www.php.net/manual/fr/language.types.string.php) | **`TRUE`** | **`FALSE`** | **`TRUE`** | **`FALSE`** |
| _$x = "-1";_ | [chaîne de caractères](https://www.php.net/manual/fr/language.types.string.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = "php";_ | [chaîne de caractères](https://www.php.net/manual/fr/language.types.string.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = "true";_ | [chaîne de caractères](https://www.php.net/manual/fr/language.types.string.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |
| _$x = "false";_ | [string](https://www.php.net/manual/fr/language.types.string.php) | **`FALSE`** | **`FALSE`** | **`TRUE`** | **`TRUE`** |

## Variables

## PDO



