
# Jquery Built in Fucntions and Trick 

1- jqyery Built In Functionalties 


$("*") 	Selects all elements 	
$(this) 	Selects the current HTML element 	
$("p.intro") 	Selects all <p> elements with class="intro" 	
$("p:first") 	Selects the first <p> element 	
$("ul li:first") 	Selects the first <li> element of the first <ul> 	
$("ul li:first-child") 	Selects the first <li> element of every <ul> 	
$("[href]") 	Selects all elements with an href attribute 	
$("a[target='_blank']") 	Selects all <a> elements with a target attribute value equal to "_blank" 	
$("a[target!='_blank']") 	Selects all <a> elements with a target attribute value NOT equal to "_blank" 	
$(":button") 	Selects all <button> elements and <input> elements of type="button" 	
$("tr:even") 	Selects all even <tr> elements 	
$("tr:odd")

DES: Use Functions According to your Need   

<br>
2- Event On Different Moves 

MouseEvents Keyboard Events   Form Events  Document/Window Events
click 		keypress 	           submit 		load
dblclick 	keydown 	           change 		resize
mouseenter 	keyup 		         focus 	   	scroll
mouseleave 	                   blur 	   	unload



<br>
3- Calling Back Function 
 
 <script>
$(document).ready(function(){
  $("button").click(function(){
    $("p").hide("slow",function(){
      alert("The paragraph is now hidden");
    });
  });
});
</script>

DES : First Excute the First Function after Compltion of First execute the next one 

<br>
4- Chaining Functions 

-  $("#p1").css("color","red"); Implment Any Style

<script>
$(document).ready(function()
  {
  $("button").click(function(){
    $("#p1").css("color","red").slideUp(2000).slideDown(2000);
  });
});
</script>

DES : Allow you to call many function with in same line of code and Also the Way you can Implment the different Function to the Div element.


<br>
5- Add and Remove the css properties and Classess

$("p").css("background-color","yellow"); 


    addClass() - Adds one or more classes to the selected elements
    removeClass() - Removes one or more classes from the selected elements
    toggleClass() - Toggles between adding/removing classes from the selected elements
    css() - Sets or returns the style attribute
    
    

<br>
6- Combine The Value of varibale to make A New String array

<script>
    var text ="Hasnain";
        text +="Haider";
        text +="khan";
        text +="niazi";
        alert(text);

</script>

<br>
7- Immplement the Style to all the elemnet inside the ancestors 

.ancestors *
{ 
display: block;
border: 2px solid lightgrey;
color: lightgrey;
padding: 5px;
margin: 15px;
}

DEC : * with class implemnt the properties to all the values inside that div class 

<br>
8- jQuery children() also can use the Class to search the certain childer with id 

<script>
$(document).ready(function(){
  $("div").children("p.1").css({"color":"red","border":"2px solid red"});
});
</script>



<br>
9- Apply the Filter when the certain define condition is meet 

<script>
$(document).ready(function(){
  $("p").eq(1).css("background-color","yellow");
});
</script>
<script>
$(document).ready(function(){
  $("p").not(".intro").css("background-color","yellow");
});
</script>
<script>
$(document).ready(function(){
  $("div p").first().css("background-color","yellow");
});
</script>
<script>
$(document).ready(function(){
  $("div p").last().css("background-color","yellow");
});
</script>


<br>
10- Load String From the Server Through Two Method 

- Via using the Ajax() Dafualt Method

$.ajax({
   type: "POST",
   url: "some.php",
   data: "name=John&location=Boston",
   success: function(msg){
     alert( "Data Saved: " + msg );
   }
 }); 
 
 
- Via using the Load() Jquery by Dafault Method 

$.post("some.php", { name: "John", time: "2pm" },
   function(data){
     alert("Data Loaded: " + data);
   });
   
  DES: Load Data From the Server 

<br>
11- Send Data via using load() method with array ()

$("#objectID").load("test.php", { 'choices[]': ["Jon", "Susan"] } );

DES: Send Data Via using the array 


12- jQuery.getJSON()  Function equal to the 

$.ajax({
dataType: "json",
url: url,
data: data,
success: success
});

<br>
13 - Get JSON Data From API and Show 

<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>jQuery.getJSON demo</title>
        <style>
            img {
                height: 100px;
                float: left;
            }
        </style>
        <script src="//code.jquery.com/jquery-1.10.2.js"></script>
    </head>
    <body>
        <div id="images"></div>
        <script>
            (function() {
                var flickerAPI = "http://api.flickr.com/services/feeds/photos_public.gne?jsoncallback=?";
                $.getJSON( flickerAPI, {
                    tags: "mount rainier",
                    tagmode: "any",
                    format: "json"
                })
                .done(function( data ) {
                    $.each( data.items, function( i, item ) {
                        $( "<img>" ).attr( "src", item.media.m ).appendTo( "#images" );
                        if ( i === 100 ) {
                            return false;
                        }
                    });
                });
            })();
        </script>
    </body>
</html>

DES: SHow the JSON Data after Getting From the API 
