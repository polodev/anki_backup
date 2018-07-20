# 1 - Basic syntax
~~~js
$(selector).action()
~~~

# 2 - The Document Ready Event
~~~js
$(document).ready(function(){
 // jQuery methods go here...
});
// shorter
$(function(){
 // jQuery methods go here...
});
~~~

# 3 - Selects the first `<li>` element of the first `<ul>`

~~~js
$("ul li:first")	
~~~

# 4 - Selects the first `<li>` element of every `<ul>`
~~~js
$("ul li:first-child")	
~~~

# 5 - Selects all `<a>` elements with a target attribute value equal to `"_blank"`
~~~js
$("a[target='_blank']")	
~~~


# 6 - Selects all `<a>` elements with a target attribute value NOT equal to `"_blank"`
~~~js
$("a[target!='_blank']")	
~~~

# 6 - Selects all `<button>` elements and `<input>` elements of `type="button"`
~~~js
$(":button")	
~~~

# 7 - Mouse Events
* click
* dblclick
* mouseenter	
* mouseleave
* mousedown
* mouseup
* hover (combination of mouseenter and mouseleave)

# 8 - Keyboard Events
* keypress
* keydown
* keyup
* blur

# 9 - Form Events
* submit
* change
* focus (attaches an event handler function to an HTML form field)

# 10 - Document/Window Events
* load
* resize
* scroll
* unload

# 11 - Click method
~~~js
$("p").click(function(){
  $(this).hide();
});
~~~

# 12 - The on() Method
The on() method attaches one or more event handlers for the selected elements.
~~~js
$("p").on("click", function(){
  $(this).hide();
});
~~~

# 13 - multiple event handlers to a single element:
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

# 14 - hide in jquery

~~~js
$(selector).hide(speed,callback);

$("button").click(function(){
  $("p").hide(1000);
});
~~~


# 15 - show in jquery
~~~js
$(selector).show(speed_optional,callback_optional);

$("button").click(function(){
	$("p").hide(1000);
});
~~~

# 16 - jQuery toggle()
combination of hide() and show() method
~~~js
$(selector).toggle(speed,callback);

$("button").click(function(){
  $("p").toggle();
});
~~~

# 17 - jquery fade method

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

# 18 - jQuery Effects - Sliding

* slideDown() show the content
* slideUp() hide the content
* slideToggle()

~~~js
$(selector).slideDown(speed,callback);
$("#flip").click(function(){
  $("#panel").slideDown();
});
~~~

# 19 - jQuery Animations - The animate() Method
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

# 20 - jQuery animate() method with relative value `+=`
~~~js
$("button").click(function(){
  $("div").animate({
    left: '250px',
    height: '+=150px',
    width: '+=150px'
  });
}); 
~~~

# 21 - jQuery animate() - Using Pre-defined Values
~~~js
$("button").click(function(){
  $("div").animate({
    height: 'toggle'
  });
}); 
~~~

# 22 - jQuery animate() - Uses Queue Functionality
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

# 23 - jQuery stop() Method
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


# 24 - jQuery Method Chaining
there is a technique called chaining, that allows us to run multiple jQuery commands, one after the other, on the same element(s)
~~~js
$("#p1").css("color", "red").slideUp(2000).slideDown(2000);
//prettier format following - which should be preferred
$("#p1").css("color", "red")
	.slideUp(2000)
	.slideDown(2000);
~~~

# 24 - Get Content from HTML page
* text() - Sets or returns the text content of selected elements
* html() - Sets or returns the content of selected elements (including HTML markup)
* val() - Sets or returns the value of form fields

# 25 - how to get content with the jQuery text() and html() methods
~~~js
alert("Text: " + $("#test").text());
alert("HTML: " + $("#test").html());
~~~

# 26 - how to get the value of an input field with the jQuery val()
~~~html
<input type="text" id="test" value="Mickey Mouse"></p>
~~~
~~~js
$("button").click(function(){
  alert("Value: " + $("#test").val());
});
~~~

# 27 - Get Attributes - attr()
The jQuery attr() method is used to get attribute values.
~~~js
alert($("#w3s").attr("href"));
~~~

# 28 - Set Content - text(), html(), and val()
* text() - Sets or returns the text content of selected elements
* html() - Sets or returns the content of selected elements (including HTML markup)
* val() - Sets or returns the value of form fields
~~~js
$("#test2").html("<b>Hello world!</b>");
~~~

# 29 - A Callback Function for text(), html(), and val()
All of the three jQuery methods above: text(), html(), and val(), also come with a callback function. The callback function has two parameters: the index of the current element in the list of elements selected and the original (old) value. You then return the string you wish to use as the new value from the function.

~~~js
$("#test1").text(function(i, origText){
  return "Old text: " + origText + " New text: Hello world! (index: " + i + ")";
});
~~~

# 30 - Set Attributes - attr()
~~~js
$("#w3s").attr("href", "https://www.w3schools.com/jquery/");
// set multiple attribute using attr method
$("#w3s").attr({
	"href" : "https://www.w3schools.com/jquery/",
	"title" : "W3Schools jQuery Tutorial"
});
~~~

# 31 - A Callback Function for attr()
~~~js
$("#w3s").attr("href", function(i, origValue){
    return origValue + "/jquery/"; 
});
~~~

# 32 -  Add Elements
* append() - Inserts content at the end of the selected elements
* prepend() - Inserts content at the beginning of the selected elements
* after() - Inserts content after the selected elements
* before() - Inserts content before the selected elements
~~~js
$("p").append("Some appended text.");
function appendText() {
  var txt1 = "<p>Text.</p>";               // Create element with HTML  
  var txt2 = $("<p></p>").text("Text.");   // Create with jQuery
  var txt3 = document.createElement("p");  // Create with DOM
  txt3.innerHTML = "Text.";
  $("body").append(txt1, txt2, txt3);      // Append the new elements 
}
~~~

# 33 - Remove Elements
* remove() - Removes the selected element (and its child elements)
* empty() - Removes the child elements from the selected element    
~~~js
$("#div1").remove();
$("#div1").empty();
~~~

# 34 - jQuery Manipulating CSS
* addClass() - Adds one or more classes to the selected elements
* removeClass() - Removes one or more classes from the selected elements
* toggleClass() - Toggles between adding/removing classes from the selected elements
* css() - Sets or returns the style attribute

~~~js
$("button").click(function(){
  $("h1, h2, p").addClass("blue");
  $("div").addClass("important");
  // multiple class by giving space
  $("#div1").addClass("important blue");
  // remove class
  $("h1, h2, p").removeClass("blue");
});
~~~

# 35 - jQuery - css()
The css() method sets or returns one or more style properties for the selected elements.
~~~js
// return propertyname
css("propertyname");
//set property name
css("propertyname","value");
$("p").css("background-color", "yellow");

~~~

# 36 - Set Multiple CSS Properties
~~~js
css({"propertyname":"value","propertyname":"value",...});
$("p").css({"background-color": "yellow", "font-size": "200%"});

~~~

# 37 - jQuery Dimension Methods
* width()
* height()
* innerWidth()
* innerHeight()
* outerWidth()
* outerHeight()

![jquery dimension](https://www.w3schools.com/Jquery/img_jquerydim.gif)


# 38 - jquery width and height method
* The width() method sets or returns the width of an element (excludes padding, border and margin).
* The height() method sets or returns the height of an element (excludes padding, border and margin).
~~~js
$("button").click(function(){
    var txt = "";
    txt += "Width: " + $("#div1").width() + "</br>";
    txt += "Height: " + $("#div1").height();
    $("#div1").html(txt);
});
~~~


