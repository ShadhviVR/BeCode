# PHP Arrays

Feel free to use [http://phptester.net/](http://phptester.net/) to play with the examples.


![Armoire](./assets/array-shelve.jpg)

Back when we were discussing Variables, we identified several types :  

1. Strings of text (*string*, ex: `"Hello"`)  
2. Integer numbers (*int*, ex: `11` )  
3. Floating numbers (*float*, ex: `3.141518`)  
4. Booleans (`true` or `false`)  
5. NULL (`null`)  
6. Arrays

Arrays are a bit special : whereas the other types can only hold one value, arrays can contain more than one value, in fact, as many as we want!
This is why the metaphor of the box seems a bit unfitting to Arrays; I 'd rather think of Arrays are as Shelves...

Because of this, Arrays are very well suited to contain data to be grouped together such as : 

- All the countries in the world
- The members of a family or of a team
- The components of a system (a car, a recipe ...)
- ...

## Syntax

Here is one way to declare an array : 

```php
$ingredients = array( 'Milk', 'Egg', 'Flour', 'Butter', 'Sugar' );
```

PHP then stores this in memory :

```php
Array
(
    [0] => 'Milk'
    [1] => 'Egg'
    [2] => 'Flour'
    [3] => 'Butter'
    [4] => 'Sugar'
)
```

The digits on the left are called **numeric keys** and are automatically assigned by PHP. They allow us to retrieve the value sitting in the corresponding shelf.
Did you notice that the key of the first element is `0`(not `1`) ?

(Note that keys can also be *Strings*, called **associative keys**. The array then becomes an Associative Array. More on this later.)

Here is how to retrieve the information using the key: 

```php
echo $ingredients[2];
// returns 'Flour'
```

## How to create an Array

You need to use the `array()` function :

```php 
$team = array(); 
```

... Of course, in PHP there are often a shorter way to do the same thing... this does the same : 

```php 
$team = []; 
```

They don't have to be empty upon creation : you can directly feed them values: 

```php 
$team = [ 'Vincent Company', 'Eden Hazard', 'Manneken Pis' ]; 
```

Notice how the elements in the array are separated by a comma : `,`

You could also create the Array value after value : 

```php
$team = array();
$team[0] = 'Vincent Company';
$team[1] = 'Eden Hazard';
$team[2] = 'Manneken Pis';
``` 

### Exercises

Let's play a bit with what you've learned so far...

1. Here is an array of countries :

```php
$countries = array( 'Belgium', 'France' , 'Germany', 'Netherlands', 'Ukraine' ); 
```

What will this line return ? 

```php
 echo $countries[2];
```

answer: `ʎuɐɯɹǝפ`

2. Create an array representing your family members
3. Display its content using the  `print_r` function
4. Then, create an array describing your favourite recipes
5. Display its content using the  `print_r`
6. Then, create an array listing your favourite films
7. Then, using that array, display only the one film you like best using its index

### Most common array operations

#### Check the content of an array for debugging

You can check an array content using `var_dump()` but I like this technique better as it contains less visual noise : 

```php
echo '<pre>';
print_r($countries);
echo '</pre>';
```

`var_dump()` will add more information, which might sometimes be useful, so make sure to not blindly follow my advise, and test it too: 

```php
var_dump($countries);
```


#### Retrieve and display an element
As mentioned above, to retrieve a value in an array, we have to use its corresponding key, mentioned inside squared brackets `[ ]` . 

```php
 echo $countries[2];
```

#### Add an element

Here is the long way :

```php
array_push($countries, 'England');
```

And the short way :

```php
$countries[] = 'England';
```
If you want to use an associative key (more on this in a bit):
```php 
$person['function'] = 'Junior Web Developer';
```


#### Replace the value of a key by another one

Say `$person`describes, Jeanne, a Junior Web Developer :

```php 
$person['function'] = 'Junior Web Developer';
echo $person['function'];
// returns 'Junior Web Developer'
```
After a few years in the industry, she's promoted to Senior.

```php 
$person['function'] = 'Junior Web Developer';
$person['function'] = 'Senior Web Developer';
echo $person['function'];
// returns 'Senior Web Developer'
```


## Associative Arrays

Associative arrays function much like the numeric arrays, except that instead of using numbers, we can use **unique labels** as indexes.

For example, suppose we want to record a person's contact information in an array. With a numeric array, you would have to know that the key `1` contains the street, key `2`contains the city. Not convenient.

```php 
$person[0] = '02/2198445';
$person[1] = 'Cantersteen 10';
$person[2] = 'Brussels';
```

That's why associative arrays are much more useful and make your code more legible.

```php
// compare this
echo $person[1];
// with this
echo $person['street'];
```


### Coding an Associative Array

It's pretty much the same as for "normal" arrays, except that you specify a label in front of each information.


```php 
$user = array (
    'firstname' => 'Juan',
    'lastname' => 'Pablo',
    'adress' => '3 Paradijsestraat',
    'city' => 'Antwerpen'
    );
```
**Note 1**:  Although it spans over multiple line, there is really only one instruction (there is only one `;`). PHP allows to write your code on several lines, should you find it more legible.

**Note 2**: Notice the arrow (`=>`) to assign the key to its value.

Thus, to display the user's lastname, you can simply do : 

```php
echo $user['lastname'];
```

#### Exercise

Describe yourself using an associative array: `$me`. Specify your age, your favourite season of the year, wether you like soccer or not (boolean). Try to use the right variable type for each value.

Here is a head start :

```php
$me = array('firstname' => 'Karen');

```

```php
echo '<pre>';
print_r($me);
echo '</pre>';
```

## Multidimensional arrays

As seen before, you can store all types of values in an array... including other arrays! Your array then becomes a **multidimensional Array**. Very useful because now you can store many things that come as groups. For intance, let's add your favourite movies to the `$me`array :


```php
$me = array(
	'age'	=> 45 , 
	'firstname' 		=> 'Alexandre' ,
	'lastname' 	  		=> 'Plennevaux' ,
	'favourite_movies' 	=> array('My Own Private Idaho', 'Her', 'Matrix')
);

echo '<pre>';
print_r($me);
echo '</pre>';

```

### Exercices
1. Add your hobbies using an array to your `$me` array

```php
$me['hobbies'] = ...
```

2. Then, after the `$me` array, create a second array with the same keys as yours, to describe your mother : the `$mother` array (make it someone else if you prefer).
3. Make sure to also describe her hobbies
4. Then, below that, assign the `$mother` array to a new key in your `$me`array : let's call that key   `'mother'`.
5. Now, below that, check the content of `$me` using `print_r()`. (wrap it inside a `<pre>` html tag to make it more legible ). It should show a multi-dimensional array, where the mother array are values of your `mother` key.
6. Read multiple times your code to make sure you understand what happens.

## Manipulating arrays exercises

### Count the number of elements

 - Say you want to know how many hobbies your mother has.  Try to guess the native php function that allows you to **count** the number of elements in an array.  
 - Below, count your own hobbies
 - Below, add both totals and display the total amount of hobbies. 

### Add an element in a multi-dimensional array
A friend introduced you to the joys of Taxidermy : it quickly becomes your new hobby.  Try to find the right way to add that new hobby to your array's `'hobbies'` key.

Answer: `;,ʎɯɹǝpᴉxɐʇ,=[][,sǝᴉqqoɥ,]ǝɯ$` 

### Replace
You decide you need a reset and change your last name to `Durand`. 
How would you update your array ? 

### Create a new array from 2 others (or more)

One day, you meet your `$soulmate`. Describe your soulmate as an array, with the same keys as yours.

Now, I wonder ... What are the potential hobbies your child could have ?  It turns out there was a documentary on TV the other day, in which an expert in Genetics explained 2 possible scenarios that could answer that question :

- either **intersection** (only the hobbies common to both arrays)
- or a **fusion** (all the hobbies of each array together)

Try to guess the name of the 2 PHP functions that can make these two operations and look it up in the online PHP Manual. (Tip: both start with  `array_`). Test their syntax and try to answer the question.

Here is a headstart: 

```php
$me = array(...);
$soulmate = array( ... );

// perform array operation
$possible_hobbies_via_intersection = array_...;
$possible_hobbies_via_merge = array_...;

echo '<pre>';
print_r($possible_hobbies_via_intersection);
print_r($possible_hobbies_via_merge);
echo '</pre>';
```



## More array exercises
Let's get more fluent in array manipulation : add, delete and replace elements.

**For each of these exercises, use `print_r()`or `var_dump()` to check if the result corresponds to the specifications.**


- Create an array ` $web_development` containing a `'frontend'` and a `'backend'` key. Assign an empty array to each key. 
- Then, add a line underneath that pushes `'xhtml'` in the right array.
- Then, add a line underneath that pushes `'Ruby on Rails'` in the right array.
- Then, add a line underneath that pushes `'CSS'` in the right array.
- Then, add a line underneath that pushes `'Flash'` in the right array.
- Then, add a line underneath that pushes `'JavaScript'` in the right array.
- Then, add a line underneath that replace `'xhtml'` by `'html'`.
- Then, add a line underneath that removes `'Flash'` from the array.


![Giphy](./assets/woohoo-anim2.gif)
