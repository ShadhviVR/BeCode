= Log yourself in

// Links
:mvc: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
:crud: https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
:tstamp: https://en.wikipedia.org/wiki/Timestamp
:pdo: https://phptherightway.com/#pdo_extension

Type of challenge: *learning* +
Duration: *4 days* +
Team challenge: *solo* +
Project submission (if you want a feedback about your project): https://forms.gle/e7FJkCQ1WtoCJAgZ7



== Learning objectives

At the end of this challenge you should be able to:

* write *SQL queries*
* use a *database manager*
* make a *CRUD* (create, read, update and delete) system
* write a login and registration form
* manage login state


== The mission

You probably *login* to countless website everyday, but have you ever wondered
how it's done? Well today you'll have to *code it*!

This challenge will have you create a {crud}[CRUD] system allowing users to
register, login, modify and delete themselves from your _database_. Optionally
you should try to apply an {mvc}[MVC] structure to your project.

For the sake of learning, you should try to use a *database manager* (DB beaver,
mysql workbench, PhpMyAdmin _not recommended for security concerns_, etc...) to
work with the database. You could also use the _terminal_ to manage your
databases, but that'll be for another time.

There are *no deadlines* for this challenge, so take the time to make your work
*functionnal* and *pretty*.

=== Instructions

==== Step 1: create a database

Go to your *database manager*, create a database called _becode_ with a table
called _student_.

The _student_ table must contain the following fields:

* `id` _(primary key and index | auto increment)_
* `username` _(NOT NULL)_
* `email` _(NOT NULL)_
* `password` _(NOT NULL)_
* `first_name`
* `last_name`
* `linkedin`
* `github`

Optionally it can also have the following fields:

* `avatar` _(a fun picture of yourself or something else)_
* `created_at` _({tstamp}[timestamp] of the created entry | NOT NULL)_

NOTE: You can also add more fields if needs be.

==== Step 2: connect to the database

Now that you have a *database*, you should try to *connect* to it. Write the
basic PHP code to do just that.

.Example
[source,php]
----
function openConnection() {
	// Try to figure out what these should be for you
	$dbhost = "DB_HOST";
	$dbuser = "DB_USER";
	$dbpass = "DB_USER_PASSWORD";
	$db = "DB_NAME";

	// Try to understand what happens here 
	$pdo = new PDO("mysql:host=$dbhost;dbname=$db",$dbuser,$dbpass);
 
	// Why we do this here
	return $pdo;
}
----

If you search the web for how to connect to a database with PHP, you'll likely
face one of these three methods: _mysql_connect_, _mysqli_connect_ and _PDO_. 

Long story short, you shouldn't use _mysql_connect_ as it is *deprecated* by
_mysqli_connect_. For the rest, do some research to decide the one you want to
use.

==== Step 3: registration form

Create a _registration page_ where new user can register on your website. The
form should ask for these informations:

* `username`
* `email`
* `password`

Then insert a new row into the table _student_, the password should be
*encrypted*.

==== Step 4: login

Now for the funny part, add a way to *login* to the website. Check if the user
exist in the database and if his password is correct. Once connected display a
custom message with the _username_ or with the _name_ and _lastname_ if provided
(see next section).

NOTE: Once connected, the user must also be able to *disconnect*.

==== Step 5: modification page

Lastly make a _modification page_ from which the *connected user* will be able
to update his informations or delete them from the database all together.

=== Resources

* https://sqlbolt.com/[sqlbot]
* https://websitebeaver.com/php-pdo-vs-mysqli[pdo vs msqli]


== Congrats

With the help of _databases_ we can now add a sense of memory to our website. Do
you have ideas of new crazy projects yet?

image::https://media.giphy.com/media/2lVqM29dDcGM8/giphy.gif[]
