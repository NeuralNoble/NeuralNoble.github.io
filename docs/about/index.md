---
hide:
  - navigation
  - feedback
  - toc
search:
  exclude: true
icon: material/account-box
---

# I'm Aman Anand

<style>
  @media (min-width: 900px) {
    main > div > div.md-content {
      max-width: 75%;
      margin: auto;
    }
  }
  article > h1 { display: none; }
  #my-projects-index { display: none; }
  .md-typeset ul:has(.experiences-li) { list-style-type: none; }
  .md-typeset ul li:has(.experiences-li),
  .md-typeset ul li.experiences-li {
    margin-left: 0;
  }
</style>

<p style="text-align: center; margin: 0px;" markdown>
  <img src="https://avatars.githubusercontent.com/u/156664113?v=4" alt="NeuralNoble" style="width: 300px; border-radius: 50%;" />
  <p class="light" style="text-align: center; font-size: 25px; margin: 0px;"><strong>Aman Anand</strong></p>
</p>

<p style="text-align: justify;" markdown>
I'm an AI/ML enthusiast obsessed with understanding how intelligent systems work and how to build them from the ground up. I love exploring deep learning, computer vision, and generative AI—not just in theory but as tools to create things that matter. I'm constantly experimenting, questioning, and learning—whether it’s cracking the math behind models or designing agentic systems that solve real problems. I think in systems, break things to understand them, and build with intent. My goal? To become one of the best in this field—not just technically, but in how I think and create.
</p>

---

<p align="center" markdown>
{% for social in about.socials|sort(attribute="title") %}
  <a href="{{ social.url }}" title="{{ social.title }}"> :{{ social.icon }}:{ .lg .light } </a>&nbsp; &nbsp;
{% endfor %}
</p>


---

<h2 class="light" align="center"><strong>Experiences</strong></h2>

{% for exp in about.experiences %}

<div class="grid cards" markdown>

  - **{{ exp.title }}**<br>
    <small>{{ exp.company }} **•** {{ exp.period }}</small>

    {% if exp.points|length %} --- {% endif %}

    {% for point in exp.points %}
    - :{{ point.icon }}: {{ point.desc }}
    {: .experiences-li }
    {% endfor %}

</div>

{% endfor %}


---

<h2 class="light" align="center"><strong>Tech Stacks</strong></h2>

<div class="grid cards" markdown>
{% for stack, techs in about.tech_stack.items()|sort(attribute=0) %}
  - **{{ stack }}**
  {: align=center style="margin-bottom: 0;" }

    <hr style="margin-top: 0.3em; margin-bottom: 0.8em;">

    <p align="center" style="margin: 0;">
    {% for tech in techs|sort(attribute='title') %}:{{ tech.icon }}:{ .lg .hover-icon-bounce .{{ tech.icon|replace("simple-", "") }} title="{{ tech.title }}" } &nbsp; {% endfor %}
    </p>
{% endfor %}
</div>

---