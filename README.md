# multisite
Library of Estimators of Treatment-effect Heterogeneity across sites in multi-site random experiments with few units per site.
multisite wraps in four commands to estimate treatment-effect heterogeneity across sites in multi-site RCTs, and more generally in stratified RCTs.

## Setup
### Stata
```stata
ssc install did_multiplegt, replace
```

## Description & Syntax
**multisite_varITT** computes the estimated variance of ITTs across sites in multi-site randomized trials.
### Stata
**multisite_varITToutcome instrument site** [if] [aweight]

**multisite_varLATE** computes the estimated variance of LATEs across sites in multi-site randomized trials.
### Stata
**multisite_varLATE outcome treatment instrument site** [if] [aweight]

**multisite_regITT** computes the coefficients from a regression of site-level ITTs on site-level characteristics in multi-site randomized trials.
### Stata
**multisite_regITT outcome instrument site** [if] [aweight] [, **controls**(varlist numeric) **mediators**(varlist numeric) **y0** **fs**(treatment numeric)]

**multisite_regLATE** estimates the sign of univariate regression coefficients from regressions of site-level LATEs on site-level characteristics in multi-site randomized trials.
### Stata
**multisite_regLATE outcome treatment instrument site** [if] [aweight] [, **controls**(varlist numeric) **mediators**(varlist numeric) **y0** **fs**]

