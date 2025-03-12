# multisite
Library of Estimators of Treatment-effect Heterogeneity across sites in multi-site random experiments with few units per site.
multisite wraps in four commands to estimate treatment-effect heterogeneity across sites in multi-site RCTs, and more generally in stratified RCTs, based on [de Chaisemartin, C, Deeb, A (2024)](https://ssrn.com/abstract=4615304).

## Setup
### Stata
```stata
ssc install multisite, replace
multisite
```

## Description 
**multisite_varITT** computes the estimated variance of ITTs across sites in multi-site randomized trials.

**multisite_varLATE** computes the estimated variance of LATEs across sites in multi-site randomized trials.

**multisite_regITT** computes the coefficients from a regression of site-level ITTs on site-level characteristics in multi-site randomized trials.

**multisite_regLATE** estimates the sign of univariate regression coefficients from regressions of site-level LATEs on site-level characteristics in multi-site randomized trials.

## Syntax
**multisite_varITToutcome instrument site** [if] [aweight]

**multisite_varLATE outcome treatment instrument site** [if] [aweight]

**multisite_regITT outcome instrument site** [if] [aweight] [, **controls**(varlist numeric) **mediators**(varlist numeric) **y0** **fs**(treatment numeric)]

**multisite_regLATE outcome treatment instrument site** [if] [aweight] [, **controls**(varlist numeric) **mediators**(varlist numeric) **y0** **fs**]

## Options   

For **multisite_regITT**: 

**controls(***varlist***)**: gives the list of site-level characteristics that are observed and do not need to be estimated to be included in the regression.

**mediators(****varlist***)**: gives the list of mediators to be included in the regression. Mediators are variables that could be affected by the treatment, and that effect could in turn explain the treatment's effect on the main outcome variable. Therefore, mediators are other outcome variables, whose site-level ITTs need to be estimaded.

**y0**: indicates that the site's average outcome without a treatment offer should be included in the regression. This can be used to assess if ITT effects are lower or larger in sites with a high y0, to assess if treatment offers reduce or increase inequalities across sites.

**fs(***treatment***)**: indicates that the site's first-stage effect should be included in the regression. treatment is an indicator variable for whether a unit is treated.

For **multisite_regLATE**:

**controls(***varlist***)**: gives the list of site-level characteristics that are observed and do not need to be estimated whose coefficients' sign has to be estimated.

**mediators(****varlist***)**: gives the list of mediators whose coefficients' sign has to be estimated. Mediators are variables that could be affected by the treatment, and that effect could in turn explain the treatment's effect on the main outcome variable. Therefore, mediators are other outcome variables, whose site-level ITTs need to be estimaded.

**y0**: indicates that the sign of the coefficient on sites' average outcome without a treatment offer should be estimated. This can be used to assess if LATEs are lower or larger in sites with a high y0.

**fs**: indicates that the sign of the coefficient on sites' first-stage effect should be estimated. This can be used to assess if sites with the largest treatment take up rate also have the largest LATEs, which would be consistent with a Roy model.

## References

de Chaisemartin, C, Deeb, A (2024).  [Estimating treatment-effect heterogeneity across sites, in multi-site randomized experiments with few units per site.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4615304).

## Authors

Clément de Chaisemartin, Economics Department, Sciences Po, France. 
Antoine Deeb, Development Impact Evaluation,  World Bank.

**<ins>Contact:</ins>**  
[chaisemartin.packages@gmail.com](mailto:chaisemartin.packages@gmail.com)

