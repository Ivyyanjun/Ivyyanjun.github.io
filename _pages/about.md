---
permalink: /
title: "Home"
author_profile: true
show_news: true
redirect_from:
  - /about/
  - /about.html
---

I'm a researcher and instructor at the **China Central Academy of Fine Arts (CAFA)**. Before CAFA, I was a Postdoc Fellow at **The Hong Kong University of Science and Technology (HKUST)**, working under the guidance of Associate Professor [Xiaojun Ma (麻晓娟)](https://www.cse.ust.hk/~mxj/). Before joining HKUST, I worked with Professor Xin Wei Sha and Mina Johnson at **Arizona State University**, and with Hiroshi Ishii's Tangible Media Group at the **MIT Media Lab**.

My research focuses on Human-Computer Interaction, responsive environments for children's social well-being, and Human-AI agent interaction for sociality. My current research interests lie in AI integration with design, exploring AI-mediated methods to promote children's social well-being.

Research Interests
------
- Human-Computer Interaction
- Human-AI Interaction
- Responsive multi-sensory environments for children's social well-being
- Embodied games for children's education

Recent Publications
------
{% assign recent_pubs = site.publications | sort: "date" | reverse %}
{% for post in recent_pubs limit: 5 %}
- **{{ post.title }}**{% if post.venue %} — *{{ post.venue }}*{% endif %}
{% endfor %}

[See all publications →](/publications/)
