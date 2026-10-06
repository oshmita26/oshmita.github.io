---
layout: page
title: Medi-assist
description: A bot supporting pre-clinical diagnosis based on your systems
img: assets/img/mediassist.jpg
importance: 2
category: fun
giscus_comments: false
---

## Demo

<!--
  Demo hosted on Google Drive. Drive files can't use al-folio's video.liquid include
  (that builds a YouTube/Vimeo-style iframe), so we embed Drive's own /preview player.
  Requirement: the Drive file's sharing must be "Anyone with the link - Viewer",
  otherwise visitors hit a sign-in wall.
  To swap the video, replace the FILE_ID in the /preview URL below.

  The video matches the text content width (it sits in al-folio's normal content
  column, respecting the same left/right margins as the surrounding text). The iframe
  is given an explicit responsive height (clamp) and fills 100% of its wrapper so the
  Drive player uses the whole allocated area instead of letterboxing a small video.
-->

<div style="width: 100%; height: clamp(480px, 70vh, 820px);">
    <iframe
        src="https://drive.google.com/file/d/13_3ZDKrJtSN-k7RAZigQpQmvJiogQ6MP/preview"
        title="Medi-assist demo"
        class="z-depth-1"
        style="width: 100%; height: 100%; border: 0; display: block;"
        allow="autoplay"
        allowfullscreen
        loading="lazy"
    ></iframe>
</div>
<div class="caption">
    A short walkthrough of Medi-assist.
</div>

## Links

- Source code: [shrutidebnath/medi-assist](https://github.com/shrutidebnath/medi-assist)
