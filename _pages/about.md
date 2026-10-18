---
permalink: /
author_profile: true
show_news: true
redirect_from:
  - /about/
  - /about.html
---
I am a researcher and instructor in Human-Computer Interaction at the **China Central Academy of Fine Arts (CAFA)**. Before joining CAFA, I was a postdoctoral researcher at the [HCI Initiative](https://hci.cse.ust.hk/), **The Hong Kong University of Science and Technology (HKUST)**, working with Prof. [Xiaojun Ma (麻晓娟)](https://www.cse.ust.hk/~mxj/). Prior to HKUST, I was a research fellow with Prof. [Mina Johnson](https://immerse.illinois.edu/symposium-speakers/Johnson-Glenberg-Mina) at the Sanford Harmony Institute, a children's cognitive developmental science research lab at **Arizona State University (ASU)**. I received my Ph.D. in Media Arts and Sciences from ASU, advised by Prof. [Sha Xin Wei](https://ontheimage.com/2025-conference/sha-xin-wei) and Prof. Lauren Hayes. Earlier in my career, I spent a year studying and working with Prof. Hiroshi Ishii's [Tangible Media Group](https://tangible.media.mit.edu/) at the **MIT Media Lab**.

My research focuses on Human-Computer Interaction, Embodied XR design for children's social well-being, and Human-AI agent interaction for sociality. My current research interests lie in AI integration with design, exploring AI-mediated methods to promote human's social well-being.


Recent Publications
------
{% assign recent_pubs = site.publications | sort: "date" | reverse %}
{% for post in recent_pubs limit: 5 %}
- **{{ post.title }}**{% if post.venue %} — *{{ post.venue }}*{% endif %}
{% endfor %}

[See all publications →](/publications/)
