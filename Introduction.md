# Introduction

## HTML
A barebones example of HTML code is below: 

~~~html
	<!DOCTYPE html>
	<html>
	<head>
		<title></title>
	</head>
	<body>
	
	</body>
	</html>
~~~

HTML consists of a collection of nested tags (words in between angle brackets) that are used to create an information hierarchy. The end of a tag is indicated by adding a "/" to the beginning of a copy of the original tag. HTML files are saved using a .html extension.  
 
<code><!DOCTYPE html></code> tells the browser that we want to use HTML5 (the current standard), not a previous version.   

Besides the DOCTYPE declaration, the outermost HTML tag is "html". The first children, or nested elements, of the html tag are "head" and "body".
  
A website's head can contain the following information:
  
* **title**: The title contains the text you see at the top of a tab
* **favicon**: Not shown here, the favicon references the little image to the left of a page's title
* **meta**: Meta tags contain information viewable by search engines and web scrapers, but not by humans (unless they inspect the website's source code)
* **script and link tags**: The head tag can also contain links to [JavaScript](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) and [CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) files used by the site.

A website's body contains all of the information you, a user, sees. There are a number of different popular tags used within a website's body, including but not limited to:

* **div**: A basic building block of web content. [Divs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) can contain any other type of tag, including other divs
* **Headers**: [Headers](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) provide default styling for text. The tags from largest to smallest are h1, h2, h3, h4, h5 and h6
* **p**: [Paragraph](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) tags contain text and provide a margin below to separate following information
* **span**: [Spans](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) contain text, but do not provide spacing like p tags
* **Lists**: Lists come in two varieties: [ordered](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) (tag: ol) and [unordered](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) (tag: ul). Ordered lists by default display numbers, whereas unordered lists display bullet points. The elements of each list are contained within li tags
* **Semantic Elements**: The HTML5 specification includes new semantic elements, aka tag names that sound like what they do. Here's an [explanation](http://www.htmlgoodies.com/tutorials/html5/new-tags-in-html5.html) of the tags if you're interested.

## CSS
You might be wondering how you can use CSS to style HTML. The answer is with tags, classes and ids.  

Let's take the previous HTML skeleton code and add some content to it:

~~~html
	<!DOCTYPE html>
	<html>
	<head>
		<title></title>
	</head>
	<body>
		<p class="word" id="first">Hello</p>
		<p class="word another-word" id="second">World,</p>
		<p>I'm a dolphin.</p>
	</body>
	</html>
~~~
	
**Classes**, denoted by text inside of quotes, following <code>class=</code>, are tag attributes used to identify a group of tags that should look or behave a certain way. Multiple classes can be added to a single tag by adding spaces between them, such as in the second p tag (in this case, a hyphen is used in lieu of a space between 'another' and 'word' as to not make the words themselves separate classes).  

**ids** are denoted similarly to classes, but there should only be one of each on a page. Each id should uniquely identify a single, specific tag.

By default, this page represented by the code above will display something like:  

Hello  
World,  
I'm a dolphin.  

But what if instead of using default style, we want to make the page background blue, the text white, and add special styling to the first two p tags? We'll need to use some CSS. CSS files are saved using a .css extension. 

Let's begin by making the background blue (you can follow along by copying this code into your own editor. If you are unsure of how to link your CSS to your HTML, [Google it](https://www.google.com/search?q=how+to+link+a+css+file+to+html&oq=how+to+link+a+css+file+to+html&aqs=chrome..69i57j0l5.6664j0j1&sourceid=chrome&es_sm=119&ie=UTF-8)). Since we're not styling any p tag in particular, we can assign this style to the body itself:   

~~~css
	body {
		background-color: blue;
	}
~~~

CSS style is organized by selecting a tag, class, or id (or combination of the three!) and placing it in front of a set of curly braces. In the example above, "background-color" is a CSS property, and "blue" is its definition. Properties must be immediately followed by a colon (:), and definitions must precede a semicolor (;).

 To make all of the text white, we'll need to style our p tags:

~~~css
	p {
		color: white;
	}
~~~

If we look back to the HTML, we'll see that although the first two p elements (tag + content) share the "word" class, the third does not. This means we can use CSS to select the "word" class and apply styling just to those first two elements:

~~~css
	.word {
		font-weight: bold;
	}
~~~

When selecting classes in CSS, precede the class name with a period.  

If you've been following along, you'll see the HTML represented as white text on a blue background (at least surrounding the paragraphs), and the first two paragraphs are bold. If we want to add some decoration to the text, but make it unique to each of the first two p elements, we can use their ids:

~~~css
	#first {
		text-decoration: underline;
	}
	#second {
		text-decoration: line-through;
	}
~~~

When selecting ids in CSS, precede the id name with a hash symbol. Now the word "Hello" will be underlined and "World," will have a strikethrough.  

There are a number of other ways to select HTML elements with CSS, and hundreds of other properties you can use to style them. Once you feel comfortable with these basics, move onto Week 1's lesson.