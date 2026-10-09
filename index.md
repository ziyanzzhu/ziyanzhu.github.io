---
layout: page
title: Home
---


<p class="front-title-font">Designing quantum materials on demand </p>
<div class="research-background-image-container"></div>

<p class="front-body-font">

	We develop numerical models to predict and understand emergent quantum phenomena by studying the coupling between lattices, electrons, and spins. 
	Our multiscale framework bridges atomistic simulations with the mesoscopic properties of large aperiodic quantum materials. We aim to guide experimental searches for exotic phases of matter, from superconductivity to topological states.
	
</p>

<div class="news-section">
	<h3 class="news-heading">News</h3>
	<ul class="news-list">
		{% for item in site.data.news limit:5 %}
		<li>
			<span class="news-date">{{ item.date }}</span>
			<span class="news-text">{{ item.text }}{% if item.url %} <a href="{{ item.url }}">{{ item.link_text | default: "Read more" }}</a>{% endif %}</span>
			{% if item.logo %}<img class="news-logo" src="{{ item.logo }}" alt="{{ item.logo_alt }}">{% endif %}
		</li>
		{% endfor %}
	</ul>
</div>


<!--


<p class="research-body-font">

	Realistic quantum materials are often large and aperiodic.
	They contain millions of atoms, and their complexity is further compounded by interactions with electrons, phonons (lattice vibrations), and other quasiparticles. These interactions result in an exponential increase in the system's dimensionality. Traditional theoretical models for quantum materials either require an impractically large amount of computational power or rely on overly crude approximations.
</p>
<p class="research-body-font">
	To address these challenges, we employ a hierarchical modeling approach that integrates first-principles density functional theory (DFT) calculations, low-energy continuum models, effective many-body models, and machine learning techniques. The combination of these approaches allows us to effectively model aperiodic systems and understand their emergent properties.
</p> -->






