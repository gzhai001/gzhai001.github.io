---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

My research applies **causal inference and machine learning** to pressing transportation problems, organized around two complementary themes: learning *what works* for safety, and learning *why people choose* the mobility options they do. The common thread is a commitment to credible inference — methods that separate real policy and design effects from confounding, and models of behavior that remain interpretable at the moment of decision-making.

<img class="gz-fig" src="/images/hero-pipeline.svg" alt="Research overview: crash records, behavioral big data, and stated choices feed causal inference and machine learning methods — propensity scores, difference-in-differences, doubly robust estimation, Bayesian ML, choice models, and LLMs — which inform safer transportation systems and sustainable shared mobility" width="100%">
<p class="gz-figcap">From multimodal data to decisions: causal inference × machine learning across both research themes.</p>

## Theme I: Causal Inference for Transportation Safety

<img class="gz-fig" src="/images/theme1-causal-inference.svg" alt="Causal inference framework: treatment and policy affect safety outcomes, confounded by built environment and exposure, identified via propensity scores, difference-in-differences, and doubly robust estimation" width="100%">

How can we credibly measure the safety effects of policies, vehicles, and infrastructure? Transportation safety questions are causal at their core — but crash data is noisy, interventions are never randomized, and exposure is hard to observe. I develop and apply causal inference designs — propensity score matching, (spatial) difference-in-differences, doubly robust estimation, and Bayesian learning — to produce evidence that policymakers can act on with confidence. Increasingly, this theme also asks how generative AI and vision-language models can *create* the rare, safety-critical situations we hope to prevent.

<div class="gz-methods">
  <span class="gz-tag">propensity score matching</span>
  <span class="gz-tag">spatial difference-in-differences</span>
  <span class="gz-tag">doubly robust estimation</span>
  <span class="gz-tag">Bayesian safety performance functions</span>
  <span class="gz-tag">generative scenario synthesis</span>
  <span class="gz-tag">vision-language models</span>
</div>

Representative work:

- **Citywide speed limit reduction** — PSM + spatial DiD evaluation of a real policy, isolating its true crash-reduction effect (TR-A 2022; <a href="https://doi.org/10.1016/j.tra.2022.01.004">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-speed-did.png" alt="Spatial difference-in-differences estimates of crash changes after the speed limit reduction" width="70%">
- **Equity-aware safety performance functions** — embedding social equity into pedestrian-crash hotspot identification (AAP 2024; <a href="https://doi.org/10.1016/j.aap.2024.107759">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-equity-map.jpg" alt="Demographic equity dimensions across Virginia census tracts" width="70%">
- **Ride-hailing vs. taxi safety** — multivariate spatial comparisons with explicit accommodation of exposure uncertainty (AAP 2023; <a href="https://doi.org/10.1016/j.aap.2023.107281">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-ridehailing-maps.jpg" alt="Spatial distribution of severe ride-hailing crashes and minor taxi crashes in Chicago" width="70%">
- **Safety-critical scenario generation** — generative AI for realistic vehicle–pedestrian interaction scenarios used in autonomous-vehicle safety evaluation (TR-C 2027; <a href="https://doi.org/10.1016/j.trc.2026.106002">doi</a>).
  <img class="gz-fig" src="/images/pub-scenario-gen.svg" alt="Generative loop producing safety-critical vehicle-pedestrian crossing scenarios" width="70%">

## Theme II: AI-Driven Behavioral Analytics for Sustainable Shared Mobility

<img class="gz-fig" src="/images/theme2-shared-mobility.svg" alt="Behavioral analytics pipeline: GPS trajectories and built-environment data feed discrete choice and machine learning models of ride-hailing, metro, e-scooter, and urban air mobility choices" width="100%">

How do people choose and use shared mobility services, and how do the built environment and pricing shape those choices? Shared mobility generates rich behavioral data — GPS trajectories, transactions, stated choices — but the relationships we care about are nonlinear, spatially heterogeneous, and entangled with policy. I combine discrete choice models with interpretable machine learning (BART, random forests, SHAP) to recover behavioral structure that both predicts well and explains itself, with applications from ride-hailing and micromobility to urban air mobility.

<div class="gz-methods">
  <span class="gz-tag">discrete choice models</span>
  <span class="gz-tag">Bayesian additive regression trees</span>
  <span class="gz-tag">geographically weighted random forest</span>
  <span class="gz-tag">SHAP &amp; partial dependence</span>
  <span class="gz-tag">latent class analysis</span>
  <span class="gz-tag">spatial heterogeneity</span>
</div>

Representative work:

- **Shared e-scooter expenses** — Bayesian learning (BART+LN) reveals nonlinear built-environment drivers of zonal shared e-scooter usage (TR-D 2025; <a href="https://doi.org/10.1016/j.trd.2025.105020">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-escooter-framework.png" alt="BART+LN modeling framework for shared e-scooter trip expenses" width="70%">
- **Taxi-metro competition** — Bayes-BART quantifies how trip attributes, built environments, and station features drive taxi–metro competition (TR-D 2026; <a href="https://doi.org/10.1016/j.trd.2026.105637">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-taximetro-importance.jpg" alt="Relative importance of trip, built-environment, and station attributes in taxi-metro competition" width="55%">
- **Bike-and-ride patterns** — geographically weighted random forest maps station-level importance of built-environment factors for bike-and-ride trips (TBS 2026; <a href="https://doi.org/10.1016/j.tbs.2025.101201">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-bikeride-grid.jpg" alt="Station-level importance of built-environment factors for bike-and-ride trips across metro networks" width="80%">
- **Urban air mobility preferences** — latent-class discrete choice with mixed-logit extensions uncovers heterogeneous preferences for air-taxi services (TBS 2026; <a href="https://doi.org/10.1016/j.tbs.2025.101229">doi</a>).
  <img class="gz-fig" src="/images/pubs/pub-uam-shares.jpg" alt="Stated mode-choice shares for urban air mobility across age, income, and gender segments" width="70%">

## Research Funding

| Project | Funder | Role | Period |
|---|---|---|---|
| Causal Decision-Making for Safe Systems | Ministry of Education, Overseas Postdoctoral Talent Program | <span class="gz-role pi">PI</span> | 2027–2029 |
| Causal Inference Approach to Missing-Not-at-Random Mechanism Identification and Collaborative Imputation in Crash Data | NSFC Young Scientists Fund | <span class="gz-role pi">PI</span> | 2026–2028 |
| Multimodal AI-Driven Demand Identification and Route Planning for Urban Air Mobility | Fundamental Research Funds for the Central Universities | <span class="gz-role copi">Co-PI</span> | 2026–2027 |
| Digital Sisters: A Causally-Grounded Framework for Urban Mobility Knowledge Transfer in Data-Scarce Cities | National Natural Science Foundation of China | <span class="gz-role copi">Co-PI</span> | 2026–2027 |
| Home and Firm Location Choice Models and Platform Development | Urban Redevelopment Authority, Singapore | Research Fellow | 2024–2027 |
| Factors Influencing Pedestrian Decisions to Cross Mid-Block and Potential Countermeasures | FHWA & Virginia DOT | Research Assistant | 2022–2024 |
| Improving Safety Service Patrol Performance | FHWA & Virginia DOT | Research Assistant | 2021–2023 |
| Statewide Landslide Risk Assessment on Transportation Infrastructure in Virginia | Old Dominion University Internal Research Grant | Research Assistant | 2022–2024 |
{: class="gz-grants"}
