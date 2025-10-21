---
title: "Brainbreak"
description: "The fast-loading brainbreak site"
layout: single
---

## Search Brainbreaks

<div class="search js-only">
  <input type="text" id="search" placeholder="Search ALL Brainbreaks...">
  <button id="clear-search">
    <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><title>Backspace</title><path d="M135.19 390.14a28.79 28.79 0 0021.68 9.86h246.26A29 29 0 00432 371.13V140.87A29 29 0 00403.13 112H156.87a28.84 28.84 0 00-21.67 9.84v0L46.33 256l88.86 134.11z" fill="none" stroke="currentColor" stroke-linejoin="round" stroke-width="32"></path><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="32" d="M336.67 192.33L206.66 322.34M336.67 322.34L206.66 192.33M336.67 192.33L206.66 322.34M336.67 322.34L206.66 192.33"></path></svg>
  </button>
</div>

<script>
// @license magnet:?xt=urn:btih:5ac446d35272cc2e4e85e4325b146d0b7ca8f50c&dn=unlicense.txt Unlicense

document.addEventListener("DOMContentLoaded", () => {
  for (e of document.getElementsByClassName("js-only")) {
    e.classList.remove("js-only");
  }

  const brainbreaks = document.querySelectorAll("#artlist li");
  const search = document.getElementById("search");
  const oldheading = document.getElementById("newest-brainbreaks");
  const clearSearch = document.getElementById("clear-search");
  const artlist = document.getElementById("artlist");

  search.addEventListener("input", () => {
    // grab search input value
    const searchText = search.value.toLowerCase().trim().normalize('NFD').replace(/\p{Diacritic}/gu, "");
    const searchTerms = searchText.split(" ");
    const hasFilter = searchText.length > 0;

    artlist.classList.toggle("list-searched", hasFilter);
    oldheading.classList.toggle("hidden", hasFilter);

    // for each brainbreak hide all but matched
    brainbreaks.forEach(brainbreak => {
      const searchString = `${brainbreak.textContent} ${brainbreak.dataset.tags}`.toLowerCase().normalize('NFD').replace(/\p{Diacritic}/gu, "");
      const isMatch = searchTerms.every(term => searchString.includes(term));

      brainbreak.hidden = !isMatch;
      brainbreak.classList.toggle("matched-brainbreak", hasFilter && isMatch);
    })
  })

  clearSearch.addEventListener("click", () => {
    search.value = "";
    brainbreaks.forEach(brainbreak => {
      brainbreak.hidden = false;
      brainbreak.classList.remove("matched-brainbreak");
    })

    artlist.classList.remove("list-searched");
    oldheading.classList.remove("hidden");
  })
})
// @license-end
</script>

## Newest Brainbreaks

{{< artlist >}}

## Or Browse by Category...

{{< tagcloud >}}

## About this site

This website is a fork of [Based Cooking](https://based.cooking).

## It's easy to contribute!

New brainbreaks can be submitted [on Github](https://github.com/lukesmithxyz/based.cooking).
We are funded by you only, not 20MB of ads or privacy-violating trackers per page.
