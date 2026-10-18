---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

{% assign all_projects = site.data.projects %}
{% assign leading = all_projects | where: "role", "leading" %}
{% assign participating = all_projects | where: "role", "participating" %}

<div class="proj">
  <div class="proj__meta">
    <span>From 2023 to Present</span>
    <span class="proj__asof">(As of October 2026)</span>
  </div>
  <div class="proj__tabs" role="tablist">
    <button class="proj__tab is-active" data-filter="all">All Projects <span class="proj__count">{{ all_projects.size }}</span></button>
    <button class="proj__tab" data-filter="leading">Leading Projects <span class="proj__count">{{ leading.size }}</span></button>
    <button class="proj__tab" data-filter="participating">Participating Projects <span class="proj__count">{{ participating.size }}</span></button>
  </div>
  <ul class="proj__list">
    {%- for p in all_projects %}
    <li class="proj__item" data-role="{{ p.role }}">
      <i class="fas fa-sitemap proj__icon" aria-hidden="true"></i>
      <div class="proj__body">
        <div class="proj__title">{{ p.title }}</div>
        {% if p.title_zh %}<div class="proj__title">{{ p.title_zh }}</div>{% endif %}
        {% if p.funder %}<div class="proj__funder">{% if p.funder_link %}<a href="{{ p.funder_link }}">{{ p.funder }}</a>{% else %}{{ p.funder }}{% endif %}</div>{% endif %}
        {% if p.award or p.amount %}<div class="proj__team">{% if p.award %}<span>Award #: {{ p.award }}</span>{% endif %}{% if p.amount %}<span>Amount: {{ p.amount }}</span>{% endif %}</div>{% endif %}
        {% if p.team or p.pi %}<div class="proj__team"><span>{{ p.team }}</span><span>{{ p.pi }}</span></div>{% endif %}
        {% if p.years %}<div class="proj__years">{{ p.years }}</div>{% endif %}
        {% if p.desc %}<div class="proj__desc">{{ p.desc }}</div>{% endif %}
      </div>
      <div class="proj__side">
        <span class="proj__badge proj__badge--{{ p.role }}">{% if p.role == "leading" %}Leading{% else %}Participating{% endif %}</span>
        {% if p.logos %}<div class="proj__logos">{% for logo in p.logos %}<img src="{{ logo | prepend: '/images/' | relative_url }}" alt="" onerror="this.remove()">{% endfor %}</div>{% endif %}
      </div>
    </li>
    {%- endfor %}
  </ul>
</div>

<style>
.proj { font-size: 0.85em; border-left: 4px solid #2a4fa8; background: var(--global-footer-bg-color); padding: 0.8em 1.2em 1em; border-radius: 2px; }
.proj__meta { display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 0.5em; padding-bottom: 0.8em; border-bottom: 1px solid var(--global-border-color); }
.proj__asof { font-size: 0.8em; color: var(--global-text-color-light); }
.proj__tabs { display: flex; flex-wrap: wrap; gap: 0.4em; padding: 0.9em 0; border-bottom: 1px solid var(--global-border-color); }
.proj__tab { font: inherit; cursor: pointer; background: none; border: 2px solid transparent; border-radius: 4px; padding: 0.35em 0.8em; color: var(--global-link-color); }
.proj__tab:hover { border-color: var(--global-border-color); }
.proj__tab.is-active { background: #2a4fa8; color: #fff; border-color: #1d3c86; }
.proj__count { display: inline-block; min-width: 1.6em; padding: 0 0.4em; margin-left: 0.3em; border-radius: 0.8em; background: #6c757d; color: #fff; font-size: 0.8em; text-align: center; }
.proj__list { list-style: none; margin: 0; padding: 0; }
.proj__item { display: flex; gap: 0.6em; padding: 0.8em 0; border-bottom: 1px dashed var(--global-dark-border-color); margin: 0; }
.proj__item[hidden] { display: none; }
.proj__icon { margin-top: 0.25em; color: var(--global-text-color); }
.proj__body { flex: 1; min-width: 0; }
.proj__title { color: var(--global-text-color); line-height: 1.4; }
.proj__funder, .proj__funder a { color: #1f9cad; text-decoration: none; }
.proj__team { display: flex; flex-wrap: wrap; gap: 0.3em 3em; font-size: 0.8em; margin: 0.3em 0; }
.proj__years { color: #22a33a; }
.proj__side { display: flex; flex-direction: column; align-items: flex-end; gap: 0.6em; flex-shrink: 0; }
.proj__logos { display: flex; align-items: center; gap: 0.6em; background: #fff; padding: 0.4em 0.6em; border-radius: 4px; }
.proj__logos:empty { display: none; }
.proj__logos img { height: 44px; width: auto; display: block; }
.proj__logos img[src*="tsinghua"] { height: 72px; }
.proj__desc { font-size: 0.85em; line-height: 1.55; margin-top: 0.4em; color: var(--global-text-color); }
@media (max-width: 600px) { .proj__item { flex-wrap: wrap; } .proj__side { flex-direction: row; width: 100%; justify-content: space-between; } }
.proj__badge { align-self: flex-end; font-size: 0.72em; font-weight: 600; color: #fff; padding: 0.15em 0.5em; border-radius: 3px; white-space: nowrap; }
.proj__badge--leading { background: #22a33a; }
.proj__badge--participating { background: #6c757d; }
</style>

<script>
document.querySelectorAll('.proj__tab').forEach(function (tab) {
  tab.addEventListener('click', function () {
    var f = tab.getAttribute('data-filter');
    document.querySelectorAll('.proj__tab').forEach(function (t) { t.classList.toggle('is-active', t === tab); });
    document.querySelectorAll('.proj__item').forEach(function (it) {
      it.hidden = !(f === 'all' || it.getAttribute('data-role') === f);
    });
  });
});
</script>
