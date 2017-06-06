# sopnorny2

//imports appropriate libraries 
import processing.video.*;
Movie movie;

import processing.sound.*;
SoundFile soundfile;

//floating image offset 
float offset = 1;
float easing = .5;
float offer = 3;
float x, y;
float dim = 100.0;
float a;

PImage img1; 
PImage img2;
PImage img3;
PImage img4;
PImage img5;
PImage img6;

void setup(){
  size(1920, 1080,P3D);
  background(255);
  // Load and play the video in a loop
  movie = new Movie(this, "SOP NOR NY Processing Edit.mp4");
  movie.loop();
  
      //Load a soundfile
    soundfile = new SoundFile(this, "Human.aif");
    soundfile.loop();

    // These methods return useful infos about the file
    println("SFSampleRate= " + soundfile.sampleRate() + " Hz");
    println("SFSamples= " + soundfile.frames() + " samples");
    println("SFDuration= " + soundfile.duration() + " seconds");

    // Play the file in a loop
    soundfile.loop();

 img1 = loadImage("Pine Trail Wallpaper Cut Section1 Final.jpg");
 img2 = loadImage("Pine Trail Wallpaper Cut Section 2 Charcoal.jpg");
 img3 = loadImage("Pine Trail Wallpaper Cut Section 3 Charcoal.jpg");
 img4 = loadImage("Pine Trail Wallpaper Cut Section 4 Charcoal.jpg");
 img5 = loadImage("Pine Trail Wallpaper Cut Section 5 Charcoal.jpg");
 img6 = loadImage("Pine Trail Wallpaper Cut Section 6 Charcoal.jpg");
 
 a = height/2;
}

void movieEvent(Movie m){
  m.read();
}

void draw(){
    //if (movie.available() == true) {
  //  movie.read(); 
  //}
  image(movie, 0, 0, width, height);
  
  imageMode(CORNERS); 

//image(img1, 0, 1080, 320, 158);
float dy = (mouseY-img1.height/2) - offset;
offset += dy * easing;
tint(255, 200);  // Display at half opacity
image(img1, 10, mouseY);

  
//image(img2, 320, 1080, 640, 196); // Display at full opacity
float cx = (mouseX+img2.height/3) - offset;
offset += cx * easing;
tint(255, 200);  // Display at half opacity
image(img2,329, mouseX);
  
 //image(img3, 640,1080, 960, 158);  // Display at full opacity
float ex = (mouseX-img3.width/4) - offset;
offset += ex * easing;
tint(255, 200);  // Display at half opacity
image(img3, 647, mouseY);
  
//image(img4, 960, 1080, 1280, 196);  // Display at full opacity
float bx = (mouseX+img4.height/5) - offset;
offset+= bx * easing;
tint(255, 200);  // Display at half opacity
image(img4,960,mouseX);
  
//image(img5, 1280, 1080,1600, 160);  // Display at full opacity
float ax = (mouseX-img5.height/6) - offset;
offset+= ax * easing;
tint(255, 200);  // Display at half opacity
image(img5,1279,mouseY);
  
//image(img6, 1600, 1080, 1920, 199);  // Display at full opacity
float fx = (mouseX+img6.height/2) - offset;
offset += fx * easing;
tint(255, 200);  // Display at half opacity
image(img6, 1599, mouseX);
  }
