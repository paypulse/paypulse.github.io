---
layout: default
avatar: true
permalink: /
url: https://google.fr
location:
  latitude: 51.5285582
  longitude: -0.2416807

---
## What is most important things in the Pay-pulse company.
Accurancy, Humanity, sincerity.

---

## Why did i make the Pay-pulse company.

We need more good solution for a measuring instrument and we want to introduce foreign start-up company and sell their product to Korea. so, we made the company.

---
## Who made the Pay-pulse company.
{% for post in site.posts limit:1 %}
  <img src="https://paypulse.github.io/assets/images/test.jpg" width = "20" height ="20" />  
{% endfor %}



---
## When is the birth day of Pay-pulse company.

Individual business , April 3 2017.

---
## Where is the Pay-pulse company.

We are located in South Korea , Byeollae Awesome factory.

{% for post in site.posts limit:1 %}
  {% google_map show_popup="false" zoom="10" %}


{% endfor %}
