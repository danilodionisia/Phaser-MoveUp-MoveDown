# Phaser-MoveUp-MoveDown
This is just an example of moves to up and down

var game = new Phaser.Game
(1200, 600, Phaser.AUTO, '', 
{ 
	preload: preload, 
	create: create, 
	update: update 
});


function preload() {

	game.load.spritesheet('star', 'star.png');

}

var spriteH;
var spriteV;

function create() {

    game.physics.startSystem(Phaser.Physics.ARCADE);

	game.stage.backgroundColor = '#124184';

	//setPositionHorizontal(100, 50, 300);
	setPositionVertical(100, 600, 0);
}

function update() {

	game.physics.arcade.collide(spriteV);
	//var sp = spriteH.position.x;
	/*
	if(sp > 750){
		sprite.kill();
		setPositionHorizontal(-100, 750, 300);
	}else if(sp < 50){
		sprite.kill();
		setPositionHorizontal(100, 50, 300);
	}*/
	
}


function setPositionHorizontal(gravity, posX, posY){
	
	spriteH = game.add.sprite(posX, posY, 'star', 2);
	game.physics.arcade.enable(spriteH);
	game.physics.arcade.gravity.x = gravity;
}

function setPositionVertical(gravity, posX, posY){
	
	spriteV = game.add.sprite(posX, posY, 'star', 2);
	game.physics.arcade.enable(spriteV);
	game.physics.arcade.gravity.y = gravity;
}

