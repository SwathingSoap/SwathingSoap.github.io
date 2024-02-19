---
layout: default
---

<br/><br/>
<center>SWATHINGSOAP</center>

<br/><br/><br/>

<center>MY PROJECTS:</center>
<center><a href="https://store.steampowered.com/app/1486950/The_Underground_Man_2/">The Underground Man 2</a></center>
<center><a href="https://store.steampowered.com/app/1449000/CALL_OF_LDPR/e">CALL OF LDPR</a></center>
<center><a href="https://www.youtube.com/watch?v=XYS-zTtFvno">The Deadly Auction Of Beauties</a></center>
<center><a href="https://clips.twitch.tv/FunnySarcasticSkirretDAESuppy-s4wDuDBGWqqIe3gE">HPG 4.0</a></center>
<br/><br/><br/>

<center>MY POSTS:</center>
<ul>
  {% for post in site.posts %}
      <center><a href="{{ post.url }}">{{ post.title }}</a></center>
  {% endfor %}
</ul>
