---
layout: about
title: Home
permalink: /
subtitle: ""  # Empty string instead of null

banner:
  image: cs_building.jpg 
  alt_text: "Dalhousie University, Faculty of Computer Science Building"

news_items:
  - date: 2024
    title: "Accepted Papers 2024"
    content: "2 papers (NeurIPS), 2 papers (NAACL), 2 papers (EMNLP)"
  - date: 2023
    title: "Accepted Papers 2023"
    content: "3 conference papers (NeurIPS, ICLR, ACL), 1 Journal (JMLR), 3 demo papers (AAAI, ACL, EACL)"
  - date: 2023
    content: "NeurIPS 2023: Evaluating Neuron Interpretation Methods of NLP Models"
  - date: 2023
    content: "ICLR 2023: Learning Uncertainty for Unknown Domains with Zero-Target-Assumption"
  - date: 2023
    content: "JMLR 2023: Discovering Salient Neurons in deep NLP models"
  - date: 2023
    content: "ACL Demo 2023: NeuroX 2.0 Library for Neuron Analysis of Deep NLP Models"
  - date: 2023
    content: "ACL findings 2023: Impact of Adversarial Training on Robustness and Generalizability of Language Models"

selected_papers: false
social: false

groups:
  - staff
  - affiliated 
  - alumni

staff:
  title: Research Staff
  people:
    - name: Hassan Sajjad
      description: Prof. Dr. and Head of HyperMatrix
      website: https://hsajjad.github.io/
      picture: hassan.png
    - name: David Arps
      description: PhD student
      website: https://davidarps.github.io/
      picture: david.jpeg
    - name: Domenic Rosati
      description: PhD student
      website: https://domenicrosati.github.io/
      picture: domenic.jpg
    - name: Paolo Gajo
      description: PhD student
      website: https://scholar.google.com/citations?user=ryn1awMAAAAJ&hl=en
      picture: paolo.jpeg
    - name: Hamad Rizwan
      description: PhD student
      website: https://scholar.google.com/citations?user=vERBCLMAAAAJ&hl=en
      picture: hamad.jpeg
    - name: Sher Badshah
      description: PhD student
      website: https://web.cs.dal.ca/~badshah/
      picture: sher.jpeg
    - name: Xuemin Yu
      description: PhD student
      website: https://xueminyu.com/
      picture: xuemin.png
    - name: Manpreet Singh
      description: Master student
      website: https://msingh-cse.github.io/
      picture: manpreet.jpeg

affiliated:
  title: Research Collaborators
  people:
    - name: Enyu Ye
      description: Undergraduate student
      website: ""
      picture: ""
    - name: Nouri Marzia
      description: Undergraduate student
      website: ""
      picture: ""
      
alumni:
  title: Alumni
  people:
    - name: Manpreet Singh
      description: Master student
      website: https://msingh-cse.github.io/
      picture: manpreet.jpeg
    - name: Magen Cao
      description: Bachelor student
      website: ""
      picture: ""

sponsors:
  - name: Faculty of Computer Science, Dalhousie University
    website: https://www.dal.ca/faculty/computerscience.html
    logo: dal.png
  - name: Natural Sciences and Engineering Research Council of Canada (NSERC)
    website: https://www.nserc-crsng.gc.ca/
    logo: nserc.png
  - name: Research Nova Scotia
    website: https://researchns.ca/
    logo: research_ns.png
  - name: MITACS
    website: https://www.mitacs.ca/?hsLang=en
    logo: mitacs.png
---

<div class="projects">
  <h2 class="category">About Us</h2>
  <div class="about-content">
    Welcome! We are the HyperMatrix research lab at Dalhousie University, Halifax, Canada, directed by <a href="https://hsajjad.github.io/">Prof. Hassan Sajjad</a>. We conduct cutting-edge research in Artificial Intelligence, focusing on Natural Language Processing, Deep Learning, and Safe and Trustworthy AI.
    
    <p style="margin-top: 1rem;">Our mission is to advance the field of AI by making models that are not only powerful but also transparent, safe, and aligned with social needs. Our research interests include language generation, interpretability, explainability, generalization, robustness, and model editing—all with the aim of developing trustworthy AI systems.</p>
  </div>

  <h2 class="category">News</h2>
  <div class="news">
    <ul>
      {% for item in page.news_items %}
      <li class="news-item">
        {% if item.title %}
          <strong>{{ item.title }}:</strong>
        {% endif %}
        {{ item.content }}
      </li>
      {% endfor %}
    </ul>
  </div>

  {%- for group in page.groups -%}
    <h2 class="category">{{page.[group].title}}</h2>
    <div class="grid">
      {%- for person in page.[group].people -%}
        <article class="grid-item card">
          {% if person.picture -%}
            <img class="avatar" src="/assets/img/{{person.picture}}" alt="Portrait ({{person.name}})" width="auto" height="auto">
          {%- else -%}
            <img class="avatar" src="/assets/img/hyper_matrix.png" alt="Portrait ({{person.name}})" width="auto" height="auto">
          {%- endif -%}
          <div class="card-body">
            <h2 class="card-title">
              {% if person.website -%}
                <a href="{{person.website}}">{{person.name}}</a>
              {%- else -%}
                {{person.name}}
              {%- endif -%}
            </h2>
            <div class="card-text">
              {{person.description}}
            </div>
          </div>
        </article>
      {%- endfor -%}
    </div>
  {%- endfor -%}

  <h2 class="category">Organizations</h2>
  <p>Our research is supported by:</p>
  <div class="sponsors">
    {%- for sponsor in page.sponsors -%}
      <div class="sponsor-item">
        <a href="{{ sponsor.website }}" target="_blank">
          <img src="/assets/img/{{ sponsor.logo }}" alt="{{ sponsor.name }} Logo">
        </a>
      </div>
    {%- endfor -%}
  </div>

  <h2 class="category">Find us</h2>
  <p>We are located at 6050 University Ave, Halifax, NS B3H 1W5 (<a href="/contact">→ directions</a>).</p>
  <p><a href="https://www.dal.ca/faculty/computerscience.html"><i class="fa fa-university" aria-hidden="true"></i> Faculty of Computer Science, Dalhousie University, Halifax, NS</a></p>
  <p><a href="https://twitter.com/hassaan84s"><i class="fab fa-twitter"></i> Hassan Sajjad</a></p>
</div>
