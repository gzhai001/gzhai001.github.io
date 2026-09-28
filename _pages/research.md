---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

My research enables **causal decision-making for safe systems**, organized around two complementary questions: which safety policies and designs *actually work*, and *why travelers choose* the mobility options they do. Across both themes, the common thread is credible inference — methods that separate real policy and design effects from confounding, and models of behavior that remain interpretable at the moment of decision-making.

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

**Research questions**

- How can crash-reduction effects of real-world policies be identified when treatment is not randomized and spatial spillovers break standard assumptions?
- How should safety inference adapt when crash records are incomplete or missing not at random, and exposure can only be estimated?
- How can generative models synthesize rare, safety-critical vehicle–pedestrian scenarios that are realistic, controllable, and useful for evaluating automated driving systems?

**Current focus**

- Causal decision-making frameworks that turn safety effect estimates into deployable policies and designs (MoE Overseas Postdoctoral Talent Program, 2027–2029).
- Identifying missing-not-at-random mechanisms in crash data with collaborative imputation across data sources (NSFC Young Scientists Fund, 2026–2028).
- Causality-driven active prevention and control of traffic safety on urban expressways via air–ground collaboration (Fundamental Research Funds for the Central Universities, 2026–2027).

**Selected papers** — highlighted as cards on the [homepage](/): citywide speed-limit evaluation (<i>TR-A</i> 2022, <a href="https://doi.org/10.1016/j.tra.2022.01.004">doi</a>), equity-aware safety performance functions (<i>AAP</i> 2024, <a href="https://doi.org/10.1016/j.aap.2024.107759">doi</a>), ride-hailing vs. taxi safety (<i>AAP</i> 2023, <a href="https://doi.org/10.1016/j.aap.2023.107281">doi</a>), and generative safety-critical scenario synthesis (<i>TR-C</i> 2027, <a href="https://doi.org/10.1016/j.trc.2026.106002">doi</a>).

## Theme II: AI-Driven Behavioral Analytics for Sustainable Shared Mobility

<img class="gz-fig" src="/images/theme2-shared-mobility.svg" alt="Behavioral analytics pipeline: GPS trajectories and built-environment data feed discrete choice and machine learning models of ride-hailing, metro, e-scooter, and urban air mobility choices" width="100%">

How do people choose and use shared mobility services, and how do the built environment and pricing shape those choices? Shared mobility generates rich behavioral data — GPS trajectories, transactions, stated choices — but the relationships we care about are nonlinear, spatially heterogeneous, and entangled with policy. I combine discrete choice models with interpretable machine learning (BART, random forests, SHAP) to recover behavioral structure that both predicts well and explains itself, with applications from ride-hailing and micromobility to urban air mobility. The aim is behavioral evidence that is simultaneously predictive and explanatory — ready to inform pricing, service design, and policy.

<div class="gz-methods">
  <span class="gz-tag">discrete choice models</span>
  <span class="gz-tag">Bayesian additive regression trees</span>
  <span class="gz-tag">geographically weighted random forest</span>
  <span class="gz-tag">SHAP &amp; partial dependence</span>
  <span class="gz-tag">latent class analysis</span>
  <span class="gz-tag">spatial heterogeneity</span>
</div>

**Research questions**

- Which trip attributes, built-environment factors, and station features actually drive competition between shared modes and public transit — and where do these effects vary in space?
- How can choice models capture the nonlinearities and heterogeneity that machine learning finds, while remaining interpretable at the moment of decision-making?
- What do travelers value in emerging modes such as urban air mobility, and how heterogeneous are those preferences across population segments?

**Current focus**

- Multimodal AI-driven demand identification and route planning for urban air mobility (Fundamental Research Funds for the Central Universities, Co-PI, 2026–2027).
- Causally-grounded transfer of urban mobility knowledge to data-scarce cities (National Natural Science Foundation of China, Co-PI, 2026–2027).
- Serving as Guest Editor of the <i>Transportation Research Part D</i> special issue on <a href="https://www.sciencedirect.com/special-issue/1027Z51HRF6">AI-Driven Behavioral Analytics for Sustainable Shared Mobility</a>.

**Selected papers** — highlighted as cards on the [homepage](/): shared e-scooter built-environment drivers (<i>TR-D</i> 2025, <a href="https://doi.org/10.1016/j.trd.2025.105020">doi</a>), taxi–metro competition (<i>TR-D</i> 2026, <a href="https://doi.org/10.1016/j.trd.2026.105637">doi</a>), bike-and-ride patterns (<i>TBS</i> 2026, <a href="https://doi.org/10.1016/j.tbs.2025.101201">doi</a>), and urban air mobility preferences (<i>TBS</i> 2026, <a href="https://doi.org/10.1016/j.tbs.2025.101229">doi</a>).

## Research Funding

Full project history, current and past; selected PI grants are also highlighted on the [homepage](/).

| Project | Funder | Role | Period |
|---|---|---|---|
| Causal Decision-Making for Safe Systems | Ministry of Education, Overseas Postdoctoral Talent Program | <span class="gz-role pi">PI</span> | 2027–2029 |
| Causal Inference Approach to Missing-Not-at-Random Mechanism Identification and Collaborative Imputation in Crash Data | NSFC Young Scientists Fund | <span class="gz-role pi">PI</span> | 2026–2028 |
| Causality-Driven Active Prevention and Control of Traffic Safety on Urban Expressways via Air–Ground Collaboration | Fundamental Research Funds for the Central Universities | <span class="gz-role pi">PI</span> | 2026–2027 |
| Multimodal AI-Driven Demand Identification and Route Planning for Urban Air Mobility | Fundamental Research Funds for the Central Universities | <span class="gz-role copi">Co-PI</span> | 2026–2027 |
| Digital Sisters: A Causally-Grounded Framework for Urban Mobility Knowledge Transfer in Data-Scarce Cities | National Natural Science Foundation of China | <span class="gz-role copi">Co-PI</span> | 2026–2027 |
| Home and Firm Location Choice Models and Platform Development | Urban Redevelopment Authority, Singapore | Research Fellow | 2024–2027 |
| Factors Influencing Pedestrian Decisions to Cross Mid-Block and Potential Countermeasures | FHWA & Virginia DOT | Research Assistant | 2022–2024 |
| Improving Safety Service Patrol Performance | FHWA & Virginia DOT | Research Assistant | 2021–2023 |
| Statewide Landslide Risk Assessment on Transportation Infrastructure in Virginia | Old Dominion University Internal Research Grant | Research Assistant | 2022–2024 |
{: class="gz-grants"}
