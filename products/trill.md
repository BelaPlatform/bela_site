---
layout: product-page
section_id: products
hero-image: trill-hero.png
title: Trill touch sensors
sub-title: Capacitive touch sensing inspired by musicians, designed for makers
permalink: /products/trill/
---

{% include photocaption.html src='trill-family.png' %}

Trill is a family of touch sensors designed by Bela. [Launched in 2019 on Kickstarter](https://www.kickstarter.com/projects/423153472/trill-touch-sensing-for-makers?ref=5h34wt&token=6b96b598), Trill sensors are designed to place the power of high-resolution touch sensing in the hands of artists, designers, musicians, and creative makers of all kinds.

<h2>For natural, beautiful touch sensing</h2>

Trill was inspired by the way we use our hands to interact with the world. Harnessing the power of capacitive touch sensing for interaction, Trill sensors come in a range of shapes, sizes and types to create a convenient way of integrating beautiful touch sensing into any interactive project.

<h2>Build beautiful, custom touch interfaces</h2>

Trill sensors can be used individually, or chained together to make even larger surfaces. You can use up to 8 of a single Trill type, or a network of different Trill sensors for a totally custom, perfectly crafted interface.

Trill sensors are also highly customisable. Not only can they be trimmed to size to fit exactly where they need to, but they can also be covered and fully embedded in a project, and calibrated in software for exactly the right responsiveness and sensitivity you need.

<h2>Designed for Bela, widely compatible</h2>

Though Trill touch sensors are designed to take advantage of Bela's low-latency processing, they are compatible with any system that supports I2C communication such as Arduino, Teensy and Raspberry Pi. Download the Trill library and example projects for Bela and other platforms on <a href="https://learn.bela.io/products/trill/about-trill/">the Trill Github repo</a>.

<h2>Types of Trill sensors</h2>

{% for item in site.data.product_list.trill %}
<div class='row product-item'>
    <div class='medium-4 columns'>
      <img class="fadeinleft" alt="" src="{{ site.baseurl }}/images/products/trill/{{ item.image }}"/>
    </div>
    <div class='medium-8 columns'>
      <div class='spacing'></div>
      <h2>{{ item.title }}</h2>
      <div class='spacing'></div>
      <p>{{ item.desc }}</p>
      <div class='spacing'></div>
      <h3>Dimensions: {{ item.dimensions }}</h3>
      <a class='button buy' href="{{ item.url }}" target='_blank'>Buy {{ item.title }} now <i class='fas fa-arrow-right'></i></a>
  </div>
</div>
{% endfor %}
