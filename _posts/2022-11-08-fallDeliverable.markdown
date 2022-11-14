---
layout: post
title:  "Deliverable for DH900 fall semester"
date:   2022-11-08 14:30:17 -0600
categories: jekyll update
---
Keypoints:

	Building Website: Jekyll, github pages
	Website layout: html, yml, markup
	Mapping: python folium module, leaflet
	NLP & Geoparsing: I don't really need to invent wheels to get things done

What I have now: A ready-to-go program and platform package for deep mapping

What I learned: projects made with "civilian" applications, digital humanities and public history, the open source community, and google is programmers' best friend.

<iframe src="https://lavender-salome-82.tiiny.site" height="600px" width="100%" style="border:none;"></iframe>




Advanced features under construction:

Filter:
 <iframe src="https://vdn3.vzuu.com/SD/92449f6e-03fc-11ec-8fa7-3e3072498e96.mp4?disable_local_cache=1&bu=078babd7&c=avc.0.0&f=mp4&expiration=1668414824&auth_key=1668414824-0-0-7783bec5de9f3c9b02e7035b263ccc82&v=tx&pu=078babd7" height="600px" width="100%" style="border:none;"></iframe>

connect the previous concepts with programatic control flow with Liquid:

<iframe src="https://davidjvitale.com/blog/travel/" height="600px" width="100%" style="border:none;"></iframe>


{% leaflet_map %}
    { "center" : [63.0694,  -151.0074],
                 "zoom" : 7,
                 "providerBasemap": "OpenTopoMap" } 
	 {%- for post in site.posts -%}
        {% if post.location.geojson %}
            {% leaflet_geojson {{post.location.geojson}} %}
        {% elsif post.location.latitude and post.location.longitude %}
            {% leaflet_marker { "latitude" : {{post.location.latitude}},
                                "longitude" : {{post.location.longitude}} } %}
        {% endif %}
    {% endfor %}
{% endleaflet_map %}
