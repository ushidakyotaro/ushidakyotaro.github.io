---
layout: default
title: "Contact"
permalink: /en/contact/
ref: contact
description: "Contact information for Kyotaro Ushida."
---

<div class="contact-container">

  <section class="contact-intro">
    <h1>Contact</h1>
    <p>
      Please feel free to contact me by email or via the form below.
    </p>

    <div class="contact-email-box">
      <i class="far fa-envelope"></i>
      <span class="label">Email:</span>
      {% include email.html %}
    </div>

    {% if site.data.social %}
    <div class="social-links">
      {% for sns in site.data.social %}
        <a href="{{ sns.url }}" target="_blank" rel="noopener noreferrer" class="social-btn">
          <i class="{{ sns.icon }}"></i> {{ sns.name }}
        </a>
      {% endfor %}
    </div>
    {% endif %}
  </section>

  <hr class="divider">

  <section class="form-section">
    <h2>Contact Form</h2>
    <p style="font-size: 0.9em; color: #666;">The form is written in Japanese, but you may answer in English.</p>
    <div class="iframe-wrapper">
      <iframe src="https://forms.gle/oAgkfyva773NKtX57" width="100%" height="800" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
    </div>
  </section>

</div>
