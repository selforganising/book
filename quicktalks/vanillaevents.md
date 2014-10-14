##Event Handling
##Without JQuery

How to handle events with JQuery:
```
$(".btn").click(function(){
  alert("HELLO");
});
```


How to do it without:
```
var buttons = document.getElementsByClassName("btn");
buttons.forEach(function (button) {
    button.onclick = function () {
      alert("HELLO");
    };
})

```

or

```
button.addEventHandler("click", function(){ alert("HELLO")}, false);
//                      type          //handler function
```

Maybe 3 more lines of code but no time finding the CDN link, no time making sure you pasted the right one, no loading the entire JQuery library just so you can alert "HELLO" to the user. 

\#govanilla

-Checkout attachEvent for compatibility with IE and Opera (get used to it).
-Checkout DOM event types
