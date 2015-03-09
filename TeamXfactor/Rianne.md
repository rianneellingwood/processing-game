X Factor
//Set up necessary variables.
int x=10; //x-coordinate of ellipse moving around sketch edge.
int y=10; //y-coordinate of ellipse moving around sketch edge.
int cx=100; //x-coordinate of bouncing ball
int cy=10; //y-coordinate of bouncing ball
int r=30; //radius of bouncing ball
int vx=2; //bouncing ball's direction on the x-axis
int vy=3; //bouncing ball's direction on the y-axis

//Set up variable for speed of ellipse moving around sketch edge.
int speed=1;

//Allows ellipse moving around sketch edge to change direction depending on position.
int state=0;

//Set up size of and smooth out sketch.
void setup(){
size(500, 300);
smooth();
}

//Set background to white to hide previous draw commands.
void draw(){
background(255);

noStroke();
//Fill bouncing ball as black.
fill(0);
//Change ellipse mode.
ellipseMode(CENTER);
//Draw bouncing ball with variables.
ellipse(cx, cy, r, r);

//Set cy variable to move across the sketch
cy = cy + vy;

//Set condition to bounce ball once it reaches sketch edge.
if((cy>height-40)||(cy<0)){
  vy = vy * -1;
}
//Set cx variable to bouncing ball move across the sketch.
cx = cx + vx;

//Set condition to bounce ball once it reaches sketch edge.
if((cx > width - 10)||(cx < 0)){
  vx = vx * -1;
}

}
