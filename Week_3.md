# Week 3: Positioning

As you've researched the web for navigation and grids, you may have come across examples in which text or other HTML elements appear to be stacked on top of one another, or stick to one part of the page regardless of scroll location. This is accomplished by using the ```position``` and / or ```z-index``` CSS properties.

```position``` can take the following values:  

* ```static```
* ```relative```
* `fixed`
* ```absolute```

HTML elements are assigned ```position: static;``` by default. Static positioning follows the normal flow of the page. This means that static elements are positioned one after the other. If you want to move around static elements, you use properties such as `margin` you've learned in the past couple of weeks. These properties position your element relative to *other* elements.

If you add the CSS `position: relative;` to an element, it will be positioned relative to its normal (static) position. The following properties are used to position an element relative to where it would be if was static:

* `top`
* `right`
* `bottom`
* `left`

Setting these properties will not work unless the `position` is set in a prior line. For example,

```css
div {
	position: relative;
	top: 100px;
	left: 50px;
}
```

will work, but the following will not reposition:

```css
div {
	top: 100px;
	left: 50px;
	position: relative;
}
```

If you add the CSS `position: fixed;` to an element, it will stay in place on the page regardless of scrolling. It uses `top`, `right`, `bottom` and `left` for positioning as well, but instead of being relative to its normal positioning, these properties arrange it relative to the viewport (page). For example,

```html
<div class="top-navigation"></div>
```
```css
.top-navigation {
	position: fixed;
	top: 0px;
}
```

will create a navigation that sticks to the top of the page.

Adding `position: absolute;` to an element will position it relative to its nearest ancestor (prior) element that is positioned with a value other than `static`. For example, 

```html
<div class="outer">
	<div class="inner">I'm absolute!</div>
</div>
```

```css
.outer {
	position: relative;
	height: 100px;
}

.inner {
	position: absolute;
	top: 50px;
}
```

will position the `div.inner` element `50px` lower than the position of `div.outer`. 

An absolute-positioned element can be nested within a parent that has `position: fixed;`.

When elements are assigned non-static positioning but are not moved away from one another, they will stack up. Normally, the last non-static element will be on the top of the stack. If you want to control which elements are located on top of one another, you use the `z-index` property. 

`z-index` can take any integer value. If an element's `z-index` value is larger than that of another element's, the element with the larger `z-index` will be stacked on top of the other element. For example,

```html
<div class="outer">
	<div class="inner" id="first">
	<div class="inner" id="second">
</div>
```
```css
.outer {
	position: relative;
}

.inner {
	position: absolute;
}
```

will make `div.inner#second` stack on top of `div.inner#first`. However, if we wanted to reverse that stacking order, we could do the following:

```css
#first {
	z-index: 2;
}

#second {
	z-index: 1;
}
```

Since 2 > 1, `div.inner#first` will now be stacked on top of `div.inner#second`.

Alternatively, a negative `z-index` value will position an element behind another with a larger value. If you're interested in learning more about `z-index`, I suggest [this article](http://philipwalton.com/articles/what-no-one-told-you-about-z-index/).

