<h1 id="publications"></h1>

<h2 style="margin: 60px 0px -15px;">Publications <temp style="font-size:15px;">[</temp><a href="https://scholar.google.com.hk/citations?hl=zh-CN&pli=1&user=Z1F1vLgAAAAJ" target="_blank" style="font-size:15px;">Google Scholar</a><temp style="font-size:15px;">]</temp><temp style="font-size:15px;">[</temp><a href="https://www.researchgate.net/profile/Yang-Yan-18" target="_blank" style="font-size:15px;">ResearchGate</a><temp style="font-size:15px;">]</temp><temp style="font-size:15px;">[</temp><a href="https://orcid.org/0000-0001-8085-6981" target="_blank" style="font-size:15px;">ORCID</a><temp style="font-size:15px;">]</temp></h2>

<style>
  .earlier-publications {
    display: none;
  }

  .earlier-publications.is-open {
    display: block;
  }

  .pub-toggle-wrap {
    margin: 10px 0 24px 0;
    padding-left: 0;
  }

  .pub-toggle-btn {
    display: inline-block;
    border: none;
    background: transparent;
    color: #1772b4;
    font-family: inherit;
    font-size: 14px;
    font-weight: 600;
    padding: 0;
    cursor: pointer;
  }

  .pub-toggle-btn:hover {
    text-decoration: underline;
  }
</style>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main limit:5 %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
            <abbr class="badge">{{ link.conference_short }}</abbr>
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}" target="_blank" rel="noopener noreferrer">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.data %} 
      <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c; font-weight:600">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>

<div class="pub-toggle-wrap">
  <button class="pub-toggle-btn" id="earlierPubBtn" onclick="toggleEarlierPublications()">
    Show earlier publications
  </button>
</div>

<div class="earlier-publications" id="earlierPublications">
<ol class="bibliography" start="6">

{% for link in site.data.publications.main offset:5 %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
            <abbr class="badge">{{ link.conference_short }}</abbr>
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}" target="_blank" rel="noopener noreferrer">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.data %} 
      <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c; font-weight:600">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>
</div>

<script>
  function toggleEarlierPublications() {
    var earlier = document.getElementById("earlierPublications");
    var btn = document.getElementById("earlierPubBtn");

    if (earlier.classList.contains("is-open")) {
      earlier.classList.remove("is-open");
      btn.innerHTML = "Show earlier publications";
    } else {
      earlier.classList.add("is-open");
      btn.innerHTML = "Hide earlier publications";
    }
  }
</script>
