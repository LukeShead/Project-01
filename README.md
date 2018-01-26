# Project-01
HND Game development Project 01

## What is the Game,

The game is where the user will play a square avatar, they will have to avoid an NPC square from colliding with the user, there are three lives that the user has to lose by colliding with the other square, the game ends when the players lives are dropped to 0. A timer is displayed on the app to show the user how far they have got.

## IDE, Implementation and standards of project 1.

## The IDE I used to design this product is the original Notepad,

I used this to write the code as it is the most basic text editor, this was to show me what the difference was between a basic text editor and a code development software. Learning that there are many things that other IDE's can offer many more features such as debugging, however using notepad showed me how difficult it can be to write code with no help from the software, IDE's provide many features such as syntax highlighting that helps when reading code, however Notepad does not have any of these features, this has helped me understand the importance of IDE's.

## The implementation.

In order to implement the code, I used a method of finding code online, learning it and what each line does, then writing my own to help me understand how it is written. By researching the different functions using sites like W3schools.com, I was able to use these functions to help me write the code. This research made creating the project much easier, this is because knowing what certain functions did was very helpful when looking at what functions to use at the time, by using the right functions I was able to make more progress rather than have more errors.

This usually worked however by not taking individual problems and solving them one by one I tried to solve the whole thing at once and because of this it means that the program was filled with errors and not allowing me to finish by the deadline.


### Code I used.

<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<style>
canvas {
    border:1px solid #d3d3d3;
    background-color: #f1f1f1;
}
</style>
</head>
<body onload="startGame()">
<script>
var myGamePiece;
var targetPiece;
var gamepieceX;
gamepieceX = 30;
gamepieceY = 30;
var othergamepieceX;
var othergamepieceY;
othergamepieceX = 100;
othergamepieceY = 100;
var gamelives;
gamelives = 3;
document.write(gamelives ," lives left")
function startGame() {
    myGamePiece = new component(30, 30, "red", gamepieceX, gamepieceY);
    targetPiece = new component(30, 30, "blue", othergamepieceX,othergamepieceY);
    
    myGameArea.start();
}
var myGameArea = {
    canvas : document.createElement("canvas"),
    start : function() {
        this.canvas.width = 480;
        this.canvas.height = 270;
        this.context = this.canvas.getContext("2d");
        document.body.insertBefore(this.canvas, document.body.childNodes[0]);
        this.interval = setInterval(updateGameArea, 20);
		window.addEventListener('mousemove', function (e) {
			myGameArea.x = e.pageX;
			myGameArea.y = e.pageY;
		})
    },
    clear : function() {
        this.context.clearRect(0, 0, this.canvas.width, this.canvas.height);
    }
}
function component(width, height, color, x, y) {
    this.width = width;
    this.height = height;
	this.speedX = 0;
	this.speedY = 0; 
	this.x = x;
	this.y = y;
    this.update = function(){
        ctx = myGameArea.context;
        ctx.fillStyle = color;
        ctx.fillRect(this.x, this.y, this.width, this.height);
    }
}
function updateGameArea() {
    myGameArea.clear();
	if (myGameArea.x && myGameArea.y) {
		targetPiece.x = myGameArea.x;
		targetPiece.y = myGameArea.y;
	}
	othergamepieceX = targetPiece.x
	othergamepieceY = targetPiece.y
	myGamePiece.update();
    targetPiece.update();
	
    //document.write(gamepieceX)
    if (myGamePiece.x < othergamepieceX) {
    	myGamePiece.x += 1;
		targetPiece.update();
		myGamePiece.update();
	}
	if (myGamePiece.x > othergamepieceX) {
    	myGamePiece.x -= 1;
		targetPiece.update();
		myGamePiece.update();
	}
	
	
	if (myGamePiece.y < othergamepieceY) {
    	myGamePiece.y += 1;
		targetPiece.update();
		myGamePiece.update();
	}
	
	if (myGamePiece.y > othergamepieceY) {
    	myGamePiece.y -= 1;
		targetPiece.update();
		myGamePiece.update();
	}
	

## Coding standards.

I used tabs to make my work look better for me, by being able to place them all in a structure I was able to read the code better, this is my standard of coding and it helps me understand what functions go with what variables, for example I will put certain lines of text further to the right since people read left to right, having something to distinguish the code helps. When reading my code back for references for future work, my coding standards will make it easier for me and any of my team to read and understand the code written. 

## Debugging.

With debugging I had to attempt to debug the code myself, this is because notepad does not have any forms of debugging available which means errors needed to be found and fixed myself.
