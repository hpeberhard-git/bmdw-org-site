---
layout: default
title: "In Memory of Jack"
permalink: /
---

<section class="memory-intro">
  <p>
    Jack touched so many lives with his kindness, his humour, and his dedication.
    On this page, we invite friends and colleagues to share their memories,
    messages, and moments with him.
  </p>
  <p>
    Your words will help us celebrate the life of someone who gave so much to others.
  </p>

  <hr>

  <h2>Ter nagedachtenis aan Jack</h2>
  <p>
    Jack heeft zoveel mensen geraakt met zijn vriendelijkheid, zijn humor en zijn toewijding.
    Op deze pagina nodigen we vrienden en collega’s uit om hun herinneringen,
    woorden en momenten met hem te delen.
  </p>
  <p>
    Jullie bijdragen helpen ons om het leven te vieren van iemand die zoveel heeft gegeven.
  </p>
</section>

<section class="memory-share">
  <h3>Share your memory / Deel je herinnering</h3>

  <p>
    We warmly invite you to share your memories, stories, and thoughts about Jack.
    You may write in English or Dutch. If you like, you can also share a photo
    that we may include alongside your message on this page.
  </p>

  <p>
    We nodigen je van harte uit om je herinneringen, verhalen en gedachten over Jack te delen.
    Je mag in het Engels of in het Nederlands schrijven. Als je wilt, kun je ook een foto delen
    die we – indien mogelijk – samen met je bericht op deze pagina plaatsen.
  </p>

  <p>
    You can submit your message without a Google account.  
    If you would like to include a photo, you may email it to us and we will
    add it to the memorial page together with your message.
  </p>

  <p>
    Je kunt je bericht insturen zonder Google-account.  
    Als je een foto wilt toevoegen, kun je die per e-mail sturen; we plaatsen
    de foto dan samen met je bericht op de herdenkingspagina.
  </p>

  <p>
    <a href="https://forms.gle/L6mK816z5vPGMo1K7"
       class="btn"
       target="_blank" rel="noopener">
      Open form / Open formulier
    </a>
  </p>
</section>

<section class="memory-list">
  <h3>Memories / Herinneringen</h3>

  {% assign memories = site.memories | sort: "date" | reverse %}
  {% for memory in memories %}
  <article class="memory-card">
    <p class="memory-meta">
      {% if memory.name %}
        <strong>{{ memory.name }}</strong>
        {% if memory.date %} – {{ memory.date | date: "%-d %B %Y" }}{% endif %}
      {% elsif memory.date %}
        {{ memory.date | date: "%-d %B %Y" }}
      {% endif %}
    </p>

    {% if memory.photo %}
    <figure class="memory-photo">
      <img src="{{ memory.photo | relative_url }}"
           alt="{{ memory.photo_alt | default: 'Memory photo' | escape }}">
      {% if memory.photo_caption %}
      <figcaption>{{ memory.photo_caption }}</figcaption>
      {% endif %}
    </figure>
    {% endif %}

    <div class="memory-body">
      {{ memory.content | markdownify }}
    </div>
  </article>
  {% endfor %}
</section>