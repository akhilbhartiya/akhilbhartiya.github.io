---
layout: default
title: Home
---

<img src="profile.jpg" alt="Akhil Bhartiya" class="profile-img" />

# Akhil Bhartiya

Ph.D. candidate studying quantum dynamics and nonchaotic systems under [Prof. Tobias Kramer](https://quantumobserver.wordpress.com/) at the [Institute for Theoretical Physics](https://www.jku.at/en/institute-for-theoretical-physics/), Linz.

<ul class="link-buttons">
  <li><a href="mailto:akhil.bhartiya@jku.at">✉️ Email</a></li>
  <li><a href="https://scholar.google.com/citations?user=ZS47oC0AAAAJ&hl=en">🎓 Google Scholar</a></li>
  <li><a href="https://www.linkedin.com/in/bhartiya">💼 LinkedIn</a></li>
  <li><a href="https://github.com/akhilbhartiya">🐙 GitHub</a></li>
  <li><a href="https://orcid.org/0000-0001-8734-1606">🆔 ORCID</a></li>
</ul>

---

## 🔬 Publications

<div class="pub-card">
  <h3><a href="https://doi.org/10.1103/PhysRevE.107.024207">Signatures of strange nonchaotic dynamics in a forced quantum system</a></h3>
  <div class="meta">
    Arnab Acharya, <strong>Akhil Bhartiya</strong>, and Soumitro Banerjee — <em>Phys. Rev. E 107, 024207 (2023)</em>
  </div>
  <p>Numerical computation of wave function evolution in a forced quantum impact oscillator, investigating dynamical signatures and strange nonchaotic behavior.</p>
</div>

---

## ✍️ Recent Posts

{% for post in site.posts limit:5 %}
* **[{{ post.title }}]({{ post.url }})** — *{{ post.date | date: "%B %d, %Y" }}*
{% endfor %}
