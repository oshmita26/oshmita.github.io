---
layout: page
title: bookshelf
permalink: /books/
nav: false
covers: /assets/img/book_covers/
---

> Sometimes I think heaven must be one continuous unexhausted reading.
>
> -- Virginia Woolf (1975). "The Letters of Virginia Woolf: 1932-1935"

{% comment %}
Card-based bookshelf grouped into named sections via each book's `shelf:` field in \_books/\*.md.
Allowed shelf values: currently-reading, favorites, academic, non-academic.
Covers are optional — set `cover`, `olid`, or `isbn` in a book's front matter to show its image;
otherwise a text placeholder card is rendered. Card markup/classes mirror the gem book-shelf layout
so styling (figure.cover, figcaption status badges) is inherited from al_folio_core.

NOTE: HTML lines below are intentionally NOT indented. Kramdown treats lines indented by
4+ spaces as a code block, which would print the markup instead of rendering it.
{% endcomment %}

{% assign sections = "currently-reading,favorites,academic,non-academic" | split: "," %}
{% assign section_titles = "Currently Reading,Favorites / Recommendations,Academic / Field-Specific Reads,Non-Academic Reads" | split: "," %}

{% for shelf in sections %}
{% assign shelf_books = site.books | where: "shelf", shelf %}
{% if shelf_books.size > 0 %}

<h2 id="{{ shelf }}">{{ section_titles[forloop.index0] }}</h2>
<div class="books-grid" style="display:flex;flex-wrap:wrap;align-items:flex-start;">
{% for item in shelf_books %}
<figure class="cover">
<a class="cover-link" href="{{ item.url | relative_url }}">
{% if item.cover %}
<img alt="{{ item.title }} cover" src="{{ item.cover | prepend: page.covers | relative_url }}" style="height:200px" />
{% elsif item.olid %}
<img alt="{{ item.title }} cover" src="https://covers.openlibrary.org/b/olid/{{ item.olid }}-L.jpg?default=false" style="height:200px" />
{% elsif item.isbn %}
<img alt="{{ item.title }} cover" src="https://covers.openlibrary.org/b/isbn/{{ item.isbn }}-L.jpg?default=false" style="height:200px" />
{% else %}
<span class="cover-placeholder" style="display:flex;flex-direction:column;justify-content:center;align-items:center;width:140px;height:200px;padding:0.75rem;text-align:center;border:1px solid var(--global-divider-color);border-radius:6px;background-color:var(--global-card-bg-color);"><strong style="font-size:0.9rem;line-height:1.2;">{{ item.title }}</strong>{% if item.author %}<span style="font-size:0.8rem;margin-top:0.4rem;color:var(--global-text-color-light);">{{ item.author }}</span>{% endif %}</span>
{% endif %}
{% assign statuses = "abandoned,finished,interested,paused,queued,reading,reread" | split: "," %}
{% assign status = item.status | downcase | strip %}
{% if item.status and statuses contains status %}
<figcaption class="{{ status }}">{{ status | upcase }}</figcaption>
{% else %}
<figcaption class="uncategorized">UNCATEGORIZED</figcaption>
{% endif %}
</a>
</figure>
{% endfor %}
</div>
{% endif %}
{% endfor %}
