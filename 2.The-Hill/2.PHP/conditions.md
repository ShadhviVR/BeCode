# PHP: conditional structures


![Rail Switch](https://pmcdn.priceminister.com/photo/Aiguillage-train-miniature-1097270594_L.jpg)

## Conditions

The world we live in is an ever-changing dynamic system.  
Sometimes it rains, sometimes we can enjoy a bright sunshine. Sometimes it is daylight, sometimes, it is a pitch dark night. Sometimes, the person in front of you is a man, sometimes it is a woman. Sometimes, it's cold, sometimes it's hot. In Belgium alone, there are 3 different official languages. Depending on where you are, you greet people differently.

We, humans, have learned to deal with these variations. For instance, if it is cold outside, we reach out for a scarf to cover our neck. But if we are in the middle of a summer heat wave, that behaviour would be irrelevant.
 
Well, we have learned a decision-making system that is now almost inconscious, allowing us to deal with variations. We ask ourself a question : "should i wear a scarf ?" which leads to "what's the weather forecast?" upon which information we decide whether we should (_true_) or should not (_false_). 

In programing, this logical pattern is called a **conditional structure**.
The most common forms are the  `if()`, the `if () /else` and the `if()/else if()/ else` statements.  The syntax looks like this :

```php
if( condition ) {
   // code to execute if the condition results TRUE
  echo "Yep, that's right.";
  echo "And I love being right!";
 } else {
   // code to execute if the condition results FALSE
   echo "Nah, it's not.";
   echo "Better luck next time :-( .";
 }
```

Did you notice the `{` and `}` characters ? They are used to encapsulate blocks of instructions to be executed together. You'll see them in conditions and in functions.


### Operators
Operators are caracters you can use to express conditions by doing comparisons between 2 parts. You can use several types of operators : 

`==` : is the same as 
`!=` : is different than  
`>` : is greater than  
`<` : is smaller than  
`>=` : is greater or equal to  
`<=` : is smaller or equal to 

This must feel a bit abstract at this point, so let's go back to our weather forecast situation.  In PHP you could solve that decision-making algorithm like this: 

```php
if( $temperature > 21 ) {
   // code to execute if the condition results TRUE
   $clothes = "T-shirt";
   $should_i_wear_a_scarf = false;
 } else {
   // code to execute if the condition results FALSE
   $clothes = "Pull-over";
   $should_i_wear_a_scarf = true;
 }
 
 if ($should_i_wear_a_scarf == true){
	 // this is a "fake" function for the sake of the example 
	 // that function is only executed in the condition is true
	 grab_scarf_from_door_hanger();
 }
 // The following function will be executed everytime, 
 // but its $clothes argument changes according to the result
 // of our previous conditional structure
cover_my_chest_with($clothes);
 
```

#### Exercise:
- Change the condition so that it becomes: "if the temperature is greater or equal to 15 degrees".

## Combining conditions

### condition1 AND / OR condition2 
You can test a "multiple condition" by using the keywords  `AND` and `OR`.

```php
if ( $age <= 12 AND $language == "English" ) { 
	echo "Hello kiddo!";
} else {
	echo "Good day stranger !";
}
```

## Conditions in conditions
You can also write conditions inside conditions. Pay special attention to your brackets (`{`) signs.

**Tip** Using proper code indentation helps to visualize the   l'indentation du code pour t'aider à t'y retrouver visuellement.

```php
if ($gender == 'Female'){

	// Instructions here will be ran if gender is "Female"

	if ( $age <= 12 and $language == "English" ) {
		// Instructions here will be ran if gender is Female, age is below 13 and language is English.  
		...
	} else{
		// Instructions here will be ran if gender is Female, and age is above 12 or language is not English. 
		...
	}

} else {
	// Instructions here will be ran if gender is not "Female"

	if ( $age <= 12 and $language == "Chinese" ) {
		// Instructions here will be ran if gender is not Female, and if age is below 13 and language is Chinese. 
		...
	}
}

```

### Best Practice: PHP before HTML
Now that you are ready to write your own conditions, you might as well keep the following advise in mind.  
As you have seen before, you can mix html and php in the same `.php` file.  
But you should try to keep as much php before doing any html, as once you start doing html, you are returning to the client and a series of operations will not be possible anymore (redirections via php, creating cookies, ...) .


## Exercises

### A Drill 
Practice the art of writing conditions with this [series of exercises](drill-conditions.md).  


### Real-life scenario : form field validation
PHP is often used to process data sent via an html form. A mandatory part of that process is to check whether the data sent matches the expected input. To protect your application against human errors or hacking attempts. This is called **form validation**.

For instance, your application might require that a specific field `fullname` be mandatory. You could then imagine such a check : "if the number of characters in the input is below 1, the input is empty, and thus invalid".

One way to write it would be : 

```PHP
$fullname = $_GET['fullname'];

if ( strlen($fullname) == 0 ){
  echo "Ahem. You forgot to enter your name.";
  exit;
}
```
Try to guess what the function  `strlen()` does... Then look in the [PHP manual.](https://www.php.net/manual/en/function.strlen.php) to see if you got it right.

**Note**: There are many other ways to express that condition "is not empty". Explore the following PHP functions [in the php documentation](http://php.net/manual/en/index.php):  
- ` empty() `  
- `filter_var()`  

![Giphy](https://media0.giphy.com/media/gpDtMjkONKp7a/giphy.gif)
