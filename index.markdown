---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: splash
header:
    overlay_filter: rgba(237, 27, 47, 0.3)
    overlay_image: /assets/images/head.jpg
---

<link rel="stylesheet" href="./assets/style.css">

We, at **HyperMatrix**, work towards developing **trustworthy** and **responsible AI**. 

The current focus is on the **robustness**, **generalization**, **interpretation** and **explainability** of deep learning models. 

The lab is led by **[Professor Hassan Sajjad](https://hsajjad.github.io/)** at the **[Faculty of Computer Science](https://cs.dal.ca)**, **[Dalhousie University](https://dal.ca)**.


## News 

* We will be at **[ACL 2023](https://2023.aclweb.org/)**. Check out our presentations on:  
  **1)** Impact of Adversarial Training on Robustness and Generalizability of Language Models, <br>
  **2)** Neuron-level Interpretation of Deep NLP Models: A Survey, <br>
  **3)** NeuroX Library for Neuron Analysis of Deep NLP Models<br>
* ICLR 2023: Learning Uncertainty for Unknown Domains with Zero-Target-Assumption <br> Talk by Hassan: Latent Concepts in Transformer Models of NLP. UKP, TU Darmstadt, Germany (Jun. 2023)

<ul>
    {% for post in site.posts %}
        <li class="home_news_item">
        <a href="{{ post.url }}" class="home_news_title">{{ post.title }}</a>
        {{ post.excerpt }}
        </li>
    {% endfor %}
</ul>
