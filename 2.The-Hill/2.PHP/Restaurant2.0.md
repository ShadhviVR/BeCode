# Restaurant 2.0

Type of challenge: **learning**

Duration: **5 days**

Team challenge: **solo**

## Learning objectives

At the end of this challenge, depending on what you completed, you should be able to:

- Make a Form and manage messages via an interface
- View and manage a guestbook
- Display an image gallery dynamically
- Use an API
- Deploy a project in php

## The mission

Once upon a time **you made a website** for a restaurant franchise. Now and after hearing about the wonderful work you did the owner is calling you back to implement new features and **improve the website**.

Sadly, he can only pay you for a week of work, which **won’t be enough time** to implement all his ideas. Hopefully, he’s ready to make compromises, you have to **implement as much as you can** in the given time.

## Instructions

- take back your old [project](https://github.com/becodeorg/BXL-Swartz-4-27/blob/master/1.The-Field/6.Bootstrap/restaurant.adoc)
- implement at least one new feature
- improve the design (if you have time)
- use whatever technology you want

| Note | You don’t have to fill any form for this project, as it’s a learning challenge. However, if you feel it could unlock **badges** you can try to claim them with it. |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|      |                                                                                                                                                                    |

### Features

#### Back office

One of the idea the owner had was to implement a "Back office" to the website. The objective is to receive all the messages from the form on a single page to facilitate the work of marketing and communication. From this interface you can **view** the messages and **delete** them.

Something like that

![](deletemessage.png)

#### Guest book

The owner would like to have a new [guest book](https://en.wikipedia.org/wiki/Guestbook) page to receive comments, kind words or advice from the customers. However, it ideally need to be made with the **google sheet API** to allow the owner to check everything directly from his _google account_.

**If you find that it is too early to take an interest in API's you can proceed as for the previous form and use your database.**

The form should at least contain:

- customer name
- visited restaurant
- visit date
- comment (optional input)

#### Bonus

Use only one page to manage messages and the guestbook

![](backofficeX2.png)

#### Gallery

For the moment the images in your gallery are not dynamic. To add a photo you must add them one by one in your html code. What if I told you "Hey marketing and communications hired a photographer, there are 4000 photos to add to the gallery!"?

The objective is twofold. First create a page to upload images.
Secondly create a php script that allows you to display the images (Normally the front of your gallery does not change).

#### Bonus

Use only one page to manage messages, guestbook and gallery

![](backofficeIMG.png)

#### Deploy

This is the opportunity to deploy your project. As you have probably noticed, github does not allow php hosting. There are free solutions. It's up to you to find them and share them with your colleagues!

### Resources

- [composer](https://getcomposer.org/)
- [add composer on a docker image](https://tinyurl.com/yxda5q7o)
- [google sheet API](https://developers.google.com/sheets/api/quickstart/php)

## Congrats

It’s alright the world isn’t on fire, you might just be flooded with things to do. So what, one thing at a time.

[![giphy](https://camo.githubusercontent.com/81248d4b3e370e2b55d85b260099725374b154e5a06ad06a06e6dc15a4c3ab96/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f316a597968734f646d4c394e7138426d4b702f67697068792e676966)](https://camo.githubusercontent.com/81248d4b3e370e2b55d85b260099725374b154e5a06ad06a06e6dc15a4c3ab96/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f316a597968734f646d4c394e7138426d4b702f67697068792e676966)
