---
layout: about
title: Home
permalink: /
subtitle: 

banner:
  image: cs_building.jpg 
  alt_text: "Dalhousie University, Faculty of Computer Science Building"

# profile:
#   align: right
#   image: hyper_matrix.png
#   image_circular: true
#   address:

news: false # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

groups: [staff]
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
    - name: Hamad Rizwan
      description: PhD student
      website: https://scholar.google.com/citations?user=vERBCLMAAAAJ&hl=en
      picture: hamad.jpeg
    - name: Jinkun Chen
      description: PhD student
      website: https://jinkunchen.com/
      picture: jinkun.jpeg
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
      website: https://www.linkedin.com/in/manpreet-singh-52b2271ab
      picture: manpreet.png

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

Welcome!
We are the HyperMatrix research lab at Dalhousie University, Halifax, Canada, directed by [Prof. Hassan Sajjad](https://hsajjad.github.io/). We conduct cutting-edge research in Artificial Intelligence, focusing on Natural Language Processing, Deep Learning, and Safe and Trustworthy AI.

Our mission is to advance the field of AI by making models that are not only powerful but also transparent, safe, and aligned with social needs. Our research interests include language generation, interpretability, explainability, generalization, robustness, and model editing—all with the aim of developing trustworthy AI systems.

<div class="projects">
  <h2 class="category">News</h2>
    <li>Accepted Papers 2024: 2 conference papers (NAACL)</li>
    <li>Accepted Papers 2023: 3 conference papers (Neurips, ICLR, ACL), 1 Journal (JMLR)</li>
    <li>Neurips 2023: Evaluating Neuron Interpretation Methods of NLP Models</li>
    <li>ICLR 2023: Learning Uncertainty for Unknown Domains with Zero-Target-Assumption</li>
    <li>JMLR 2023: Discovering Salient Neurons in deep NLP models</li>
    <li>ACL Demo 2023: NeuroX 2.0 Library for Neuron Analysis of Deep NLP Models</li>
    <li>ACL findings 2023: Impact of Adversarial Training on Robustness and Generalizability of Language Models</li>

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
            <!-- <h2 class="card-title">{{person.name}}</h2> -->
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

  <!-- <h2 class="category">Join Our Team</h2>
  Join us! <a href="/jobs">→Open positions</a> -->

  <h2 class="category">Organizations</h2>
    Our research is supported by:
  <div class="sponsors">
    {%- for sponsor in page.sponsors -%}
      <div class="sponsor-item">
        <a href="{{ sponsor.website }}" target="_blank">
          <img src="/assets/img/{{ sponsor.logo }}" alt="{{ sponsor.name }} Logo">
        </a>
      </div>
    {%- endfor -%}
  </div>

  <h2 class="category">HyperMatrix resources and code</h2>
  You can find resources (data, code, repositories) released by HyperMatrix lab members <a href="https://github.com/hypermatrixlab">on our github page</a>

  <!-- <h2 class="category">Organizations</h2>
  Our research is supported by:
  <ul>
    <li><a href="https://www.dal.ca/faculty/computerscience.html">Faculty of Computer Science, Dalhousie University</a></li>
    <li><a href="https://www.innovation.ca/">Canada Foundation for Innovation (CFI)</a></li>
    <li><a href="https://www.nserc-crsng.gc.ca/">Natural Sciences and Engineering Research Council of Canada (NSERC)</a></li>
    <li><a href="https://researchns.ca/">Research Nova Scotia</a></li>
    <li><a href="https://www.mitacs.ca/?hsLang=en">MITACS</a></li>
  </ul> -->

 <!-- TODO <img src="MCML_Logo.jpg" alt="MCML logo"/> -->

  <h2 class="category">Find us</h2>
  We are located at 6050 University Ave, Halifax, NS B3H 1W5 (<a href="/contact">→ directions</a>).<br/>
<a href="https://www.dal.ca/faculty/computerscience.html"><i class="fa fa-university" aria-hidden="true"></i> Faculty of Computer Science, Dalhousie University, Halifax, NS</a><br/>
<a href="https://github.com/hypermatrixlab"><i class="fab fa-github"></i> HyperMatrix</a><br/>
<a href="https://twitter.com/hassaan84s"><i class="fab fa-twitter"></i> Hassan Sajjad</a>

</div>
