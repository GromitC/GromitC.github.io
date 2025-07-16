---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Research
---

<div id="pub-tabs">
  <div class="tab-buttons">
    <button class="tab-btn active" onclick="showTab('selected')">Selected Publications</button>
    <button class="tab-btn" onclick="showTab('all')">All Publications</button>
  </div>
  <div id="tab-selected" class="tab-content" style="display:block;">
    {% for pub in site.data.publications %}
      {% if pub.selected %}
        <table>
          <tr>
            <td id="leftcol">
              <div id="pubTitle"><b>{{ pub.title }}</b></div>
              <div id="pubAuthor">{{ pub.author}}</div>
              {{ pub.venue }}
            </td>
            <td id="rightcol">
              {% if pub.image %}
              <img src='assets/images/teasers/{{ pub.image}}'>
              {% endif %}
            </td>
          </tr>
        </table>
        <div id="paperlink">
          {% if pub.paper %}
          <a href="assets/papers/{{ pub.paper }}">preprint</a>
          {% endif %}
          {% if pub.appendix %}
          <a href="{{pub.appendix}}">appendix</a>
          {% endif %}
          {% if pub.link %}
          <a href="{{pub.link}}">link</a>
          {% endif %}
          {% if pub.slide %}
          <a href="assets/slides/{{pub.slide}}">slides</a>
          {% endif %}
          {% if pub.video %}
          <a href="assets/videos/{{pub.video}}">video</a>
          {% endif %}
          {% if pub.talk %}
          <a href="assets/videos/{{pub.talk}}">talk</a>
          {% endif %}
        </div>
      {% endif %}
    {% endfor %}
  </div>
  <div id="tab-all" class="tab-content" style="display:none;">
    {% for pub in site.data.publications %}
      <table>
        <tr>
          <td id="leftcol">
            <div id="pubTitle"><b>{{ pub.title }}</b></div>
            <div id="pubAuthor">{{ pub.author}}</div>
            {{ pub.venue }}
          </td>
          <td id="rightcol">
            {% if pub.image %}
            <img src='assets/images/teasers/{{ pub.image}}'>
            {% endif %}
          </td>
        </tr>
      </table>
      <div id="paperlink">
        {% if pub.paper %}
        <a href="assets/papers/{{ pub.paper }}">preprint</a>
        {% endif %}
        {% if pub.appendix %}
        <a href="{{pub.appendix}}">appendix</a>
        {% endif %}
        {% if pub.link %}
        <a href="{{pub.link}}">link</a>
        {% endif %}
        {% if pub.slide %}
        <a href="assets/slides/{{pub.slide}}">slides</a>
        {% endif %}
        {% if pub.video %}
        <a href="assets/videos/{{pub.video}}">video</a>
        {% endif %}
        {% if pub.talk %}
        <a href="assets/videos/{{pub.talk}}">talk</a>
        {% endif %}
      </div>
    {% endfor %}
  </div>
</div>
<script>
function showTab(tab) {
  document.getElementById('tab-selected').style.display = (tab === 'selected') ? 'block' : 'none';
  document.getElementById('tab-all').style.display = (tab === 'all') ? 'block' : 'none';
  var btns = document.getElementsByClassName('tab-btn');
  for (var i = 0; i < btns.length; i++) {
    btns[i].classList.remove('active');
  }
  if(tab === 'selected') {
    btns[0].classList.add('active');
  } else {
    btns[1].classList.add('active');
  }
}
</script>

