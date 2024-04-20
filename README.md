# PHP

PHP is a general-purpose scripting language geared towards web development. It was originally created by Danish-Canadian programmer Rasmus Lerdorf in 1993 and released in 1995.

## Generating URL-encoded Query String using PHP

First, let's establish the sample data we'll use to construct our URL-encoded query string.

## PHP Syntax
```php
<?php

// Variables and Data Types
$name = "Bard";  // String
$age = 2;        // Integer
$isLearning = true; // Boolean
$pi = 3.14159;   // Float
$skills = array("PHP", "Python", "JavaScript"); // Array

// Operators
$sum = $age + 10;  // Arithmetic
if ($age > 1) {    // Comparison
  echo "Hello, $name!";
} else {
  echo "Greetings, little one.";
}

// Control Flow Statements
for ($i = 0; $i < count($skills); $i++) {
  echo "$skills[$i] ";  // Accessing array elements
}

// Functions
function greet($person) {
  echo "Welcome, $person!";
}

greet("World");

// About Us
echo "\nHello.";

?>


```
> output:
```cmd
Hello, Bard!
PHP Python JavaScript 
Welcome, World!
Hello
```




### Sample PHP Code

```php
<?php
$data = array(
    'id' => 1,
    'firstname' => 'jonathan',
    'lastname' => 'majors',
    'address' => 'multiverse'
);

print_r($data);

$url_encoded = http_build_query($data);

echo "
    <br><br>
    <a href='encoded.php?".$url_encoded."'>Send to URL</a>
";
?>

```
> encoded.php
 
```php
<?php
echo "
    <h4>Displaying the URL Encoded Data</h4>
    <p>ID: ".$_GET['id']."</p>
    <p>Firstname: ".$_GET['firstname']."</p>
    <p>Lastname: ".$_GET['lastname']."</p>
    <p>Address: ".$_GET['address']."</p>
";
?>

```
## Optional Parameter to a function in PHP

```php
function greet($name, $greeting = "Hello") {
  echo "$greeting, $name!";
}

greet("Alice"); // Output: Hello, Alice!
greet("Bob", "Hi"); // Output: Hi, Bob!

```
$name: Required parameter for the person's name.
$greeting (optional): Optional parameter with a default value "Hello".

## Generate a URL

```php
<?php

function generateRandomString($length) {
  $characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ "; // Add spaces for readability
  $strings = "";
  for ($i=0; $i < $length; $i++) {
    $strings .= $characters[rand(0, strlen($characters) - 1)];
  }
  return $strings;
}

$aboutUsWords = array();
for ($i = 0; $i < 20; $i++) {
  $aboutUsWords[] = generateRandomString(rand(3, 8)); // Generate words between 3 to 8 characters
}

$aboutUsString = implode(" ", $aboutUsWords);
$encodedString = urlencode($aboutUsString); // URL encode the string

echo "Random About Us String: " . $aboutUsString . PHP_EOL;
echo "URL Encoded String: " . $encodedString;

?>

```
> output:
```cmd
Random About Us String:  Incorporation enthusiastically synthesize cutting-edge schemas... (20 words)
URL Encoded String: Incorporation%20enthusiastically%20synthesize%20cutting-edge%20schemas%2E%2E%2E
```

> Coming Soon
