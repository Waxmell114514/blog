---
permalink: /
title: "Ziwei Liu"
hide_title: true
excerpt: "Data science undergraduate at HKUST working on machine learning research and mechanistic interpretability."
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% include base_path %}

<div class="home" markdown="1">

<header class="home-hero">
  <p class="home-hello">Hi, I'm Ziwei <span class="home-wave" aria-hidden="true">👋</span></p>
  <p class="home-lede">I take neural networks apart to see what is <span class="home-mark">actually</span> going on inside them.</p>
</header>

Most days that means **mechanistic interpretability**: training sparse
autoencoders, patching activations, fitting probes, and staring at hidden states
until they either make sense or stubbornly refuse to. My latest rabbit hole was a
simple question: [if you secretly hijack a robot policy's actions, does anything
inside it notice?]({{ base_path }}/posts/2026/09/hijacking-vla-actions/) As far
as linear probes can tell, no, and that negative result turned into my first
workshop paper.

Since January 2026 I've been an undergraduate research assistant at **PeiLab,
HKUST**, where I train reward models, distil world models, and keep VLA and LLM
training pipelines running. Knowing how a model gets built makes it a lot easier
to guess what is happening inside it, so I like having a foot on both sides.
I'm a second-year **Data Science and Technology** student at
[HKUST](https://hkust.edu.hk) and part of the S. S. Chern Class.

<ul class="home-chips" aria-label="Things I work with">
  <li>sparse autoencoders</li>
  <li>activation patching</li>
  <li>logit lens</li>
  <li>circuit discovery</li>
  <li>linear probes</li>
  <li>reward models</li>
  <li>world models</li>
  <li>VLAs</li>
</ul>

## News

<ul class="home-news">
  <li>
    <span class="home-date">Sep 2026</span>
    <span>🎉 My paper
      <a href="{{ base_path }}/research/reaction-without-attribution/"><em>Reaction Without Attribution: Hijacking a VLA's Actions Reveals No Linearly Readable Efference Copy</em></a>
      was accepted at the <strong>NeurIPS 2026 RoboPAD Workshop</strong>
      (<a href="{{ base_path }}/files/Reaction_Without_Attribution.pdf">PDF</a> ·
      <a href="https://openreview.net/forum?id=1OTHIshAFK">OpenReview</a>).</span>
  </li>
</ul>

## Lately on the blog

I write things up in public because a reader forces a precision a private note
never does, and if a post is wrong, I'd rather find out.

{% assign home_posts = site.posts | slice: 0, 3 %}
<ul class="home-posts">
  {% for post in home_posts %}
  <li>
    <a href="{{ base_path }}{{ post.url }}">
      <span class="home-post-title">{{ post.title }}</span>
      <span class="home-post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
    </a>
  </li>
  {% endfor %}
</ul>
<p class="home-more"><a href="{{ base_path }}/research/">What I'm working on</a> · <a href="{{ base_path }}/year-archive/">All posts</a></p>

{% assign zt_latest = site.zatsudan | sort: "date" | reverse | first %}
{% if zt_latest %}
<aside class="home-aside">
  <p class="home-aside-label">Off the clock</p>
  <p>When I'm not probing models, I write long essays about anime over in
    <a href="{{ base_path }}/zatsudan/">杂谈</a>: why a story works at the
    exact moment it does. Latest:
    <a href="{{ base_path }}{{ zt_latest.url }}">{{ zt_latest.title }}</a></p>
</aside>
{% endif %}

## Say hi

If any of this overlaps with what you're working on, or you think one of my
posts gets something wrong, I'd genuinely like to hear about it. Email me at
[zliuhs@connect.ust.hk](mailto:zliuhs@connect.ust.hk); my code lives on
[GitHub](https://github.com/Waxmell114514). The formal version of all this is on
the [CV]({{ base_path }}/cv/) page
([PDF]({{ base_path }}/files/Ziwei_Liu_CV.pdf)).

</div>
