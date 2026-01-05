---
layout: default
title: "Contact"
permalink: /contact/
---

<div class="contact-container">
  
  <section class="contact-intro">
    <h1>Contact</h1>
    <p>
      お問い合わせは、<br>
      以下のメールアドレス、またはGoogleフォームよりお願いいたします。
    </p>

    <div class="contact-email-box">
      <i class="far fa-envelope"></i>
      <span class="label">Email:</span>
      <a href="mailto:{{ site.email }}">{{ site.email }}</a>
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
    <h2>お問い合わせフォーム</h2>
    <div class="iframe-wrapper">
      <iframe src="https://forms.gle/oAgkfyva773NKtX57" width="100%" height="800" frameborder="0" marginheight="0" marginwidth="0">読み込んでいます…</iframe>
    </div>
  </section>

</div>