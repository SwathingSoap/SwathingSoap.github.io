---
layout: default
---

<br/><br/>
<center>SWATHINGSOAP</center>

<center><a href="https://swathingsoap.github.io/resume">RESUME</a></center>
<br/><br/><br/>

<center>MY PROJECTS:</center>
<center><iframe src="https://store.steampowered.com/widget/1449000/" frameborder="0" width="646" height="190"></iframe></center>
<center><a href="https://www.youtube.com/watch?v=XYS-zTtFvno">THE DEADLY AUCTION OF BEAUTIES</a></center>
<center><a href="https://clips.twitch.tv/FunnySarcasticSkirretDAESuppy-s4wDuDBGWqqIe3gE">HPG 4.0</a></center>
<br/><br/><br/>

<center>MY POSTS:</center>
<ul>
  {% for post in site.posts %}
      <center><a href="{{ post.url }}">{{ post.title }}</a></center>
  {% endfor %}
</ul>
