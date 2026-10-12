# TinyCalc
A very simple graphing calculator under 3kb
that you can just bookmark as a data url. No
internet required.

# How to use
Set the viewport, and type the equation.
You can also select an example from the list.

# Link

```link
data:text/html,<!DOCTYPE html><html><body><input id="equation" value="x=>x**2" /><br/>Viewport:<br/>x: <input id="left" value="-1" /> to <input id="right" value="1" /><br/>y: <input id="bottom" type="text" value="0" /> to <input id="top" type="text" value="2" /><br/><canvas id="c" width="500" height="500"></canvas><br/>Open console (ctrl+shift+i) to show errors.<br/><h3>Examples</h3><button onclick="set_equation('x=>x**2')">y=x^2</button><button onclick="set_equation('x=>Math.abs(x)')">y=|x|</button><button onclick="set_equation('x=>Math.sqrt(1-x*x)')">Top Half Circle (y=sqrt(1-x^2))</button><button onclick="set_equation('x=>1-Math.sqrt(1-x*x)')">Bottom Half Circle (y=1-sqrt(1-x^2))</button><script>setInterval(graph, 100);function set_equation(t){document.getElementById("equation").value=t}const ctx=document.getElementById("c").getContext("2d");function get_math_x(t){const e=document.getElementById("left").value-0;return t/500*(document.getElementById("right").value-0-e)+e}function get_pixel_y(t){const e=document.getElementById("top").value-0;return 500*(t-e)/(document.getElementById("bottom").value-0-e)}function graph_column(pixel_x){const math_x=get_math_x(pixel_x),math_y=eval(document.getElementById("equation").value.replaceAll("^","**"))(math_x),pixel_y=get_pixel_y(math_y);ctx.fillRect(pixel_x-2,pixel_y-2,4,4)}function graph(){ctx.fillStyle="white",ctx.fillRect(0,0,500,500),ctx.fillStyle="black";for(let t=0;t<500;t++)graph_column(t)}setInterval(graph,100);</script></body></html>
```

#
Made for Hack Club's Shrink program so I can
win a free Raspberry Pi.
