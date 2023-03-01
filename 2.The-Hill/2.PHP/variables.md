# PHP Fundamentals : Variables

## Variables

In essence, programing is the manipulation of data and information.

```php
$variable_name = "This is the variable's value";
$us_president = 'Donald Trump';
$birth_year = 1973; 
$is_raining = false;
$team_players = array('Jean','Jeanne','Dirk');
```

Remember the script that would greet each of the 7 billion humans by their
individual name?

Well, let's write it out.

- go into the folder served by your Web server (on Ubuntu, it often is `/var/www/html` or `/htdocs` or `/public`

- Create a folder `variable` and inside, a file called `humans.php` containing this piece of code :  

```php
<html>
  <head><title>Hi!</title></head>
  <body>
  	<?php if (isset($_GET['name'])){ ?>
    	<h1>Aloha <?php echo $_GET['name']; ?>!</h1>
   	<?php } ?>
    
  </body>
</html>
```

- Done ? Open the following urls in your browser and looks what happens:  
  - [http://localhost:80/variable/humans.php?name=Alexandre](http://localhost:80/variable/humans.php?name=Alexandre)
  - [http://localhost:80/variable/humans.php? name =Pierre](http://localhost:80/variable/humans.php?name=Pierre)
  - [http://localhost:80/variable/humans.php? name =Jennifer](http://localhost:80/variable/humans.php?name=Jennifer)

- Read the script again and try to understand what actually happens.

As you can see, the file contains *mostly* html with bits of PHP code. These start with  `<?php` and end with `?>`. Consider them as tags that allow us to mix php inside html.  

- Let's have a closer look at this little snippet :  

```php
<?php echo $_GET['nom']; ?>
```

What do we see: 

- ` $_GET ` is a variable.
- in PHP, a variable **always** starts with the `$` sign
- `echo ` is a function native of PHP, which is used to reveal the content of a variable.
- the line finishes with  `;`. In PHP, it is mandatory otherwise it will throw an error at you.

With that said, let's start with the beginning : variables.

## Variables


*Variables* allow us to store something in memory. For instance, the logged in user's name, their date of birth (and thus calculate their age) and many many things! Variables are at the heart of programing.

You could think of a variable as a box, that can contain anything : texts, numbers, objects,... called "value".  
![Carton](./assets/carton.png)

The label on the box = the variable name  
The content inside the box = the value of the variable

Like butterflies, the typical variable does not live long in PHP : only for the duration that the script is executed.
As soon as the script is done, all variables are cleared out of memory to save resources. Think of it more as a small bit of information stored in the RAM of the server.

They are called variables because their value can change in the course of the script. For example: 

```php
$a = 5;
$a = $a + 37;
echo $a;
```

See ? The `$a`variable has changed value twice. Can you guess what the result is?

### A Name and a Value
    
- The variable **name** : a bit like the label you put on boxes when moving houses, the variable name allows you to recall the information from memory. For example : `$user_age`;  
- The variable **value** : it's the valuable part of the variable (pun intended :D). For instance: `45`.  

We can modify that value, perform operations with it, etc. When you need to retrieve the information, call the variable by its name, and its value will be accessible to your script. 

> The proper wording is "assigning a value to a variable".

#### Naming do's and dont

Rules for PHP variables:

- A variable starts with the `$` sign, followed by the name of the variable
- The dollar must then be followed with either a letter or the underscore `_` character, not a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable names are case-sensitive ( `$age`, `$Age` and `$AGE` are three different variables)

### Types of variables
Much like boxes in which you could have pizza, shoes, pearls, even live chicken (hopefully not all at once), you can store many things in variables :  numbers, text, objects, tables of values (called Arrays)...

Here is the list of variable types at your disposal. Coding is a lot about choosing the right type of variables so make sure to understand each type.

- **Strings of text** (*string*) : perfect for textual content. In programing, text is called _string_. These variables are recognizable by the **quotation marks** on either side of the value  : 

```php  
$message = "I need pizza !";  
```
- **Integer numbers** (*int*) : Integers are numbers like 1, 2, 3, 4, etc. Including their negative counter parts : -1, -2, -3…  
Example : 

```php 
$total = 42 + 4 ;
```
  
- **Floating numbers** (*float*) : numbers that contain floating decimal points. For example, the numbers 5.5, 0.001, and -2,345.6789 are floating point numbers.  In the following example, $total contains a *float*.

```php 
$total = 42 + 4.34543; 
``` 

- **Boolean** (*bool*) : Boolean variables can only have one of two possible value : either `true`or `false`. I tend to think of them as the typical light switch in a household: it can be either "on" or "off".

```php
$is_old_enough_to_vote = true;
```

- **Null** (*NULL*) : as weirdly as it sounds, it's sometimes useful to be able to assign emptyness as a variable's value. It is more the lack of type than a type.  

```php
$donald_trump_humanity = NULL;
```

- **Arrays** (*Array*) : Arrays can contain sets of values, each located at a specific place in the array, called an *index*. It is a very useful logical structure, that deserves a chapter on its own, which we'll go to later ([Impatient? it is here](php-array.md)).  

```php
$team = array(
  0 => 'Cindy', 
  1 => 'Jean', 
  2 => 'Mustapha', 
  3 => 'Pierre', 
  4 => '', 
  5=>'Eric'); 
```

This `$team` array above contains 6 elements. Each element has a *key* (the number on the left) and a *value* (on the rightside of the `=>`arrow). The index starts at `0`.


### Exercises

Create a file called `variable_types.php` and try to do this:

1. Store your first name in a variable, then display its value (`echo`) in a `<p>` html tag so that the screen shows:   
> Hi! My name is ______. 

2. Then add another variable to contain your age, then display it in a second `<p>` tag : 
> I am ____ years old.
3. Then add yet another variable that describes the colour of your eyes, then display it in another `<p>` tag : 
> My eyes are ____
4. Then add yet another variable that contains the name of all the people in your family. What type of variable would you use for that ?
5. Display the value stored at the first index in another `<p>` tag : 
> The first person in my family is ____

5. And finally : what type of variable would you use to store the information whether you are hungry or not ?
