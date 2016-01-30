#Day 7 of FEWD 39!

#DOM, Event Listeners, and jQuery

##Today's Objectives

By the end of this lesson, you will be able to:

- Have a deeper understanding of DOM manipulation. 
- Understand event listeners conceptually and practically. 
- Understand what JQuery is and how to use it. 

##Review on DOM Manipulation
- One of the most powerful features of JS is its ability to alter the DOM.
- You can respond to events on elements, set HTML dynamically, and perform animations.

##Selecting Elements
- Like CSS, if you want to perform some action on an element you first have to select it.
- We did this in CSS through selectors such as IDs, classes, and pseudo-selectors.
- JavaScript gives us an easy way to select elements based on the same paradigm.

####querySelector()

```
document.querySelector("#my-div");
```

####querySelectorAll() 

```
document.querySelectorAll(".my-class");
```
- Look up what this returns.

##setAttribute()
- JavaScript gives you the ability to dynamically alter HTML element attributes on the fly.
- This may be used to change stylistic properties such as the background color:

```javascript
document.querySelector("#my-id").setAttribute("style", "background-color: red;");
```

##classList
- If you want to alter many style properties at one time, consider wrapping your properties up as a CSS class.
- JavaScript gives us access to an element's classes so we can manipulate them:

Add:

```javascript
document.querySelector("#my-div").classList.add("animation");
```

Remove:

```javascript
document.querySelector("#my-div").classList.remove("animation");
```

Toggle:

```javascript
document.querySelector("#my-div").classList.toggle("animation");
```

##innerHTML
- When you need to replace the HTML inside of an element you can use the `innerHTML` property.

```
document.querySelector("#my-div").innerHTML = "<span>New HTML here</span>";
```

##Handling Events
- There are many events you may want to respond to with JS including clicks, mouseovers, focuses, etc.
- Events can be listened for and responded to using `addEventListener`.

```
document.querySelector("#my-div").addEventListener("click", function() {
	alert("Click worked!");
});
```

- If you need to handle an event that occurs on many elements you will need to attach event listeners to each element individually.
- This can be done by binding the event to a class. Let's take this example:

####index.html

```
<div class="my-div"></div>
<div class="my-div"></div>
<div class="my-div"></div>
```

####app.js

```
var myElements = document.querySelectorAll(".my-div");

for (var i = 0; i < myElements.length; i++) {
	myElements[i].addEventListener("click", function() {
		alert("Click worked!");
	});
}
```

##Score Keeper Lab Code Along
- We will be creating a simple score keeper application using JavaScript.
- The HTML and CSS has already been done for you [here](score_keeper_html/).
- Here are the steps you should take:
	- Step 1: Add a link to your own custom JS file before the closing body tag.
	- Step 2: Bind click events to the +5 and -5 point buttons and change the innerHTML of the score display appropriately.
	- Step 3: Bind a click event to the set score button and set the innerHTML of the score display to the score entered in the text box. You will need to use the `parseInt` function in JS to make this work.
	- **Bonus:** Create a check in your code to make sure the score will not go negative.
	- **Super Bonus:** Create a function to make the changes to the score display rather than having to write your logic over and over.

## In-Class Lab #5: Calculator
In this exercise:

* user will enter in numbers in the first two input boxes
* user then "clicks" on one the math signs ( +, -, *, /)
* result of the calculation will appear after the " = " sign 
* __*hint__ the "input" element does not have a property called "textContent", it has a property called "value"

#Introduction to jQuery

##What is jQuery?

jQuery is a cross-browser JavaScript library designed to simplify the client-side scripting of HTML.

It helps us out with:
- DOM traversal
- CSS manipulation through `style` attributes
- Event handling
- Animation
- And much more

##How to Use jQuery
- jQuery is available via CDN at `code.jquery.com`
- You can also download the library and serve it locally
- jQuery by itself is a library of functions. The team has also built additional tools that help us with a variety of things:
	- jQuery UI: A UI tool that adds features such as additional easings, a datepicker, modals, effects, and more.
	- jQuery Mobile: A mobile-optimized framework that allows you to create HTML5 mobile applications that look and act pretty real.

##jQuery Selectors
- The Sizzle selector engine wrapped into jQuery is a powerful tool to help us with manipulating DOM elements.
- The syntax is very similar to CSS:

```
$("#myDiv > ul > li:first-child")
```

- Here the $ sign represents the jQuery library.
- Let's take a look at some of the selectors available to us [here](http://www.w3schools.com/jquery/jquery_ref_selectors.asp).

##jQuery Actions
- Actions almost always follow selectors.
- Actions are jQuery functions that perform an operation on the element(s) selected.
- The format is as follows:

```
$("my-selector").action(options);
```

##DOM Manipulation
- The DOM manipulation functions in jQuery help you accomplish some pretty neat things.
- Here are a few common manipulations you will likely see:

On the fly HTML manipulations:

```
$("my-selector").html("New HTML inside here");
```

On the fly CSS manipulations:

```
$("my-selector").css("property", "value");
```


Altering CSS class attributes:

```
$("my-selector").addClass("new class");

$("my-selector").removeClass("class");

$("my-selector").toggleClass("class");
```

##Event Handling
- Event handling is done very smoothly with jQuery.
- There are a few different ways it can be performed, each having their use cases.
- Let's say we have a button and want to attach an event:

HTML

```
<button id="my-button">Click Me!</button>
```

jQuery

- This is what I like to call the shortcut method.
- It has the limitation of not working when the DOM element doesn't already exist.

```
$("#my-button").click(function() { //Your code here });
```

- You can also bind events using `.on`
- This is also limited to elements that already exist, but it is a better approach.

```
$("#my-button").on("click", function() { //Your code here });
```

- Lastly, you can account for dynamic elements through binding the event to the document itself.
- This also happens to be the most performant if you look at benchmark tests.

```
$(document).on("click", "#my-button", function() { //Your code here });
```

- Here is a list of the most common events you are likely to see:
	- Click
	- Keyup
	- Keydown
	- Mouseenter
	- Mouseleave
	- Dblclick
	- Change


##jQuery Animations
- jQuery wraps in some neat animations that help us achieve some interesting effects.
- jQuery animations work by altering the `style` attribute dynamically over a set period of time.
- These animations are great but less performant than CSS3 animations, which are hardware-accelerated.
- Here are a few common animations you will see:

Slide down (show the element):

```
$("my-selector").slideDown();
```

Slide up (hide the element):

```
$("my-selector").slideUp();
```

Slide toggle (back and forth):

```
$("my-selector").slideToggle();
```

Fade in:

```
$("my-selector").fadeIn();
```

Fade out:

```
$("my-selector").fadeOut();
```

Fade toggle (back and forth):

```
$("my-selector").fadeToggle();
```

- Each of these animation functions take three parameters: duration, easing, and callback function to be completed when the animation is complete.

##Custom Animations
- If none of the built-in animations suit you, jQuery also gives you a way to create your own animations.
- This function will dynamically alter the `style` attribute in the HTML document for each property you specify:

```
$("my-selector").animate({
	"margin-top":"200px",
	"margin-left":"+=200px"
}, 600, "swing", function() {
	console.log("I just finished!");
});
```

##Animation Exercise: Gettysburg Address Homework
- Download the exercise files [here](gettysburg_address/).
- Alter the stylesheet to hide the contents of the page initially. When the page is loaded, fade in the contents slowly.
- Give each paragraph a yellow background only when the mouse is over it.
- Make a click of the title (`<h2>`) and simultaneously fade it to 25 percent opacity and grow its left-hand margin to 20px. Then, when this animation is complete, fade the speech text to 50 percent opacity.
- Bonus: Make the style switcher work.
- Challenge: React to presses of the arrow keys by smoothly moving the switcher box 20 pixels in the corresponding direction. The key codes for the arrow keys are: 37 (left), 38 (up), 39 (right), and 40 (down).

