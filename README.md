# Synthetic Control Example  
This project demonstrates how I would approach using **synthetic control methods** to evaluate the impact of promotions, feature launches, or policy changes in the sports betting industry.  

Sports betting in the U.S. is largely regulated at the **state level**. As more states legalize sports betting and adopt varying regulations, companies need **robust ways to assess how these changes affect user engagement, revenue, and market dynamics**.  seIn addition to regulatory variation, **sports fandom is heavily shaped by state-level factors**, including home team effects and regional preferences, leading to the need for state-level strategies to promotions and feature launch. 

## The Challenge: Causal Inference at the State Level  
Causal inference at the state level is critical for sports betting companies to make informed decisions about:  
- Where and how to allocate marketing resources. How to design state-specific promotions
- How the market will respond to market entrances
- How to anticipate the effects of regulatory changes  

However, identifying the true **causal impact** of a policy or feature in a specific state is challenging because:  

- **No clear counterfactuals** — we cannot observe what would have happened if the policy or feature had not been introduced.
- **States differ in many ways**, including demographics, sports fandom intensity, and regulatory environments, making choosing a "control" state impossible and making simple comparisons misleading.  
- **Time trends vary across states**, so naive before-and-after comparisons risk conflating underlying trends with actual intervention effects.
- - **Limited and low number of states** for statistical inferences. 

## The Synthetic Control Solution  
**Synthetic control** offers a principled way to construct a **counterfactual** for a treated state by creating a weighted combination of other states that did **not** experience the policy or feature launch. These weights are chosen so that, **prior to the intervention**, the synthetic version of the treated state closely mirrors its outcomes and relevant predictors (e.g., sports betting activity, demographics, team presence).  

By comparing the **actual post-intervention outcomes** in the treated state to the **synthetic control**, we can estimate the **causal effect** of the policy or feature.  

**Synthetic control is especially useful when**:  
- Randomized experiments are not feasible  
- The number of units (states) is limited  
- Treatment is implemented at the aggregate (state) level
  
Making synthetic control the appropriate solution to these cases in the sports betting industry. 

## Leveraging Political Science for Synthetic Control  
In general, my Political Science training grounds my approach to synthetic control. **Political science literature, datasets, and methodological innovations** has led the development and application of synthetic control methods in U.S. state-level policy evaluation.  Political scientists have used synthetic control to study the impact of diverse state-level policies, including:  
- Economic policies (e.g., minimum wage increases)  
- Public health interventions (e.g., tobacco control laws)  
- Criminal justice reforms (e.g., sentencing policy changes)  
- Voting laws (e.g., voter ID legislation)  

These studies often grapple with the same issues of **state heterogeneity, limited units, and staggered policy adoption** that also characterize the sports betting industry.  By grounding my synthetic control approach in this well-established body of political science research, I bring a **rigorous, tested methodology** to sports betting analytics. 

### State-Level Panel Datasets Available
To build credible and rich pre-treatment models, we can use **state-level panel datasets**, some frequently used in political science research. I provide some resources here:  

| Dataset Name | Description | Example Use |
|--------------|-------------|---------------------------------------------|
| [**U.S. Census Bureau**](https://www.census.gov/data/datasets.html) | State-level population, demographics, median income, education levels | Control for demographic and economic factors |
| [**Bureau of Labor Statistics (BLS)**](https://www.bls.gov/data/) | Employment rates, industry breakdowns, consumer spending data | Adjust for economic conditions |
| [**BEA Regional Economic Accounts**](https://www.bea.gov/data/economic-accounts/regional) | Geographic distribution of US economic activity and growth| Adjust for economic contexts |
| [**Correlates of State Policy Project (CSPP)**](https://ippsr.msu.edu/public-policy/correlates-state-policy) | Policy outputs and political, social, or economic factors that may influence policy differences |  Account for inter-state policy diffusion patterns and social contexts |
| [**State Policy Innovation and Diffusion (SPID) Database**](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/CVYSR7) | Records of state policy adoptions across domains | Account for inter-state policy diffusion patterns |
| [**National Conference of State Legislatures (NCSL)**](https://www.ncsl.org/technology-and-communication/ncsl-50-state-searchable-bill-tracking-databases)| Database of enacted and proposed state legislation | Identify and time revelant laws and regulatory changes |
| **State-Specific Sports Team Data** | Presence of professional and college teams, fan base size, team historical stats, etc. | Sport and team specific influences to fandom |
