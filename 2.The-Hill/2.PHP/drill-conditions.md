# Drill exercice: Conditional structures in PHP

## Objective
By the end of this drill, you will have a good mastery of expressing conditions in PHP for many sorts of use case.

## Let's go !

Make sure your Web Server is started. (on Ubuntu `sudo service apache2 start`)
In the root folder of your web server (usually `/var/www/html`) create a PHP file and call it `conditions.php`. Use it for all the exercises. At the top of the file, write in a comment information that will help you understand where this comes from, should you look back in a few months.

```php
<?php
/**
 * Series of exercises on PHP conditional structures.
*/  


```

### 1. Clean your room! 

#### 1.1. Read, then fix this code
```php

// 1.1 Clean your room Exercise 

$room_is_filthy = true;

if( write_your_condition_here ){
	echo "Yuk, Room is dirty : let's clean it up !";
	cleanup_room();
	echo "<br>Room is now clean!";
	$room_is_filthy = false;
} else {
	echo "<br>Nothing to do, room is neat.";
}
```
To test your code, change the value of `$room_is_filthy` and check that the message displayed is relevant.

#### 1.2. Improve it
Let's now make our script a little smarter by allowing more than 2 possible values. The room could be either "health hazard", "filthy", "dirty", "clean", "immaculate" in that order. Store them in an array `$possible_states`.

Use a `if/ elseif / else` for that. Invent the messages to display for each use case. 

Need a headstart? Here is a starting base, that you'll need to fix.

```php
// 1.2 Clean your room Exercise, improved

// Create the array of possible states
$possible_states = [];

// When testing, change the index value to navigate to the possible array values
$room_filthiness = $possible_states[0]; 

if( write_your_condition_here ){
	echo "Yuk, Room is Disgusting! Let's clean it up !";
} else if( write_your_condition_here ){
	echo "Yuk, Room is dirty : let's clean it up !";
// ...
} else {
	echo "<br>Nothing to do, room is neat.";
}
```

**Expected result:** when changing the value of `$room_filthiness` to any of the possible room states, the relevant message should be displayed.

### 2. Display a different greeting message depending on the time of the day. 

You know what's worse than a stupid robot? A stupid impolite robot. Let's fix that.

Write a script that implements these specifications : 

- If the time is between 05h00 and 09h00, display "Good morning !".  
- If the time is between 09h01 and 12h00, display "Good day !".  
- If the time is between 12h01 and 16h00, display "Good afternoon !".  
- If the time is between 16h01 and 21h00, display "Good evening !".  
- If the time is between 21h01 and 04h59, display "Good night !".  

**Tip:** you can combine multiple conditions (using `AND` / `OR`).

Here is a head start.

```php
// 2. "Different greetings according to time" Exercise

$now = ; // How to get the current time in PHP ? Google is your friend ;-)

// Test the value of $now and display the right message according to the specifications.
if( condition){
} ...

```

### 3. Display a different greeting according to the user's age.

Let's continue to make our robot a little more civil and greet humans properly, taking into account their age.

Here is the user experience we aim for :   
First, users see a form asking for their age :
> Please type your age : __
   
When they submit the form, the page displays the right message:

- if age is less than 12 years old, display "Hello kiddo!"  
- if age is between 12 and 18 years old, display "Hello Teenager !"  
- if age is between 18 and 115 years old, display Hello Adult !"  
- if age is beyond 115 years old, display "Wow! Still alive ? Are you a robot, like me ? Can I hug you ?"

Have both the form and the processing script in the same file. Use the GET method.  

Here is a headstart.

```php
// 3. "Different greetings according to age" Exercise

if (isset($_GET['age'])){
	// Form processing

}
// Form (incomplete)
?>
<form method="get" action="">
	<label for="age">...</label>
	<input type="" name="age">
	<input type="submit" name="submit" value="Greet me now">
</form>


```

### 3. Display a different greeting according to the user's age and gender.

Improve the previous form to add another question: "Man or Woman?". Use an input of type `radio` to capture the data.

If gender is "Woman", the displayed message should be adapted accordingly.

For example, if the user age is between 12 and 18 and the gender is female, display "Hello Miss Teen!" otherwise, display "Hello mister Teen!".

Do the same for all the other age ranges. 

**Tip:** You can nest conditional structures inside others.  

### 4. Display a different greeting according to the user's age, gender and mothertongue.

Improve the previous form to add yet another question: "Do you speak English ? ". Use an input of type `radio` to capture the data. Possible answers: "yes" or "no". 

Then modify your form processing script to implement this :

- If age is below 12 and the user replies "yes", display : "Hello boy!" or "Hello Girl!" according to the gender indicated. 
- If the answer is "no", display "Aloha boy" or "Aloha Girl"  

Adapt all the other answers accordingly, using "*Aloha*" instead of "*Hello*".


### 5. The Girl Soccer team

You want to create a soccer team for girls between 21 and 40 years old.

Create a form asking for the age, gender and name of the person.
Use the `$age` and `$gender` variables in an  `if/else` to display a "*welcome to the team !*" or "*Sorry you don't fit the criteria*" message. 


### 6. Achieve the same, without the ELSE.
A key aspect of coding conditions is to keep them as simple as possible.
Improve the previous exercise by using only an `if` statement (without the `else`), and a default value that changes only if the condition is true. 

### 7. "School sucks!" Exercise

Start a new form that would allow a (nasty) teacher to grade a student.

It would display a different message according to the number annotated : 

- note below 4 : "This work is really bad. What a dumb kid! "
- note between 5 and 9 : "This is not sufficient. More studying is required."
- note equals 10 : "barely enough!"
- note is 11, 12, 13 or 14 : "Not bad!"
- note is 15, 16, 17 or 18 : "Bravo, bravissimo!"
- note is 19 or 20 : "Too good to be true : confront the cheater!"
 

![Giphy](http://media2.giphy.com/media/NzWGJoHbR4zAI/giphy.gif)



### 8. The "Switch" structure.

![Un Switch](./rail-switch.png)

`If/elseif/elseif/else` statements are hard to read. 
Fortunately, you can use another conditional structure: the `switch`.

```php
switch $weather {
	case 'rain':
		echo "Take an umbrella";
		break;
	case 'storm':
		echo "Don't get out today!";
		break;
	default:
		echo "Weather will be ok to day";
}
``` 

It makes for a much readable code. There is a catch though : you can only use it to test equalities, it's not possible to use other operators (`< > <= >= !=`). 


1. Read more on this really cool structure in the PHP manual : [switch](http://php.net/manual/en/control-structures.switch.php).
2. Create a new file `switch-structure.php` and do the previous exercise,using a switch structure instead of the  if/else.




### 9. Ternary operators

This weird term simply refers to a more terse way to write conditions. A bit like a shortcut notation.  Its syntax goes like this :

```php
condition ? value_if_true : value_if_false ;

```


Example:  

```php
$age = 24;
$is_adult = ($age >= 18) ? true : false;
// $is_adult is true
```

Which is a shorter way to write the following :

```php
$age = 24;
if ($age >= 18)
{
	$is_adult = true;
} else {
	$is_adult = false;
}
// $is_adult is true

```

### 10. Ternary exercises

1. In a new file `ternary.php` declare a `$hello` variable which value is a greeting message. That greeting message depends on another variable `$gender`, which can either be "M" or "F". Finish by displaying the resulting message.
2. In a new file `unicorn.php`, create an html form asking "Are you a human, a cat or a unicorn ?". When submitted, the screen displays an animated Gif showing either a human, a cat or a unicorn, as per the user input (you can find gifs [here](https://giphy.com/explore/finding)). Use GET or POST as method, whichever you like. Use a ternary operation to evaluate the condition.

Done ? Bravo, you now know plenty enough on how to write conditions. The rest is practice... Here is a well-deserved gif!

![Giphy](http://media0.giphy.com/media/CNprQ8KGpORVu/giphy.gif)
