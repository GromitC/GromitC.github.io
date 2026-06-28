---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Research
---
<div id="research-intro">
  <h2>Research Overview</h2>
  I study how data processing algorithms, machine learning models and interaction designs must change when human perception and creativity, not just accuracy, are the goals, so that AI capabilities become meaningful in the interface, where humans think and create visually, not just the pipeline. This drives two lines of contribution: advances in <span class="sketch-teal">interactive data processing algorithms and AI model architectures</span>, and <span class="sketch-pink">new paradigms for how users interact with visualization and AI systems</span>.
</div>

<div id="pub-tabs">
  <div id="venue-filter">
    <span class="venue-filter-label">Venue:</span>
    <button class="venue-btn active" data-venue-key="all" onclick="filterVenue('all')">All</button>
  </div>
  <div class="tab-buttons">
    <button class="tab-btn active" onclick="showTab('selected')">Selected Publications</button>
    <button class="tab-btn" onclick="showTab('all')">All Publications</button>
  </div>
  <div id="tab-selected" class="tab-content" style="display:block;">
    {% for pub in site.data.publications %}
      {% if pub.selected %}
        <div class="pub-entry" data-venue="{{ pub.venue }}" data-type="{{ pub.type | default: 'other' }}">
          <table>
            <tr>
              <td id="leftcol">
                <div id="pubTitle"><b class="{% if pub.type == 'algo' %}sketch-teal-soft{% elsif pub.type == 'hci' %}sketch-pink-soft{% endif %}">{{ pub.title }}</b></div>
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
        </div>
      {% endif %}
    {% endfor %}
  </div>
  <div id="tab-all" class="tab-content" style="display:none;">
    {% for pub in site.data.publications %}
      <div class="pub-entry" data-venue="{{ pub.venue }}" data-type="{{ pub.type | default: 'other' }}">
        <table>
          <tr>
            <td id="leftcol">
              <div id="pubTitle"><b class="{% if pub.type == 'algo' %}sketch-teal-soft{% elsif pub.type == 'hci' %}sketch-pink-soft{% endif %}">{{ pub.title }}</b></div>
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
      </div>
    {% endfor %}
  </div>
</div>
<script>
var activeTab = 'selected';
var activeVenue = 'all';

function showTab(tab) {
  activeTab = tab;
  document.getElementById('tab-selected').style.display = (tab === 'selected') ? 'block' : 'none';
  document.getElementById('tab-all').style.display = (tab === 'all') ? 'block' : 'none';
  var btns = document.getElementsByClassName('tab-btn');
  for (var i = 0; i < btns.length; i++) { btns[i].classList.remove('active'); }
  btns[tab === 'selected' ? 0 : 1].classList.add('active');
  filterVenue(activeVenue);
}

function getVenueAcronym(venue) {
  var m = venue.match(/\(([A-Za-z\/]+)\s+\d{4}\)/);
  if (m && m[1] !== 'BigComp') return m[1];
  if (/IEEE Transactions on Visualization and Computer Graphics/.test(venue)) return 'VIS';
  if (/IEEE VIS/.test(venue)) return 'VIS';
  if (/CHI LBW/.test(venue)) return 'CHI';
  if (/ACM Web Conference/.test(venue)) return 'WWW';
  if (/IEEE Computer Graphics & Applications/.test(venue)) return 'CG&A';
  return 'Other';
}

function initVenueFilter() {
  var entries = document.querySelectorAll('#tab-all .pub-entry');
  var seen = new Set();
  var ordered = [];
  var counts = {}, algoCounts = {}, hciCounts = {};
  entries.forEach(function(e) {
    var v = getVenueAcronym(e.getAttribute('data-venue'));
    var t = e.getAttribute('data-type');
    if (!seen.has(v)) { seen.add(v); ordered.push(v); }
    counts[v] = (counts[v] || 0) + 1;
    if (t === 'algo') algoCounts[v] = (algoCounts[v] || 0) + 1;
    if (t === 'hci')  hciCounts[v]  = (hciCounts[v]  || 0) + 1;
  });
  var otherIdx = ordered.indexOf('Other');
  if (otherIdx !== -1) { ordered.splice(otherIdx, 1); }
  ordered.sort(function(a, b) { return counts[b] - counts[a]; });
  ordered.push('Other');
  var bar = document.getElementById('venue-filter');
  bar.querySelector('.venue-btn').textContent = 'All (' + entries.length + ')';
  ordered.forEach(function(v) {
    var btn = document.createElement('button');
    btn.className = 'venue-btn';
    btn.setAttribute('data-venue-key', v);
    btn.textContent = v + ' (' + counts[v] + ')';
    btn.onclick = function() { filterVenue(v); };
    var algo = algoCounts[v] || 0;
    var hci  = hciCounts[v]  || 0;
    var typed = algo + hci;
    if (typed > 0) {
      var pct = (algo / typed * 100).toFixed(2) + '%';
      var gradOff = 'linear-gradient(to right, #CCEBE7 0% ' + pct + ', #FFC7E3 ' + pct + ' 100%)';
      var gradOn  = 'linear-gradient(to right, #009B8A 0% ' + pct + ', #FB0F78 ' + pct + ' 100%)';
      btn.setAttribute('data-grad-off', gradOff);
      btn.setAttribute('data-grad-on',  gradOn);
      btn.style.background = gradOff;
      btn.style.border = 'none';
      btn.style.boxShadow = '0 0 0 1px rgba(0,0,0,0.08)';
      btn.classList.add('venue-btn-typed');
    }
    bar.appendChild(btn);
  });
}

function filterVenue(venue) {
  activeVenue = venue;
  var entries = document.querySelectorAll('#tab-' + activeTab + ' .pub-entry');
  entries.forEach(function(e) {
    e.style.display = (venue === 'all' || getVenueAcronym(e.getAttribute('data-venue')) === venue) ? '' : 'none';
  });
  document.querySelectorAll('.venue-btn').forEach(function(b) {
    b.classList.toggle('active', b.getAttribute('data-venue-key') === venue);
  });
  document.querySelectorAll('.venue-btn-typed').forEach(function(b) {
    var isActive = b.classList.contains('active');
    b.style.background = b.getAttribute(isActive ? 'data-grad-on' : 'data-grad-off');
    b.style.boxShadow = '0 0 0 1px rgba(0,0,0,' + (isActive ? '0.15' : '0.08') + ')';
  });
}

document.addEventListener('DOMContentLoaded', initVenueFilter);
</script>

