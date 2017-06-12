<!DOCTYPE html>
<html>
<head>
<style>
body {font-family: "Lato", sans-serif;}
/* Style the tab */
div.tab {
    overflow: hidden;
    border: 1px solid #ccc;
    background-color: #f1f1f1;
}
/* Style the buttons inside the tab */
div.tab button {
    background-color: inherit;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    transition: 0.3s;
    font-size: 17px;
}
/* Change background color of buttons on hover */
div.tab button:hover {
    background-color: #ddd;
}
/* Create an active/current tablink class */
div.tab button.active {
    background-color: #ccc;
}
/* Style the tab content */
.tabcontent {
    display: none;
    padding: 6px 12px;
    border: 1px solid #ccc;
    border-top: none;
}
</style>
</head>
<body>
<p>Click on the buttons inside the tabbed menu:</p>
<div class="tab">
  <button class="tablinks" onclick="openCity(event, 'Tab1')">Tab1</button>
  <button class="tablinks" onclick="openCity(event, 'Lucas')">Lucas</button>
  <button class="tablinks" onclick="openCity(event, 'Brian')">Brian</button>
  <button class="tablinks" onclick="openCity(event, 'Tokyo')">Tokyo</button>
  <button class="tablinks" onclick="openCity(event, 'London')">London</button>
  <button class="tablinks" onclick="openCity(event, 'Paris')">Paris</button>
</div>
<div id="Tab1" class="tabcontent">
  <h3><center>Hover over to see what’s inside</h3>
  <a href="SSX.html">
    <img src="SSX.jpg"
         onmouseover="this.src='http://i.imgur.com/aFevPGG.jpg';"
         onmouseout="this.src='http://bbcpersian7.com/images/bank-vault-door-clipart-5.jpg';"
         height=500
         width=480 />
<a/>
</div>
<div id="Lucas" class="tabcontent">
  <p> <div style="background-color:black;color:white;padding:20px;">
<h1 style=font-size:400%;"><center>THIS WEBSITE EXISTS FOR ONE PURPOSE</center></h1>
<h2 style=font-size:200%;"><center>FOR YOU TO CLICK THE LINK BELOW</center></h2>
  <p style="text-align:center;">-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------<br>-------------------------------------------------------------------------------------------------------------------------------------------------------<br>----------------------------------------------------------------------------------------------------------<br>---------------------------------------------------------------------------<br>-----------------------------------------------------------<br>----------------------------------------------<br>------------------------------<br>-----------------------<br>----------------<br>----------<br>-----<br>--<br>-
</h1></p>
<p><h1 style="font-size:300%;"><center </center>
<a href="https://www.facebook.com/photo.php?fbid=10205131821787582&set=pb.1005558038.-2207520000.1496967613.&type=3&theater"> <center><em>Right Here</em></center></a>
</div>
<div style="background-color:black;color:white;padding:20px;">
<p style="text-align:center;">-<br>---<br>--------<br>-----------------<br>------------------------------<br>-------------------------------------------<br>-----------------------------------------------------------<br>-------------------------------------------------------------------------------<br>--------------------------------------------------------------------------------------------------------<br>-----------------------------------------------------------------------------------------------------------------------------------------------------------<br>-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------<br>----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------<br>------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<br>--------------------------------------------------------------------------------------------------------------------------------------<br>----------------------------------------------------------------------------------------------<br>--------------------------------------------------------<br>-----------------<br>---------<br---<br>-<br>-<b--</p>
<p><h1 style="font-size:300%;"><center>Or you can try  </center>
<a href="https://www.facebook.com/photo.php?fbid=10205131821787582&set=pb.1005558038.-2207520000.1496967613.&type=3&theater"> <center><em>THIS</em></center></a>
<br>
<br>
<br>
<center>OR <br> <br> <br> <br><br><br><br>
</center>
</p>
<p>
<center>Check out THIS SHIT
<center><iframe src="http://www.staggeringbeauty.com/" style="border: 1px inset #ddd" width="598" height="698"></iframe></center>
</p>
</div>
</div>

<div id="Brian" class="tabcontent">
<h1 style="font-family:arial;color:navy;font-size:200%;”><center>Brian</title>
<p style="font-family:arial;color:red;font-size:100%;”><center>YOU ARE ONLY HERE TO PRESS THIS BUTTON</p>

<game>


<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<style>
canvas {
    border:1px solid #d3d3d3;
    background-color: #00ffff;
}
</style>

<button onclick="startGame()">Start Game</button>
<button onmousedown="accelerate(-0.3)" onmouseup="accelerate(0.4)">UP</button>
<script>



var myGamePiece;
var myObstacles = [];
var myScore;


function startGame() {
    myGamePiece = new component(30, 30, "pink", 10, 120);
    myGamePiece.gravity = 0.06;
    myScore = new component("30px", "Consolas", "black", 400, 40, "text");
    myGameArea.start();
}

var myGameArea = {
    canvas : document.createElement("canvas"),
    start : function() {
        this.canvas.width = 300;
        this.canvas.height = 200;
        this.context = this.canvas.getContext("2d");
        document.body.insertBefore(this.canvas, document.body.childNodes[0]);
        this.frameNo = 0;
        this.interval = setInterval(updateGameArea, 20);
        },
    clear : function() {
        this.context.clearRect(0, 0, this.canvas.width, this.canvas.height);
    }
}

function component(width, height, color , x, y, type) {
    this.type = type;
    this.score = 0;
    this.width = width;
    this.height = height;
    this.speedX = 0;
    this.speedY = 0;
    this.x = x;
    this.y = y;
    this.gravity = 0;
    this.gravitySpeed = 0;
    this.update = function() {
        ctx = myGameArea.context;
        if (this.type == "text") {
            ctx.font = this.width + " " + this.height;
            ctx.fillStyle = color;
            ctx.fillText(this.text, this.x, this.y);
        } else {
            ctx.fillStyle = color;
            ctx.fillRect(this.x, this.y, this.width, this.height);
        }
    }
    this.newPos = function() {
        this.gravitySpeed += this.gravity;
        this.x += this.speedX;
        this.y += this.speedY + this.gravitySpeed;
        this.hitBottom();
    }
    this.hitBottom = function() {
        var rockbottom = myGameArea.canvas.height - this.height;
        if (this.y > rockbottom) {
            this.y = rockbottom;
            this.gravitySpeed = 0;
        }
    }
    this.crashWith = function(otherobj) {
        var myleft = this.x;
        var myright = this.x + (this.width);
        var mytop = this.y;
        var mybottom = this.y + (this.height);
        var otherleft = otherobj.x;
        var otherright = otherobj.x + (otherobj.width);
        var othertop = otherobj.y;
        var otherbottom = otherobj.y + (otherobj.height);
        var crash = true;
        if ((mybottom < othertop) || (mytop > otherbottom) || (myright < otherleft) || (myleft > otherright)) {
            crash = false;
        }
                return crash;
    }

}




function updateGameArea() {
    var x, height, gap, minHeight, maxHeight, minGap, maxGap;
    for (i = 0; i < myObstacles.length; i += 1) {
        if (myGamePiece.crashWith(myObstacles[i])) {
            return;
        }
    }
    myGameArea.clear();
    myGameArea.frameNo += 1;
    if (myGameArea.frameNo == 1 || everyinterval(50)) {
        x = myGameArea.canvas.width;
        minHeight = 0;
        maxHeight = 150;
        height = Math.floor(Math.random()*(maxHeight-minHeight+1)+minHeight);
        minGap = 50;
        maxGap = 150;
        gap = Math.floor(Math.random()*(maxGap-minGap+1)+minGap);
        myObstacles.push(new component(20, height, "black", x, 0));
        myObstacles.push(new component(20, x - height - gap, "black", x, height + gap));
    }
    for (i = 0; i < myObstacles.length; i += 1) {
        myObstacles[i].x += -5;
        myObstacles[i].update();
    }
    myScore.text="SCORE: " + myGameArea.frameNo;
    myScore.update();
    myGamePiece.newPos();
    myGamePiece.update();
}

function everyinterval(n) {
    if ((myGameArea.frameNo / n) % 1 == 0) {return true;}
    return false;
}

function accelerate(n) {
    myGamePiece.gravity = n;
}


</script>
<br>

<button onclick="window.location.reload()">Restart</button>

</game>
</div>



 <div id="Tokyo" class="tabcontent">
  <h3>Tokyo</h3>
  <p>Tokyo is the capital of Japan.</p>
</div>

<div id="London" class="tabcontent">
  <h3>London</h3>
  <p>London is the capital city of England.</p>
</div>

<div id="Paris" class="tabcontent">
  <h3>ANSWER THE FOLLOWING QUERY TO GAIN ACCESS:</h3>
  <p><form action="/action_page.php">
  <div class="imgcontainer">
    <img src="http://i.imgur.com/raRuEM5.jpg" alt="Avatar" class="avatar">
  </div>

  <div

    <label><b>What is the man disgusted at?</b></label>
    <input type="password" placeholder="" name="no_one" required>
<a href="http://www.hudl.com/v/1sWamu" class="button">Submit</a>


  </div>

<script>
function openCity(evt, cityName) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tabcontent");
    for (i = 0; i < tabcontent.length; i++) {
        tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tablinks");
    for (i = 0; i < tablinks.length; i++) {
        tablinks[i].className = tablinks[i].className.replace(" active", "");
    }
    document.getElementById(cityName).style.display = "block";
    evt.currentTarget.className += " active";
}
</script>

</body>
</html>

