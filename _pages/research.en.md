---
layout: page
title: Research
permalink: /research/
description: My academic research interests and projects
nav: true
nav_order: 3
---

<style>
.research-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  max-width: 900px;
  margin: 0 auto;
  padding: 1rem 0;
}

.section-title {
  color: var(--global-theme-color);
  font-size: 1.8rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  text-align: left;
}

/* 自定义样式以适应您的需求 */
.about-card .card-title {
  color: var(--global-theme-color);
}

.card-content h3 {
  color: var(--global-theme-color);
  font-size: 1.1rem; /* 减小Key Research Areas的字体大小 */
  font-weight: 600;
  margin-top: 1rem;
  margin-bottom: 0.8rem;
}
</style>

<div class="about-container">
  <div class="about-card">
    <h2 class="card-title">Research Overview</h2>
    <div class="card-content">
      <p>My research explores computational communication and digital emotional expression, examining how online communities form around shared experiences. I combine computational methods with qualitative approaches to gain insights into group dynamics and shared emotional landscapes within digital spaces.</p>
      
      <h3>Key Research Areas</h3>
      <ul>
        <li><span class="highlight-text">Computational Communication</span>: Applying computational methods to understand communication patterns in digital environments.</li>
        <li><span class="highlight-text">Digital Emotional Expression</span>: Exploring how individuals express and process emotions in online spaces.</li>
        <li><span class="highlight-text">Online Communities</span>: Analyzing the formation, dynamics, and impact of digital communities on individual identity and collective experience.</li>
        <li><span class="highlight-text">Digital Mourning</span>: Investigating the practices and communities that form around grief and remembrance in virtual environments.</li>
        <li><span class="highlight-text">Women's Issues</span>: Focusing on women's expression, identity construction, empowerment, and related gender issues in digital environments.</li>
      </ul>
    </div>
  </div>

  <div class="about-card">
    <h2 class="card-title">Research Projects</h2>
    <div class="card-content">
      {% include research-cards.liquid %}
    </div>
  </div>
</div> 