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

I’m a  Computer Science Student ,based in Bangalore, with a deep passion for understanding how the universe around us works. Currently, I’m teaching myself machine learning and deep learning, driven by curiosity and a desire to build and improve technologies. I thrive on pushing the boundaries of what’s possible and exploring new frontiers in tech.

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