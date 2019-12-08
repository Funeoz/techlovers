---
layout: default
title: Rechercher
---
<div id="search-container">
<input type="text" id="search-input" placeholder="Rechercher">
<ul id="results-container"></ul></div>

<script src="https://unpkg.com/simple-jekyll-search/dest/simple-jekyll-search.min.js"></script>

<script>
SimpleJekyllSearch({
  searchInput: document.getElementById('search-input'),
  resultsContainer: document.getElementById('results-container'),
  json: '/techlovers/search.json'
  })
</script>