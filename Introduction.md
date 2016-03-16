# Introduction

## HTML
A barebones example of HTML code is below: 

	<!DOCTYPE html>
	<html>
	<head>
		<title></title>
	</head>
	<body>
	
	</body>
	</html>

HTML consists of a collection of nested tags (words in between angle brackets) that are used to create an information hierarchy. The end of a tag is indicated by adding a "/" to the beginning of a copy of the original tag.  
<code><!DOCTYPE html></code> tells the browser that we want to use HTML5 (the current standard), not a previous version.   
Besides the DOCTYPE declaration, the outermost HTML tag is "html". The first children, or nested elements, of the html tag are "head" and "body".
  
A website's head can contain the following information:
  
* **title**: The title contains the text you see at the top of a tab
* **favicon**: Not shown here, the favicon references the little image to the left of a page's title
* **meta**: Meta tags contain information viewable by search engines and web scrapers, but not by humans (unless they inspect the website's source code)
* **script and link tags**: The head tag can also contain links to [JavaScript](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) and [CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) files used by the site.

A website's body contains all of the information you, a user, sees. There are a number of different popular tags used within a website's body, including but not limited to:

* **div**: A basic building block of web content. Divs can contain any other type of tag, including other divs
* **Headers**: Headers provide default styling for text. The tags from largest to smallest are h1, h2, h3, h4, h5 and h6
* **p**: Paragraph tags contain text and provide a margin below to separate following information
* **span**: Contains text, but does not provide spacing like p tags
* **Lists**: Lists come in two varieties: ordered (tag: ol) and unordered (tag: ul). Ordered lists by default display numbers, whereas unordered lists display bullet points. The elements of each list are contained within li tags
* **Semantic Elements**: The HTML5 specification includes new semantic elements, aka tag names that sound like what they do. Here's a [list](http://www.htmlgoodies.com/tutorials/html5/new-tags-in-html5.html) of the tags if you're interested.

## CSS
You might be wondering how you can use CSS to style HTML. The answer is with tags, classes and ids.  

Let's take the previous HTML skeleton code and add some content to it:

	<!DOCTYPE html>
	<html>
	<head>
		<title></title>
	</head>
	<body>
		<p class="sentence" id="first">Hello</p>
		<p class="sentence" id="second">World</p>
	</body>
	</html>
	
