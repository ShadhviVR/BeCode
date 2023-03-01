# PHP functions

![Robot presse-oranges](http://ecx.images-amazon.com/images/I/51g-YUKLUoL.jpg)

## What are functions ? What is their purpose ?

You may have seen or heard the acronym *DRY* in programming ? It means :
> " Don't Repeat Yourself ".

Consider this :

```php 

$name = "Maurice";
echo "<p>Hello $name!</p>";
echo '<hr>';
$name = "Alice";
echo "<p> Hello $name!</p>";
echo '<hr>';
$name = "Jesus";
echo "<p> Hello $name!</p>";
echo '<hr>';
$name = "Judas";
echo "<p> Hello $name!</p>";
echo '<hr>';
// OUTPUT
Hello Maurice!
_______________________________
Hello Alice!
_______________________________
Hello Jesus!
_______________________________
Hello Judas!
```
It works just fine. But is it DRY ? Not at all. The same code is repeated 4 times. If we need to change the script for some reason in the future, we'll have to do it in 4 different places, thus increasing the risk of introducing bugs. Hello sadness my old friend...

Now, look at this code. It does exactly the same, but the code to be repeated is aliased into a function: 

```php

//First, you need to declare the function to make it available. It is stored in memory, not ran.
function say_hello($firstname){
	echo "<p>Hello $firstname!</p>";
	echo '<hr>';
}

// Function calls during "Runtime" :
say_hello("Maurice")
say_hello("Alice");
say_hello("Jésus");
say_hello("Judas");

// OUTPUT

Hello Maurice!
_______________________________
Hello Alice!
_______________________________
Hello Jesus!
_______________________________
Hello Judas!
_______________________________
```

Much nicer code, isn't it ? And if one day the designer tells you that (for example) the tag needs a css class "red-text", you can just modify the function declaration, without touching the code that actually gets executed.

> Just for the fun of it, we can make that code even more elegant by using an array, a loop and the function. Do you see how ?

## So : what are functions ?

Think of **functions** as little factories. They can receive an input (but not always), process it inside their walls, then return the result as an Output.

A bit like an orange juice machine : it receives oranges as input, squashes them then returns Orange Juice as output. Yummy !!!

```php
function make_orange_juice($oranges){
	// do things to $input, for example : capitalize it
	$juice = squash($oranges);
	//then return it to get it out of the factory
	return $juice;
}
```

- `function` is a keyword that tells PHP you want to declare a function.  
- `make_orange_juice` is the function name. Choose a name that make it clear what it does.
- `$oranges` is called an **argument**. It can be whatever you want.  
- `return` stops the function processing and makes available the result outside the factory. (here: the content of `$juice`).

 ![Robot presse-oranges](http://ecx.images-amazon.com/images/I/51g-YUKLUoL.jpg)

## Native functions

In the example above, we actually created a function of our own. Of course, PHP comes with tons of useful functions that makes our job much easier.   [Have a look in the manual](http://php.net/manual/fr/funcref.php).  

As a matter of fact, you already use quite a few : 

- `echo` which is a shortcut for `echo()` which displays its argument(s)
- `array()` creates a variable of type `array` which contains its argument(s).  

```php 
$team = array('Elvis', 'Johnny');   
```  

In this example, the input arguments `'Elvis', 'Johnny'` will be returned as an array construct into a `$team` variable.
 
- `print_r($array)` : displays the content of an array.  
- `die("message")` : Display the argument value and then stops the PHP execution. 
- `phpinfo();` display the PHP configuration on your server.
- `date('d M Y')` retrieves the current date, using the specified argument as formatting structure.


### Example: transform a string

The `str_shuffle()` function (read it as  : "**shuffle** **str**ing") makes it easy to ... shuffle the characters of a given text.

```php

$str = 'This is going to be shuffled !';
$str = str_shuffle($str);
 
echo $str;
```

Voilà. Not always useful, but quite fun. Could you think of a way to turn this:

> According to a researcher (sic) at Cambridge University, it doesn't matter in what order the letters in a word are, the only important thing is that the first and last letter be at the right place. The rest can be a total mess and you can still read it without problem. This is because the human mind does not read every letter by itself but the word as a whole.

Into something like this ? 

> Aoccdrnig to rscheearch at Cmabrigde uinervtisy, it deosn’t mttaer waht oredr the ltteers in a wrod are, the olny iprmoetnt tihng is taht the frist and lsat ltteres are at the rghit pclae. The rset can be a tatol mses and you can sitll raed it wouthit a porbelm. Tihs is bcuseae we do not raed ervey lteter by it slef but the wrod as a wlohe.

Let's plan. The words need to stay the same. The letters inside the words are shuffled. So:

1. let's break the big chunk of text into an Array of words.
2. then let's loop through the array
3. for each element, lets shuffle its letters !

Try to solve this! Done ? compare with this [solution](http://sandbox.onlinephpfunctions.com/code/07c77782f193e7404f817c6d0f8608bbcef1692f).


## Custom functions

Functions first need to be declared before they can be used.

**Step 1. Declare (create) the function**. Here is the syntax.  

```php 
function function_name( $argument1, $argument2,...){
	//	one or more operations operating on the arguments...
	return $something;
}
```  

Notice the `{` and `}` brackets, delimiting respectively the start and end of a block of code referred to by the function name. 


**Step 2. Use ("call") the function**   :  
Once declared, you can use it anywhere in your code by simply using its name and (optionally) specifying values as arguments.

```php
function_name($argument);
```

The instructions contained in the functions are executed at that specific point in the script.


## Chaining 
Here is a function that would make sure something sent via an online form is not harmful (a process called "sanitization") :

```php 
function sanitize( $input ){
	//	argument manipulation to clean them up
	return strip_tags( trim( $input) );
	
}
```  
To understand this, a good tip is to **read from right to left**.  
The `$input` argument is sent to  `trim()` , whose result is returned to the  `strip_tags()` function, which then returns its value to the  `return` function which... returns  the result outside of the custom function I chose to call `sanitize()` , which allows me to perform both trim and strip_tags operations in one go.  

Now that we've declared it, we can use it. Here is a typical form processing logical block :

```php

// This condition checks if form is submitted...
if (isset($_POST) && !empty($_POST) ){

	// input sanitization
	$name = sanitize( $_POST['name'] );
	$email = sanitize( $_POST['email'] );

	// validation...
	...
}
```

## Exercises

(Don't be afraid to google. But google smart.)

- Use a function that capitalizes the first letter of the provided argument. Example: `"émile"`should return `"Émile"`
- Use the native function allowing you to display the current year.
- Now display the date, time, minutes and seconds, using the same function, by playing with the arguments.
- Create a "Sum" function that takes 2 numbers and returns their sum.
- Improve that function so that it checks whether the argument is indeed a Number. If not, it should display : `"Error: argument is not a number."`
- Create a function that takes as argument a string of characters and returns an acronym made of the initials of each word.  
Example:  `"In code we trust!"` should return: `ICWT`).
- Create a function that replaces the letters "a" and "e" with "æ".
Example: `"caecotrophie", "chaenichthys","microsphaera", "sphaerotheca"` should respectively return `"cæcotrophie", "chænichthys","microsphæra", "sphærotheca"`.
- Create the opposite function, which replaces "æ" by "ae" in : `cæcotrophie`, `chænichthys`, `microsphæra`, `sphærotheca`
- Create a function to return "notice", "warning" and "error" messages to a user,which takes 2 arguments : the "message", and the "css class" (values:  "info", "error", "warning"). This function would allow us to write this :  

```php 
echo feedback("Incorrect email address", "error");
```
which will produce this html :  
 
 ```html
 <div class="error">Error: Incorrect email address.</div>
 ```
 
 - Improve that function by giving the default class the value of `"info"`. Look into the documentation [documentation php](http://php.net/manual/en/functions.arguments.php).
 - Create a random words generator, that generates 2 words: one whose length is between 1 to 5 letters, the other between 7 and 15 letters.
The screen will display a title "Generate a new word", then the two generated words, and underneath, a button with the text "Generate").
- De-capitalize the string : `"STOP YELLING I CAN'T HEAR MYSELF THINKING!!"`
- In your new job, you have to maintain the code of a former developer. Make it DRY by creating a custom function `calculate_cone_volume` : 

```php  
// Volume of a cone which ray is 5 and height is 2 
$volume = 5 * 5 * 3.14 * 2 * (1/3);  
echo 'The volume of a cone which ray is 5 and height is 2 = ' . $volume . ' cm<sup>3</sup><br />';  
// Volume of a cone which ray is 3 and height is 4  
$volume = 3 * 3 * 3.14 * 4 * (1/3);  
echo 'The volume of a cone which ray is 3 and height is 4 = ' . $volume . ' cm<sup>3</sup><br />';  
```

Here is a schematic, just to make sure you think this is more difficult than it really is...     
![Cone](https://user.oc-static.com/files/5001_6000/5758.gif)

 - Want more exercises on functions? More  [function exercises on W3resource.com](http://www.w3resource.com/php-exercises/php-function-exercises.php).

## ... AND YOU ARE DONE AND SHOULD BE GOOD TO GO WITH THE FUNDAMENTALS OF PHP! NOW, GO MAKE STUFF!
... Don't hesitate to re-do this track, especially if you found it difficult at first. The more you pratice, the easier it gets...

![](./assets/gomakestuff.gif)
