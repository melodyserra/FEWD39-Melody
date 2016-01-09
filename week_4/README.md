#Day 4 of FEWD 39!

##Some tactics we will implement as we reach the halfway mark:
a. "Ask three, then me."


b. "Glow" & "Grow"

c. Divide in to teams and come up with a team name. Your team will be your go-to resource in class and to help you solve problems on homework. 


##Today's Objectives

By the end of this lesson, you will be able to:

- Better understand how CSS is used to control layout. 
- Understand how to use the Bootstrap Framework. 
- Understand what responsive web design means and how it can be accomplished. 

#Let's start 2016 by building!
- We will be building our very own about-me website from scratch. 
- This is meant to be creative, but make sure to at least do the following:
	- There are a series of instructions in the form of comments, please start by following those directions. 
	- Add the class "fixed-top" to the header to make it stay in place during scroll.
	- Use rgba colors to make the header navbar semi-transparent.
	- Use Google Fonts to implement a font of your choice for the logo.
	- Replace the picture of me with one of you :) 
	- Replace the picture of the motorcycle with a background of your choice (Hint: Have a look at the CSS to find out where this background comes from).
	- Make the background of the banner have a parallax effect. Hint: Research the "background-attachment" property in CSS.
	- Change the text throughout the page to reflect your own personal information.
	- Add a gradient to the background of the user-info-text class in CSS.
	- **Bonus:** Implement a small animation using CSS somewhere on the page. You may want to research the `transition` and `transform` CSS properties.
- We will be discussing how to make this web page live using a service called BitBalloon.

#Advanced Layout

##Why We Care
- Advanced layout doesn't have to mean hard layout.
- Most of the difficult work done with layout is done using frameworks.
- Frameworks remove many burdens to frontend development including generic grids, mobile responsiveness via media queries, and starter UI elements.

##Grid Refresher
- Grids are the standard way of laying out content on the web.
- Most grid systems operate on a 12-column grid.
- Grid sizes can be thought of in terms of grid place offsets. For example, two blocks of content next to each other is two columns of 6. 4 across is an offset of 3.
- Grid offset numbers must add up to 12.

##Twitter Bootstrap
- Bootstrap is a front-end framework that incorporates a grid system, UI components, JavaScript widgets and more.
- Let's take a look at the documentation: [http://getbootstrap.com](http://getbootstrap.com/).
- The framework consists of one main CSS file, an optional theme CSS file, and a main JS file.
- Bootstrap requires jQuery to work, which is a JavaScript framework.

##Using Bootstrap
- To use Bootstrap you have to include the three required files.
- Bootstrap files can be linked via the CDN provided, or downloaded locally onto the computer.
- Remember to place your reference to the jQuery library above your reference to the Bootstrap JS code.

##Bootstrap Columns
- Columns are written in this format as a class attribute: col-(breakpoint)-(offset).
- An example of a three-column layout may be to use the class col-sm-4.
- All columns should be wrapped into an element with a class of row.
- So the complete three-column layout may look something like this:

```
<div class="row">
	<div class="col-sm-4">
		Content Here
	</div>
	<div class="col-sm-4">
		Content Here
	</div>
	<div class="col-sm-4">
		Content Here
	</div>
</div>
```

##Breakpoints
- The way that Bootstrap works is to dynamically reduce column size according to the window size.
- To be mobile-friendly, the columns will break into a stack layout after a minimum width is detected.
- The breakpoints you can select in your columns control at which point this happens.
- Check out their documentation [here](http://getbootstrap.com/css/#grid) to see what these breakpoints are in terms of size.

##CSS3 Media Queries
- Media queries allow you to apply and remove CSS styling based on the screen dimensions.
- This is important to create truly mobile-friendly layouts.
- To use it you have to specify screen resolution thresholds.
- Let's try an example where we want to show a div where the screen size is larger than 700 pixels:

HTML

```
<div id="my-div"></div>
```

CSS

```
@media(min-width: 700px) {
	#my-div {
		width:400px;
		height:400px;
		border:#000 1px solid;
		background-color:red;
	}
}
```

- Now where the screen size is below 700 pixels:

CSS

```
@media(max-width: 700px) {
	#my-div {
		width:400px;
		height:400px;
		border:#000 1px solid;
	}
}
```

- You can also combine these values to select a range:

```
@media(min-width: 700px) and (max-width: 900px) {
	#my-div {
		width:400px;
		height:400px;
		border:#000 1px solid;
	}
}
```

- Good news! Bootstrap does this for you!

##Code-Along
- Let's see the grid system in action.
- We will be coding the Bootstrap grid example:

![Grid Example](img/grid_template.png)

- Let's also make sure to practice using different breakpoints.

##UI Elements
- Bootstrap wraps in a myriad of great UI elements that you can drop in anywhere on your site.
- With Bootstrap you can make really pretty things quickly.
- Let's look at some [examples](http://getbootstrap.com/components/).

##Putting it Together
- Let's take a look at some of the bootstrap examples located [here](http://getbootstrap.com/getting-started/#examples).
- We will code together the "Jumbotron Narrow" template located [here](http://getbootstrap.com/examples/jumbotron-narrow/).
- Before we start, let's also plan out our grid system.

##In-Class / Homework
- For homework we will be coding from scratch [this Bootstrap template](http://getbootstrap.com/examples/offcanvas/) and adding our own creative spin to it.
- Try not to look at the code through the code inspector! X-(
- Try to first plan out the grid you will use, then figure out which components you will need.
- Go through the JavaScript exercises on [Codecademy](http://www.codecademy.com/).