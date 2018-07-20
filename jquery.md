# 1

### Basic syntax
~~~js
$(selector).action()
~~~

# 2

### The Document Ready Event
~~~js
$(document).ready(function(){
 // jQuery methods go here...
});
// shorter
$(function(){
 // jQuery methods go here...
});
~~~

# 3

### Selects the first `<li>` element of the first `<ul>`

~~~js
$("ul li:first")	
~~~

# 4

### Selects the first `<li>` element of every `<ul>`
~~~js
$("ul li:first-child")	
~~~

# 5

### Selects all `<a>` elements with a target attribute value equal to `"_blank"`
~~~js
$("a[target='_blank']")	
~~~


# 6

### Selects all `<a>` elements with a target attribute value NOT equal to `"_blank"`
~~~js
$("a[target!='_blank']")	
~~~

# 6

### Selects all `<button>` elements and `<input>` elements of `type="button"`
~~~js
$(":button")	
~~~

# 7 
### Mouse Events
* click
* dblclick
* mouseenter	
* mouseleave
* mousedown
* mouseup
* hover (combination of mouseenter and mouseleave)

# 8 
### Keyboard Events
* keypress
* keydown
* keyup
* blur

# 9
### Form Events	
* submit
* change
* focus (attaches an event handler function to an HTML form field)

# 10

### Document/Window Events
* load
* resize
* scroll
* unload

# 11
### Click method
~~~js
$("p").click(function(){
  $(this).hide();
});
~~~

# 12

### The on() Method
The on() method attaches one or more event handlers for the selected elements.
~~~js
$("p").on("click", function(){
  $(this).hide();
});
~~~

# 13

### multiple event handlers to a single element:
~~~js
$("p").on({
  mouseenter: function(){
    $(this).css("background-color", "lightgray");
  }, 
  mouseleave: function(){
    $(this).css("background-color", "lightblue");
  }, 
  click: function(){
    $(this).css("background-color", "yellow");
  } 
});
~~~

# 14 
### hide in jquery 

~~~js
$(selector).hide(speed,callback);

$("button").click(function(){
  $("p").hide(1000);
});
~~~


# 15
### show in jquery 
~~~js
$(selector).show(speed_optional,callback_optional);

$("button").click(function(){
	$("p").hide(1000);
});
~~~

# 16
### jQuery toggle()
combination of hide() and show() method
~~~js
$(selector).toggle(speed,callback);

$("button").click(function(){
  $("p").toggle();
});
~~~

# 17
### jquery fade method

* fadeIn() show the content 
* fadeOut() hide the content 
* fadeToggle()
* fadeTo()
~~~js
//syntax for fadeIn, fadeOut, fadeToggle
$(selector).fadeIn(speed,callback);

//syntax for fadeTo which taking 3 parameters
$(selector).fadeTo(speed,opacity,callback);
~~~

# 18
### jQuery Effects - Sliding

* slideDown() show the content
* slideUp() hide the content
* slideToggle()

~~~js
$(selector).slideDown(speed,callback);
$("#flip").click(function(){
  $("#panel").slideDown();
});
~~~

# 19
### jQuery Animations - The animate() Method
~~~js
$(selector).animate({params},speed,callback);
$("button").click(function(){
  $("div").animate({
    left: '250px',
    opacity: '0.5',
    height: '150px',
    width: '150px'
  });
}); 
~~~

# 20
### jQuery animate() method with relative value `+=`
~~~js
$("button").click(function(){
  $("div").animate({
    left: '250px',
    height: '+=150px',
    width: '+=150px'
  });
}); 
~~~

# 21
### jQuery animate() - Using Pre-defined Values
~~~js
$("button").click(function(){
  $("div").animate({
    height: 'toggle'
  });
}); 
~~~

# 22
### jQuery animate() - Uses Queue Functionality
if you write multiple animate() calls after each other, jQuery creates an "internal" queue with these method calls. Then it runs the animate calls ONE by ONE.     
~~~js
$("button").click(function(){
  var div = $("div");
  div.animate({height: '300px', opacity: '0.4'}, "slow");
  div.animate({width: '300px', opacity: '0.8'}, "slow");
  div.animate({height: '100px', opacity: '0.4'}, "slow");
  div.animate({width: '100px', opacity: '0.8'}, "slow");
});
~~~

# 23
### jQuery stop() Method
The jQuery stop() method is used to stop an animation or effect before it is finished.
~~~js
/**
 * stopAll parameter specifies whether also the 
 *  animation queue should be cleared or not.
 *  Default is false, which means that only
 *  the active animation will be stopped,
 *  allowing any queued animations to be
 *  performed afterwards.
 *
 *
 *  The optional goToEnd parameter
 *  specifies whether or not to complete
 *  the current animation immediately. 
 *  Default is false.
 * 
 */
$(selector).stop(stopAll,goToEnd);
$("#stop").click(function(){
  $("#panel").stop();
});
~~~


# 24
### jQuery Method Chaining
there is a technique called chaining, that allows us to run multiple jQuery commands, one after the other, on the same element(s)
~~~js
$("#p1").css("color", "red").slideUp(2000).slideDown(2000);
//prettier format following - which should be preferred
$("#p1").css("color", "red")
	.slideUp(2000)
	.slideDown(2000);
~~~

# 24
### Get Content from HTML page 
* text() - Sets or returns the text content of selected elements
* html() - Sets or returns the content of selected elements (including HTML markup)
* val() - Sets or returns the value of form fields

# 25
### how to get content with the jQuery text() and html() methods
~~~js
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});
~~~

# 26
### how to get the value of an input field with the jQuery val() 
~~~html
<input type="text" id="test" value="Mickey Mouse"></p>
~~~
~~~js
$("button").click(function(){
  alert("Value: " + $("#test").val());
});
~~~











