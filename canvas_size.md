#Making an HTML canvas fill window

###Making it fit the initial window size
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

#Common Mistakes:
This list will be updated as people report them. Please report and issue or make a pull request if you have any questions.
* Make sure you don't have any values hard coded
  - Many people have forgotten to make their clearRect linked to the same DIM_X and DIM_Y values.
