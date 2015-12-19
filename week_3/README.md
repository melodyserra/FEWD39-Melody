#Day 3 of FEWD 39!

##Today's Objectives

By the end of this lesson, you will be able to:

- Better understand how CSS is used to control layout. 
- Understand how CSS is used to position elements on the page. 
- Understand what CSS advanced selectors are and why they are useful. 

##Note on Stretch Exercises
- Stretch exercises are meant to challenge you. 
- These will be extra exercises that you may complete if you have time and want to try something a bit harder. 
- If completed they will not be graded and the solution will not be covered in class. 

##Review
- To review, we will be creating a mini-project. 
- Here are the steps you should follow:
	- Create a folder, call it "review"
	- Create your basic HTML document
	- Use a header tag, nav tag, aside tag, article tag, and footer tag. 


##CSS Positioning
- There are four main types of positioning that you will see most often - static, relative, absolute, and fixed.
- Static positioning is what all elements have by default. 
- Relative and absolute work together - elements can be positioned absolutely relative to their container.
- Fixed position elements are essentially absolute relative to the window no matter where they are in the DOM. A.K.A. the window is always the relative parent.

##Positioning Exercise
- Try to replicate the following mockups using what we've talked about in this class so far.
- Utilize margins, padding, floats, positioning, etc.

1. Stackers!

![Stackers!](img/stackers.png)

2. The Mirror

![The Mirror](img/the_mirror.png)

3. The Skinny - *Stretch Exercise*

![The Skinny](img/the_skinny.png)

4. The Absolute - *Stretch Exercise*

![The Absolute](img/the_absolute.png)

#Advanced CSS Selectors
- CSS has a lot of flexibility.
- You can achieve anything from advanced layouts to animations with CSS.
- Selectors are the first place to start when performing more advanced work with CSS.
- So far we have seen three types of selectors - class, ID, and element selectors.
- Let's take a look at the various selectors available to us [here on MDN](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) and [here on W3Schools](http://www.w3schools.com/cssref/css_selectors.asp).

##Pseudo-Class
- In CSS there is a concept called pseudo-classes that allow you do a little work with states and element subsets.
- The most popular is the hover pseudo-class:

```css
a {
	color:blue;
	font-size:1em;
	text-decoration:none;
}

a:hover {
	font-size:2em;
	color:red;
	text-decoration:none;
}
```

##CSS1 and CSS2 Selectors
- CSS1 and CSS2 are the older standards of CSS and have a lot of selectors that have since carried over to CSS3.

#####Nested elements

HTML

```html
<div class="container">
	<div></div>
	<div></div>
	<div></div>
</div>
```

CSS

```css
div div {
	width:200px;
	height:100px;
	background-color:red;
	border:#000 1px solid;
}
```

Same as:

```css
.container div {
	width:200px;
	height:100px;
	background-color:red;
	border:#000 1px solid;
}
```

#####Direct descendants
- These selectors help you select elements that are only a single DOM level down from the parent.

HTML

```html
<ul class="grocery-list">
	<li> Produce
		<ul>
			<li>Lettuce</li>
			<li>Tomatoes</li>
			<li>Oranges</li>
			<li>Bananas</li>
		</ul>
	</li>
	
	<li> Household
		<ul>
			<li>Soap</li>
			<li>Laundry detergent</li>
			<li>Paper towels</li>
		</ul>
	</li>
</ul>
```

CSS

```css
li {
	color:#000000;
}

.grocery-list > li {
	color:red;
}
```

#####Attributes

HTML

```html
<input type="text" name="email" />
<input type="text" name="address" />

<a href="http://google.com">Link to Google</a>
<a href="http://yahoo.com">Link to Yahoo!</a>
```

CSS

```css
input[name='address'] {
	width:100%;
	font-size:2em;
	border-radius:5px;
	display:block;
}

a[href='http://google.com'] {
	color:red;
	font-size:3em;
	text-decoration:none;
}
```

##CSS3 Selectors
- CSS3 is the newest version of CSS and gives us a ton of additional selectors and properties.
- These selectors and properties help us to accomplish advanced layouts.

#####:first-child, :last-child, :nth-child(n)

HTML

```html
<div class="container">
	<div></div>
	<div></div>
	<div></div>
</div>
```

CSS

```css
.container div {
	width:200px;
	height:100px;
}

.container div:first-child {
	background-color:red;
}

.container div:last-child {
	background-color:green;
}

.container div:nth-child(2) {
	background-color:orange;
}
```

#####:first-of-type, :last-of-type

HTML

```html
<div class="container">
	<p>
		Paragraph 1
	</p>
	<p>
		Paragraph 2
	</p>
	<p>
		Paragraph 3
	</p>
	<p>
		Paragraph 4
	</p>
	<div>
		Div 1
	</div>
	<div>
		Div 2
	</div>
</div>
```

CSS

```css
.container p:first-of-type {
	color:red;
}

.container p:last-of-type {
	color:orange;
}
```

##CSS Selector Exercise
- For this exercise we will be using the files [here](shakespeares_plays/).
- Select the `<ul>` with the ID "selected-plays" and place a gray background on it.
- Select the second and third `<h2>` elements (hint: they have classes) and make the font size larger and give them some space below.
- Change the background color of the third column of a table to gray.
- Select the `<li>` elements at the second level of the nested list and change the font color to red.
- Make every other table row in both tables have a gray background.
- Select an anchor tag that has a link to a pdf file. Change the color to blue and increase the font size.
- Select an anchor tag that has an href attribute containing the substring "asyoulikeit" and change the font color to orange.

##Homework
- Finish fashion blog
- Review CSS selectors
- Review documentation for [Twitter Bootstrap](http://getbootstrap.com/).
- Bonus: Go through the JavaScript sections of Dash.
