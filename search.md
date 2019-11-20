---
layout: default
title: Rechercher
---
<div id="search-container">
<input type="text" id="search-input" placeholder="Rechercher">
<ul id="results-container"></ul></div>

<script src="/techlovers/search-script.js/" type="text/javascript"></script>

<script>
SimpleJekyllSearch({
  searchInput: document.getElementById('search-input'),
  resultsContainer: document.getElementById('results-container'),
  json: '/techlovers/search.json'
  })
</script>