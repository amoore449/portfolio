---
category: ["robotics"]
  
caption: #what displays in the portfolio grid:
  title: Robotic Sheepherding
  subtitle: 2022
  thumbnail: assets/img/portfoliopictures/kalman/ray.png

  
#what displays when the item is clicked:
title: Robotic Sheepherding
subtitle: 2022
image: assets/img/portfoliopictures/kalman/ray.png
 #main image, can be a link or a file in assets/img/portfolio
alt: A Balancing Robot
video: https://www.youtube.com/embed/WlWCRKtc42w?si=SX2AYdMl3Y2070-6 

website: https://docs.google.com/presentation/d/1zZCdPusDTMsXNv8rVJC8Bo2wtI6OWp9kocA7XQ0z0ho/edit?usp=sharing 

---

  <div class="video-container d-block mx-auto padded-bottom">
    <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://www.youtube.com/embed/JpzOVDodEDk?si=nNSSABc0a0b-98Rf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  </div>

In this project, I designed and implemented an algorithm for a robotic simulation of sheep herding using the Misty Robot and [SLAM](https://www.mathworks.com/discovery/slam.html) image mapping. We used OpenCV color tracking and a Kalman Filter to estimate the position of herded flock and generate control vectors to herd the flock with a Misty robot similar to how a sheepdog would. 

<div class="video-container d-block mx-auto padded-bottom">
    <iframe class="responsive-iframe img-fluid d-block mx-auto" src= "https://drive.google.com/file/d/1PDZfBYmj0b4fLmJxgDfbtAm8mYRjAaHe/preview" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


<div class="row padded padded-bottom">
  <div class="col-md-6 col-sm-6 ">
    <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/kalman/graph.png" alt="{{ slide.image }}"/>
  </div>
  <div class="col-md-6 col-sm-6 ">
    <img class="img-fluid d-block mx-auto" src="assets/img/portfoliopictures/kalman/herd.png" alt="{{ slide.image }}"/>
  </div>
</div>



