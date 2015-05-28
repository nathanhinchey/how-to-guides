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
