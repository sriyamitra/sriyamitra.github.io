---
layout: page
title: experience
permalink: /experience/
nav: true
nav_order: 2
---

<style>
  .exp-list {
    list-style: none;
    padding-left: 0;
    margin-top: 1.5rem;
  }
  .exp-item {
    margin-bottom: 2.75rem;
    padding-bottom: 1.75rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .exp-item:last-child {
    border-bottom: none;
  }
  .exp-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 0.35rem;
  }
  .exp-title-group {
    flex: 1 1 min-content;
  }
  .exp-role {
    font-size: 1.25rem;
    font-weight: 700;
    margin: 0;
    line-height: 1.3;
    color: var(--global-text-color);
  }
  .exp-company {
    font-weight: 400;
    color: var(--global-theme-color);
  }
  .exp-logo {
    max-height: 28px;
    width: auto;
    object-fit: contain;
    margin-left: 0.75rem;
    opacity: 0.9;
  }
  .exp-meta {
    font-size: 0.875rem;
    font-family: monospace;
    font-weight: 600;
    color: var(--global-text-color-light);
    margin-bottom: 0.75rem;
  }
  .exp-highlights {
    margin-top: 0.5rem;
    padding-left: 1.25rem;
    line-height: 1.6;
    color: var(--global-text-color);
  }
  .exp-highlights li {
    margin-bottom: 0.4rem;
  }
</style>

<ul class="exp-list">
  <!-- BioMeBar -->
  <li class="exp-item">
    <div class="exp-header">
      <div class="exp-title-group">
        <h4 class="exp-role">
          GTM Analyst — <span class="exp-company">BioMeBar (Healthcare Startup)</span>
        </h4>
      </div>
      <img src="{{ '/assets/img/companies/BioMeBarLogo.svg' | relative_url }}" alt="BioMeBar" class="exp-logo">
    </div>
    <div class="exp-meta">[Jun 2026 – Present] | Healthcare Startup / Hybrid</div>
    <ul class="exp-highlights">
      <li>Rebuilt founder-led partner prospecting from manual search into an AI agent system (Claude skills + Google Sheets API), screening 350+ healthcare clinics and generating personalized message-ready leads.</li>
      <li>Analyzed ad creative from 10+ competitors alongside impression and engagement data from past campaigns, translating patterns into a paid acquisition roadmap for the next quarter.</li>
      <li>Defined the ICP and 1–10 scoring model across 3 clinical segments (GI/IBS, GLP-1/metabolic, and women’s health) with automated filters eliminating unreachable accounts.</li>
      <li>Eliminated wrong-contact outreach with a 9-point QA pass re-verifying founder identity, clinical specialty, location, and competitor overlap.</li>
      <li>Shipped a real-time pipeline dashboard (Cloudflare Pages + Apps Script API) that auto-stages leads and refreshes daily worklists.</li>
    </ul>
  </li>

  <!-- Accenture -->
  <li class="exp-item">
    <div class="exp-header">
      <div class="exp-title-group">
        <h4 class="exp-role">
          Business Consulting Analyst — <span class="exp-company">Accenture Strategy &amp; Consulting</span>
        </h4>
      </div>
      <img src="{{ '/assets/img/companies/AccentureLogo.svg' | relative_url }}" alt="Accenture" class="exp-logo">
    </div>
    <div class="exp-meta">[Aug 2023 – Jul 2025] | Global / Enterprise</div>
    <ul class="exp-highlights">
      <li>Owned SQL-based audience segmentation across 4+ enterprise data sources for 40+ campaigns, targeting 100K+ users globally on Salesforce Marketing Cloud.</li>
      <li>Redesigned end-to-end campaign launch workflows, cutting time-to-launch from 4 weeks to 2 weeks by standardizing segmentation logic and automating QA pipelines.</li>
      <li>Built and maintained Power BI KPI dashboards tracking campaign conversion funnels in real time; synthesized findings into executive presentations guiding global targeting priorities.</li>
      <li>Documented standardized campaign guidelines and mentored 10+ global analysts, reducing execution friction and boosting cross-market delivery consistency.</li>
    </ul>
  </li>

  <!-- Ernst & Young (EY) -->
  <li class="exp-item">
    <div class="exp-header">
      <div class="exp-title-group">
        <h4 class="exp-role">
          Technology Consulting Intern — <span class="exp-company">Ernst &amp; Young (EY)</span>
        </h4>
      </div>
      <img src="{{ '/assets/img/companies/EYLogo.svg' | relative_url }}" alt="EY" class="exp-logo">
    </div>
    <div class="exp-meta">[May 2022 – Jul 2022] | San Jose, CA / Remote</div>
    <ul class="exp-highlights">
      <li>Led structured competitive analysis across enterprise data privacy platforms, creating a stakeholder comparison framework that directly drove vendor selection.</li>
      <li>Performed data quality audits across compliance reporting datasets; mapped governance workflows end-to-end to eliminate manual automation gaps.</li>
    </ul>
  </li>

  <!-- TCS -->
  <li class="exp-item">
    <div class="exp-header">
      <div class="exp-title-group">
        <h4 class="exp-role">
          System Engineer — <span class="exp-company">Tata Consultancy Services (TCS)</span>
        </h4>
      </div>
      <img src="{{ '/assets/img/companies/TCSOldLogo.png' | relative_url }}" alt="TCS" class="exp-logo">
    </div>
    <div class="exp-meta">[Jul 2019 – Jul 2021] | Enterprise Systems</div>
    <ul class="exp-highlights">
      <li>Built and owned 15+ enterprise B2B data integration pipelines using SAP PI/PO, SAP CPI, and Dell Boomi, maintaining data integrity and automated ETL delivery.</li>
      <li>Designed production monitoring and proactive alerting frameworks, resolving data disruptions to achieve zero-downtime ETL automation across enterprise client systems.</li>
    </ul>
  </li>
</ul>
