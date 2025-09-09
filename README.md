## Hi there 👋

<html>
<head>
<title>Matrix Rain</title>
    <style>
        * {margin: 0; padding: 0;}
        body {background: black;}
canvas {display: block;}
body{
  padding: 25px;
}
.title {
	color: #5C6AC4;
}
    </style>
</head>
    <body>
    <canvas id="c"></canvas>
    </body>
    <script>

var c = document.getElementById("c");
var ctx = c.getContext("2d");

//making the canvas full screen
c.height = window.innerHeight;
c.width = window.innerWidth;

//english characters
var english = "1001010101110101010101010010101000101011101111010101010110101010101010101110000101";
//converting the string into an array of single characters
english = english.split("");

var font_size = 15;
var columns = c.width/font_size; //number of columns for the rain
//an array of drops - one per column
var drops = [];
//x below is the x coordinate
//1 = y co-ordinate of the drop(same for every drop initially)
for(var x = 0; x < columns; x++)
	drops[x] = 1; 

//drawing the characters
function draw()
{
	//Black BG for the canvas
	//translucent BG to show trail
	ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
	ctx.fillRect(0, 0, c.width, c.height);
	
	ctx.fillStyle = "#0F0"; //green text
	ctx.font = font_size + "px arial";
	//looping over drops
	for(var i = 0; i < drops.length; i++)
	{
		//a random chinese character to print
		var text = english[Math.floor(Math.random()*english.length)];
		//x = i*font_size, y = value of drops[i]*font_size
		ctx.fillText(text, i*font_size, drops[i]*font_size);
		
		//sending the drop back to the top randomly after it has crossed the screen
		//adding a randomness to the reset to make the drops scattered on the Y axis
		if(drops[i]*font_size > c.height && Math.random() > 0.975)
			drops[i] = 0;
		
		//incrementing Y coordinate
		drops[i]++;
	}
}

setInterval(draw, 33);
    </script>
</html>
<div id="header" align="center">
  <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExdmZiNTdtYjk5eDgyZjRwMHB1cTY0bDFld3RsNDQ4NnRqdm12ZmNoYiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/raGZ0thWzeQKzZ8WDA/giphy.gif" width="150"/>
</div>
<center>
<div id="badges"  align="center">
  <a href="https://www.linkedin.com/in/oned-imam-sutrisno-8349a1325/"> <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/> </a>
  <a href=""> <img src="https://img.shields.io/badge/Twitter-blue?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter Badge"/> </a>
</div></center>
<!--
**hidaist/hidaist** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
