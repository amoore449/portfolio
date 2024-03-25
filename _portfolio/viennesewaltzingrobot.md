---
category: ["robotics"]

caption: #what displays in the portfolio grid:
  title: Viennese Waltzing Robot  
  subtitle: 2021
  thumbnail: assets/img/portfoliopictures/Waltz/group.jpg
  
#what displays when the item is clicked:
title: Viennese Waltzing Robot 
subtitle: 2021
image: assets/img/portfoliopictures/PageTurn.png
#main image, can be a link or a file in assets/img/portfolio
alt: image alt text
video:
github: https://github.com/sbentl02/Dancing-Robots 

slides:
  - image: assets/img/portfoliopictures/Waltz/group.jpg
  - image: assets/img/portfoliopictures/Waltz/white_three_robot.jpg
---

<div class="video-container d-block mx-auto">
  <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://www.youtube.com/embed/P5tnQ8JNzDY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Using SPIKE LEGO Robotics kits, I worked with two partners to design a system of robots to “dance” based on the Viennese Waltz. Our trio of three separate robots followed an counterclockwise outer circle alongside other robot dancing “partners” while continuously spinning in smaller loops similar to the rotary style of the waltz. Our primary system consisted of a “leader” and “follower” robot, where the dance “leader” switched out mid dance with an alternative “leader robot.” We based the design of our robots on characters from the Disney movie "Up."

In our three part system, both "Leader" robots are constructed from a SPIKE Prime attached to a Raspberry Pi powered by a Battery PA. The Leader receives input from a microphone to detect music. It uses a color sensor to detect its place on a line and outputs proportional control values to its two motors. A green dot is attached to the leader for the follower's color tracking.

Like the Leader," the "Follower" robot is constructed from a SPIKE Prime and a Battery Pack powered Raspberry Pi 4. The Follower receives input from a Raspberry Pi cv2 camera attached to the front of the robot.It uses image processing to track the green dot on the "Leader" robot. Output speed and direction changes are then sent to the SPIKE's motors.

<div class="row padded">
    <div class="col-md-4 col-sm-6 ">
      <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/Waltz/bird.jpeg" alt="Bird Image"/>
      <figcaption>Fig.1 - Labeled diagram of Leader A Robot</figcaption>
    </div>
     <div class="col-md-4 col-sm-6 ">
      <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/Waltz/boy.jpeg" alt="Bird Image"/>
      <figcaption>Fig.2 - Labeled diagram of Leader B Robot</figcaption>
    </div>
     <div class="col-md-4 col-sm-6 ">
      <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/Waltz/dog.jpeg" alt="Bird Image"/>
      <figcaption>Fig.3 - Labeled diagram of Follower Robot</figcaption>
    </div>
</div>

To maintain a "dance" between the Waltzing Robots, we based the "follower" robot's movement on tracking a green dot on the "leader robot." To import a physical image, we used an opencsv camera with SPIKE Prime to identify a green ball shape with an image processing mask, dilations, erosions. In our streamed video, we trace a yellow circle with a centered red dot with dimension coordinates that can be returned to the proportional controller. In our initial trails, we used face tracking instead of color tracking for our follower robot, however we switched to a color tracking system to decrease the follower robot’s processing time.

 <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/Waltz/RobWaltzA.png">
<figcaption>Fig.4 - System Diagram of Full Leader and Follower Robot System </figcaption>


<div class="row padded">
<h3 class="text-uppercase">Line Following</h3>
</div>

 <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/Waltz/p_c.jpg" style="width:100%;">


 <figcaption>Fig.4 - System Diagram of Full Leader and Follower Robot System </figcaption>

<div class="video-container d-block mx-auto">
  <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://www.youtube.com/embed/TElTNYYjfrA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

 <figcaption>Video.1 - Initial Prototypes of Line Following Robot </figcaption>





To navigate the outer waltz circle, we use a proportional control system with color tracking along a line. For this line following task, I identified an ideal threshold value as the average of “online” and “offline” color measurement so the “leader” would follow along the edge of the line.

Error is measured relative to the difference between this “threshold” value and the actual sensor value and modulated by proportionality constant “Kp” to control for environmental factors. The resulting speed of each wheel motor is then modulated by error to keep the “Leader” following along a line.

<h3 class="text-uppercase">Leader Switch Out</h3>

<div class="video-container d-block mx-auto">
  <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://www.youtube.com/embed/y8K5sXLbs8c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<figcaption>Video.2 - Leader and Follower Robot Switch</figcaption>

To maintain a "dance" between the Waltzing Robots, we based the "follower" robot's movement on tracking a green dot on the "leader robot." To import a physical image, we used an opencsv camera with SPIKE Prime to identify a green ball shape with an image processing mask, dilations, erosions. In our streamed video, we trace a yellow circle with a centered red dot with dimension coordinates that can be returned to the proportional controller. In our initial trails, we used face tracking instead of color tracking for our follower robot, however we switched to a color tracking system to decrease the follower robot’s processing time. 

For the movement of the follower, we used a proportional controller to keep the green dot at a constant size and radius. The speed of the followers movement is dependent on the measured size and position of the dot so that the follower can speed up to catch up if it loses track of the dot and turn to stay in line with the leader robot as it spins throughout the date.

<h3 class="text-uppercase">Color Tracking</h3>

<div class="video-container d-block mx-auto">
  <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://www.youtube.com/embed/0SKpCFWBwYY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<figcaption>Video.3 - Color Detection</figcaption>


Although a waltz traditionally has two dancers, we had a three robot system and wanted to let all three robots "participate" in the dance. We used the SPIKE Prime color sensor to detect when the "Leader" robot runs over "red." Upon sensing "red," the leader robots will switch out with one another.

<h3 class="text-uppercase">Music Detection</h3>

<div class="video-container d-block mx-auto">
  <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://www.youtube.com/embed/OMv1w159Xak" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<figcaption>Video.4 - Robot Response to Waltz Music</figcaption>

We used Pyaudio and a 1D linear classifier to identify variations the start and stop of waltz music using a microphone connected to Raspberry Pi 4. We then sent indicator values to the SPIKE to start and stop over serial. While we were able to achieve some success with this method, we struggled to gather a dataset that could successfully differentiate between ambient noise and music since the Waltz music alternated between high and low output values throughout the orchestration.


