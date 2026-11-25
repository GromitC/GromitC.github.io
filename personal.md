---
layout: default
title: Personal
---
<div class="onecol">
  <div class="subheader">Some Videos</div>
  <h5>I was selected to present my work on email editing in Adobe Journey Optimizer with Kristen Bell at Adobe Summit Sneaks 2022. Part of the work was also presented at CHI LBW in the same year.</h5>
  <div class="video">
    <iframe src="https://www.youtube.com/embed/o8azsdA0ozU?si=gE3ejkYbcmcmMW9H" title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen loading="lazy"></iframe>
  </div>
  <h5>Two years later, my work on infographics editing with my intern Tongyu Zhou was selected to be presented at Summit Sneaks again. It was the only intern work selected to be presented, and Tongyu did an amazing job showing Shaquille O'Neal how cool infographics could be! The work was also accepted as a regular CHI paper in the same year.</h5>
  <div class="video">
    <iframe src="https://www.youtube.com/embed/XSMO9-7pcq8?si=JHEnwRs5MI9vB6NG" title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen loading="lazy"></iframe>
  </div>
</div>

<div class="onecol">
  <div class="subheader">Some Traveling Photos:</div>
  <div class="slideshow-container">
    {% assign travel = "bc.jpg|Bryce Canyon,boston.jpg|Boston,duluth.jpg|Duluth,gc.jpg|Grand Canyon,Kyoto.jpg|Kyoto,monterey.jpg|Monterey,mp.jpg|Machu Picchu,nikko.jpg|Nikko,ny.jpg|New York,seattle.jpg|Seattle,sf.jpg|San Francisco,singapore.jpg|Singapore,snowmobile.jpg|Yellowstone,utah.jpg|Utah,yosemite.jpeg|Yosemite,Sichuan.jpeg|Sichuan" | split: "," %}
    {% for slide in travel %}
      {% assign parts = slide | split: "|" %}
      <div class="mySlides fade">
        <img src="assets/images/travel/{{ parts[0] }}" alt="{{ parts[1] }}" loading="lazy">
        <div class="text">{{ parts[1] }}</div>
      </div>
    {% endfor %}
    <a class="prev" onclick="plusSlides(-1)" role="button" aria-label="Previous photo">&#10094;</a>
    <a class="next" onclick="plusSlides(1)" role="button" aria-label="Next photo">&#10095;</a>
  </div>
</div>
