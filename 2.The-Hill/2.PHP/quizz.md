# QUIZZ / PHP

Try to answer these questions. Some might require you to investigate. Here is a great tool for that : [http://phptester.net](http://phptester.net). Use it also to check whether you got it right. 

- PHP code must sit inside specific tags. Which one(s) ?
	-  `<?php>...</?>`  
	-  `<script>...</script> ` 
	- `<&>...</&> ` 
	- `<?php...?>`

- Which of the following variables **do not** have a valid name ? 
  
	- `myvar`
	- `$myvar`
	- `$var5`
	- `$_myvar`
	- `$_5var`
	- `$__élément1`
	- `$hotel4*`


- In which variable is stored the data sent via an html form using the GET method ? 
- When submitting a form using the POST method, the variables values appear in the URL. True or False?
- What is the difference between `$a=$b` and `$a==$b` ?
- What character must be at the end of each line of php code ?
- What will return this line: `echo "Hello" + " World";` ? Why ?
- What is the right syntax :  
 		- `<?php echo Hello World; ?>`  
		- `<?php echo("Hello world"); ?>`  
		- `<?php echo "Hello World": ?>`  
		- `<?php echo 'Hello World'; ?>`  
		- `<?= "Hello World"; ?>` 
 
- What is the result of this script ? Why ?

```php  
$Hour = 15;
$hour = 3;
echo ($hour == $Hour) ? "yes": "not correct";
```

- What is the correct way to write comments in PHP ?
	- `// This is a comment `
	- `/* This is a comment */ `  
	- `*/ This is a comment /* `  
	- `# This is a comment`  

- What is the result of this script ? Why ?

```php  
$Hour = 15;
$hour = 3;
echo ($hour == $hour) ? "yes": "not correct";
```

-  What is the name of this type of operator in the following example ?

```php  
echo ( $season == 'summer' ) ? "Go to the beach.": "Go skying.";
```
- If the condition in the previous statement is true, where will we go ?

- What is the difference between :  
		- `$a = 10;`  
		- `$a = "10";`  
		- `$a = array(10); `   

	**Tip**: use the `var_dump($a);` function to check each of these expressions.

- What will the following return ?

```php  
$a = 10;  
$b = 2;  
echo $a + $b;  
```

- And this one ? 

```php  
$a = 10;  
$b = 2;  
echo $a * $b;  
```

- And this one ? 

```php  
$a = 10;  
$b = 2;  
echo $a - $b;  
```

- And this one ? Why ?

```php  
$a = 10;  
$b = 2;  
echo $a . $b;  
```

- What will this script return at 10h23 AM ?

```php  
$hour = date('H');
if ($hour > 17){
	echo "Good evening!";
} elseif ($hour > 13){
	echo "Good afternoon!";
} else{
	echo "Hello!";
}
```

- ... And what will it return at 15h02 AM ?
- Assume `$a = 4`. What instruction will return : `4 = four` ? Why ?

	- `echo '$a = four';`
	- `echo '$a = 2+2';`
	- `echo "$a = four";`

- In the case of a form to collect sensitive data, which method will we rather use to send the data :  
	- GET
	- mailto
	- POST

 -----=== End of the quizz ===-----

![Giphy](http://media0.giphy.com/media/ByJey854EnFZe/giphy.gif)
