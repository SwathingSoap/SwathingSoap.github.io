---
layout: default
---

<br/><br/>
<center>SWATHINGSOAP</center>

<center><a href="https://swathingsoap.github.io/resume">RESUME</a></center>
<br/><br/><br/>

<center>MY PROJECTS:</center>
<center><a href="https://store.steampowered.com/app/1449000/CALL_OF_LDPR/e">CALL OF LDPR</a></center>
<center><a href="https://www.youtube.com/watch?v=XYS-zTtFvno">THE DEADLY AUCTION OF BEAUTIES</a></center>
<center><a href="https://clips.twitch.tv/FunnySarcasticSkirretDAESuppy-s4wDuDBGWqqIe3gE">HPG 4.0</a></center>
<br/><br/><br/>

<center>MY POSTS:</center>
<ul>
  {% for post in site.posts %}
      <center><a href="{{ post.url }}">{{ post.title }}</a></center>
  {% endfor %}
</ul>