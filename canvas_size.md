#Making an HTML canvas fill window

###Making it fit the initial window size
Dependency: for dynamic resizing, jQuery. I used google's [hosted library](https://developers.google.com/speed/libraries/). But see the Additional Notes.

In the \*.js file:
```javascript
. . .
MyApp.DIM_X = $(window).width();
MyApp.DIM_Y = $(window).height();
. . .
```

In the HTML file:
```HTML
. . .
<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
. . .
<canvas id="game-canvas">

<script type="text/javascript">
  $("#game-canvas").attr("width", MyApp.DIM_X);
  $("#game-canvas").attr("height", MyApp.DIM_Y);
  . . .
</script>
. . .
```

###Avoid scroll bars
In the CSS:
```CSS
body {
  overflow: hidden;
}
```

###Making it resize with the window
In the \*.js file:
```javascript
$(window).resize(function() {
  MyApp.DIM_X = $(window).width();
  MyApp.Game.DIM_Y = $(window).height();
  $("canvas").attr("width", MyApp.DIM_X);
  $("canvas").attr("height", MyApp.DIM_Y);
});
```

#Additional Notes
##Common Mistakes:
This list will be updated as people report them. Please report an issue or make a pull request if you have any questions.
* Make sure you don't have any values hard coded
  - Many people have forgotten to make their clearRect linked to the same DIM_X and DIM_Y values.

##Not using jQuery:
If you don't need to have the canvas dynamically resize, you can avoid using jQuery:
JavaScript:
```JavaScript
MyApp.DIM_X = window.innerheight;
MyApp.DIM_Y = window.innerwidth;
```

HTML:
```HTML
. . .
<canvas id="game-canvas">

<script type="text/javascript">
  canvas = document.getElementById("game-canvas");
  canvas.height = MyApp.DIM_X;
  canvas.width = MyApp.DIM_Y;
  . . .
</script>
. . .
```
