# Progressive enhancement

- Create a public repository: `progressive-enhancement`
- Slides: [Progressive Enhancement](https://app.ludus.one/8c042d9a-e404-4df5-b14e-48e3eb6e6014)
- Duration: 2 days



## 1. HTML is about semantics

What is "**semantics**" ?

A sentence is a series of words. A title is also a series of words. And so is a subtitle. How can a computer know which is which? Semantics is about marking up what a series of information is to be considered as. It adds hierarchy and structure to a text.  That's what HTML is for.

To make proper HTML code, one must think not about the looks of the text, but of its **structure** :sparkling_heart:.

**How ?** When writing html code, ask yourself this question: "*What is this series of words : a date ? A title? A paragraph? A legend? A caption describing an image ? And this series of sentences, is this a chapter ? A footnote  ?*" the answer to that question will tell you which HTML tag to best use to describe the content.

### Why is semantics so important ?

Two reasons :  **SEO** (your website's findability / visibility on Google) and **Accessibility** (make sure all humans, no matter their handicap (blindness, poor eyesight, colorblindness) can access the information.

#### 1.1 SEO

The ultimate goal of a search engine like Google is to return to a human the best possible results for what they have searched for (a few words). To do this, Google creates software such as **Googlebot**, which indexes content found on the web by following links from one page to another, from one site to another. (That's why we sometimes talk about *web spiders*).

Using powerful algorithms, Google reads and analyzes the HTML content of each page found, in order to "understand" what it is talking about thanks to its html structure (title, subtitle, list, etc.). This allows Google to determine what each page is about, and if it seems to match the search, it will return it to the user as one of the first results.

**Therefore, if our pages are not very semantic, Google will not show them, and your sites, no matter how cool they look and feel, will not have any traffic.**

> Findability Precedes Usability
> In the Alphabet and on the Web.
> You Can't Use What You Can't Find.
> – [Peter Morville](https://thatsthespir.it/quote/view/10)

#### 1.2 Accessibility
The web is a universal project: everyone must have access to content. Including the blind and visually impaired (you, one day). Blind people use "screen readers" that use html code to tell the story aloud. If your html code is not semantic, the page will not make much sense to listen to (even if it looks good). Feel free to[test on your own computer] (https://stackoverflow.com/a/43368748/53960).

### Semantic is actually pretty easy.

Semantics consists in choosing the right **tags** and **attributes** to represent your content. Do keep in mind that too much semantics hurts semantics. The rule (as often in programming) is:  **as little code as possible, but as much as necessary.**

#### Tags
Tags are used to indicate the semantic function of a portion of content in "blocks". Most html blocks work with an opening tag and a closing tag.

**Syntax example :**

```html
<p>This is a paragraph (hence the P letter).</p>
```

**Exercices :**

- Translate [this txt document](doc-the-chinese-farmer.txt) into semantic html, using the right html tags :  `h1`, `h2`, `blockquote`, `q`, `img`, `img`, `hr`, `figure` and `caption`, `table`, `th`, `tr`, `td`, `ul` or `ol` and`li`.
- No `div` or `span`: they do not provide any semantics.
- Find, for each of these tags, the origin of their name (that's how we remember them). If in doubt, look for the answer on [html5doctor.com](http://html5doctor.com).
- Add two or three links of your choice in the html page via the tag `a`
- Is there a part that could be considered as a header? If so, group it in a `header` tag.
- And a footer? If so, group this content together in a `footer` tag
- Put all instances of the words "Maybe" in a  `em` or `strong` tag.




#### Html attributes
They are used to define the characteristics of the tags.  Imagine that there is a "human" tag.

```html
<p>
Steven Paul Jobs, known as Steve Jobs, (San Francisco, February 24, 1955 - Palo Alto, October 5, 2011) is an entrepreneur...
</p>
```

We can, with attributes, describe this human being to differentiate him from others.

```html
<p class="human" name="Steve Job" nationality="USA" origin="Syria" job="CEO" company="Apple" hair="grey">
Steven Paul Jobs, known as Steve Jobs, (San Francisco, February 24, 1955 - Palo Alto, October 5, 2011) is an entrepreneur...
</p>
```

In this way, by increasing the semantics of the tags with attributes, we have clarified for a machine that is this human being.

Here is a one-line summary of the syntax of tags, attributes and values:

```html
<tag attribute="value">content</tag>
```

**Exercises :**

Back to your  html version of the Chinese farmer :

- Adds the attribute `Alt` to the images. What is the purpose of this attribute?
- Adds a "*good*" or "*bad*" class to the tags surrounding the words "Good" and "Bad".
- Find the link attribute to indicate the page to which the link should lead, and add it.
- Make sure that when you click on the links, the page opens in a new browser tab.
- Find the attribute to display a small text box when hovering over links, like this:

![Exemple](https://cdn.searchenginejournal.com/wp-content/uploads/2008/09/title-usability.jpg)

## 2. CSS is to improve the visual look

CSS is a computer language that allows you to control the visual aspect of your content.  For example, you can control the appearance of the text via these properties: `font-style`, `font-size`, `color`, `line-height`.

In other words, if html allows you to structure content, **CSS allows you to put some makeup on it**, making it more visually attractive.

### Syntax

```css
selector {
	property :  value ;
	property :  value ;
	/* This is a comment */
	property :  value ;
	...
}
```

**Remarks :**

- Each line must end with a `;`
- You can declare as many properties as you want. You can even declare the same property twice. In this case, the last one will be taken into account (hence the term "*cascading*").
- the stylized element is called "the selector". It is followed by a block containing one or more properties, enclosed in braces `{}`

**Example**: What do you think this piece of code does?

```css
p {
	font-size: 12px;
	font-family: Arial, sans-serif;
	color: purple;
}
```

For the browser to take it into account, your CSS must be either:

- in your html file, in a `<style>` tag
- in an external css file, linked to your html via the `<link>` tag


### Concept 1: CSS selectors

CSS selectors allow you to select in your html the content to be stylized via the tag containing it.


**Exercises :**

Back to your html version of the Chinese farmer :

- Style the paragraphs: use a Serif font, increase the spacing a little, use a basic size that makes it easy to read. Give the text a dark color, but not black.
- Style links so that they are easily readable.
- Style the "hover" and "visited" state of the links.

### Concept 2: block model

All tags are rendered visually as a "block". This is called the [box model](https://www.w3schools.com/css/css_boxmodel.asp).  Each block includes margin, padding border properties.

![The bloc](css-block.png)

You can control the dimensions and spacing of this block:

- `width`/ `height` : width and height dimensions
- Border: controls the border. For example: `border:1px solid #FF0000;` creates an edge made of a solid red line `#FF0000` and 1px thick
- `padding`: the space between the content of the block and its outline (the `border`). The padding "inflates" the block.
- Margin: the space around the block, outside it. The margin distances the block from its surroundings. You should know that these sometimes [collapse](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing) but for now you don't have to worry too much about it, just know it exists.


**Exercises :**

Back to your html version of the Chinese farmer :

- Give the body a maximum width of 90%.
- Then, center the body by playing with the `margin` property
- Make sure that the quotes are only half the pages width
- Using only the `margin` property, place the quotes in the middle.
- Increase the text size in quotations to 160% of the default text size
- Give a slightly greyish colour to the background of the quotations
- Add a 3px Firebrick border to the left of each quotation
- The text of the quotations touches the border, it's not pretty. Add a 30px space between the border and the text of the quotation.
- Make sure that the quotes have an empty space of 80 pixels above and below.
- Find out how to add a background color to your body
- Change the background color to use a color gradient (go to [http://www.colinkeany.com/blend/](http://www.colinkeany.com/blend/))
- Add a background image to your body
- Make sure that the image does not repeat itself
- Change its positioning to `bottom right`
- Changes its size to `cover`

### CSS selectors (part 2) :
#### The most important ones

Most often, the elements to be stylized are selected via the attribute `class` (`.name-of-class`) and `id` (`#name-of-lid`).

**Exercises**

Back to your html version of the Chinese farmer :

- Using only the tag as a selector, italicize all quotations.
- Identify the quotes of the villagers and the farmer by assigning each a corresponding class.
- Change the color of the left edge of the quotes according to the person speaking.

#### Select using parents and children elements

**Exercise**

Back to your html version of the Chinese farmer :

- Select an element of the `header` and gives it a yellow background (use the child selector)

#### All other selectors

-  `+` and `>`
-  	Select via the attribute `[attribute]`
-   There are a few others. To get an idea of what they allow, go read the [W3Schools documentation](https://www.w3schools.com/cssref/css_selectors.asp), then play with [CSS Dinner](http://flukeout.github.io/)

**Exercises**

Back to your html version of the Chinese farmer :

- Italics the text of the quotations
- Capitalize all instances of the words "good" and "bad".
- Put the words "Bad" in red
- Put the words "Good" in green
- Style the table so that the background color of each row is alternating grey or white
- At the first item in the list (types of people), play with `background-image` and `padding-right` to make the image appear ![good](bien.png)
- At the second item of the list (types of people), play with `background-image` and `padding-right` to make the image appear ![wrong](mal.png)
- At the third item of the list (types of people), play with `background-image` and `padding-right` to make the image appear ![chat](chat.png)
- Put the first paragraph in bold


### Concept 3: CSS positioning
CSS allows you to define the visual positioning of the elements. It is probably the richest and therefore the most complex system, because the ways of controlling positioning has had a rather complicated history. It was long ago necessary to use *hacks*. Things are more stable now, especially if you don't have to support users stuck on internet explorer 9....  But let's start over from the beginning.

#### Understanding the Browser Rendering flow

Each html block has a "display" property which is either: `display: inline | inline-block | block` and is displayed according to its order of appearance in the html file. This is called the **natural positioning flow** or more simply the **flow**.

![Display explained](http://4.bp.blogspot.com/-TiwOixlooJk/U4UyEnv_XpI/AAAAAAAACFs/NuuLz2IvoZ4/s1600/css-display-block-vs-inline-block.png)

##### The flexbox model
Flexbox is the commonly-used name for the CSS Flexible Box Layout Module, a layout model for displaying items in a single dimension — as a row or as a column.

In the specification, Flexbox is described as a layout model for user interface design. The key feature of Flexbox is the fact that items in a flex layout can grow and shrink. Space can be assigned to the items themselves, or distributed between or around the items.

Flexbox also enables alignment of items on the main or cross axis, thus providing a high level of control over the size and alignment of a group of items.

- [The flexbox model summary (FR)](https://developer.mozilla.org/fr/docs/Apprendre/CSS/CSS_layout/Flexbox)
- [The properties explained (FR)](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Flexible_Box_Layout/Concepts_de_base_flexbox)

**Exercise :**

Back to your html version of the Chinese farmer :

- Make the text run around the images, using the `flexbox model` property on the images (adjusted with `justify-content` to distance the text from the image).

![flexbox](flexdisplay.png)

#### Breaking the flow

The flow is the default behavior. You may need an element to exit the position flow.

`position : static | relative | absolute | fixed ;`

The `position` property allows you to position an element anywhere (via the `top` and `left` properties), from the coordinates of its first parent in `position: relative` or `static`. [Experiment via this Pen](https://codepen.io/pixeline/pen/vmzNjw?).

**Exercises :**

- [Put the notification block in the bottom right corner of the browser, even if you scroll](https://codepen.io/pixeline/pen/dWqMxe)

#### Going further
More information on CSS positioning: http://learnlayout.com

## 3. Web fonts

By default, the browser uses the fonts installed on the client's computer. However, you can use specific fonts: the **webfonts**.

**Exercises :**

- Visit [Google Webfonts](https://fonts.google.com/): changes the font of your document to this one: Open Sans.

## 4. Useful tools

- Removes the default css used by browsers ([reset.css](https://www.alsacreations.com/astuce/lire/36-reset-css.html)), or leaves on a normalized basis ([normalize.css](https://github.com/necolas/normalize.css))
- Check that your HTML is **valid** via the [w3c validator](https://validator.w3.org/)
- Check that your HTML allows **good organic SEO**, via other tools like the [Google Lighthouse Test](https://developers.google.com/web/tools/lighthouse/)
- Install [Emmet](https://emmet.io/) in your code editor.

## 5. Exercises to finish this sprint
If you have the time...
- Reproduce as accurately as possible the following layouts:
	- [homepage of turlututu.com](turlututu.png)
	- [CodeCollab homepage](activecollab.png)
Create a repository for each project. Do not forget the description, the URL of the GitHub Page and the readme!

## Done ?
HURRAY, here is a gif !

![](win.gif)

:sparkling_heart:
