---
permalink: /
author_profile: true
show_news: true
redirect_from:
  - /about/
  - /about.html
---

I'm a researcher and instructor of Human-Computer Interaction at the **China Central Academy of Fine Arts (CAFA)**. Before CAFA, I was a Post-doctoral researcher at [HCI Initiative](https://hci.cse.ust.hk/) of **The Hong Kong University of Science and Technology (HKUST)** with Prof.[Xiaojun Ma (麻晓娟)](https://www.cse.ust.hk/~mxj/). Before joining HKUST, I worked with Prof.[Sha Xin Wei](https://ontheimage.com/2025-conference/sha-xin-wei) and Prof.[Mina Johnson](https://immerse.illinois.edu/symposium-speakers/Johnson-Glenberg-Mina) at Sanford Harmony Institute at **Arizona State University**, and with Hiroshi Ishii's [Tangible Media Group](https://tangible.media.mit.edu/) at the **MIT Media Lab**.

My research focuses on Human-Computer Interaction, responsive environments for children's social well-being, and Human-AI agent interaction for sociality. My current research interests lie in AI integration with design, exploring AI-mediated methods to promote children's social well-being.


Recent Publications
------
{% assign recent_pubs = site.publications | sort: "date" | reverse %}
{% for post in recent_pubs limit: 5 %}
- **{{ post.title }}**{% if post.venue %} — *{{ post.venue }}*{% endif %}
{% endfor %}

[See all publications →](/publications/)
