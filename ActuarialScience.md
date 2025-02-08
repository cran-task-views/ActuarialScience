---
name: ActuarialScience
topic: Actuarial Science
maintainer: Christophe Dutang, Vincent Goulet
email: dutangc@gmail.com
version: 2025-02-08
source: https://github.com/cran-task-views/ActuarialScience/
---

Actuaries are experts in evaluating the likelihood and financial consequences of future events. A pivotal part of their work is the modeling of the size and frequency of insurance claims. With probability models for the claims process in hand, actuaries can compute insurance premiums, determine the amount a company has to set aside in its actuarial reserve to cope with future events, evaluate the risk the company will not be able to meet its obligations, elaborate optimal investment strategies for its assets, or run simulations to compare business strategies or solve otherwise untractable problems.

Base R contains a wide array of functions for probabilistic and statistical models used in actuarial mathematics. Nevertheless, a number of packages have been developed to extend or ease actuarial computations. Due to the intrinsically interdisciplinary nature of actuarial science, this view intersects with other views `r view("Distributions")`, `r view("Econometrics")`, `r view("ExtremeValue")`, and `r view("Finance")`.

The maintainers gratefully acknowledge the comments and suggestions from Patrice Kiener and Quentin Guibert.
If you think that some package is missing from the list, please let us know, either via e-mail to the maintainer or by submitting an issue or pull request in the GitHub repository linked above.

### Table of contents

- [Life insurance](#life-insurance) 
  - [Life contingencies](#life-contingencies)
  - [Mortality laws and prospective mortality models](#mortality-laws-and-prospective-mortality-models)
  - [Survival analysis and portfolio experience](#survival-analysis-and-portfolio-experience)
  - [Life and pension reserving](#life-reserving)
- [Non-life insurance](#non-life-insurance) 
  - [Loss modeling](#loss-modeling)
  - [Insurance pricing](#a-priori-insurance-pricing)
  - [Experience pricing](#a-posteriori-experience-pricing)
  - [Claims reserving](#claims-reserving)
  - [Ruin theory](#ruin-theory)
  - [Claims generation](#claims-generation)
- [Reinsurance and extreme events](#reinsurance-and-extreme-events)
- [Risk measures](#risk-measures)
- [Miscellaneous](#Miscellaneous)
  - [Data handling](#data-handling)
  - [Mortality databases](#mortality-databases)
  - [Actuarial datasets](#actuarial-datasets)
  - [Documentation, online courses](#documentation-online-courses)
- [Bibliography](#bibliography)
  - [Actuarial science using R](#actuarial-science-using-r-references)
  - [Life insurance references](#life-insurance-references)
  - [Non-life insurance references](#non-life-insurance-references)


### Life insurance

#### Life contingencies

- `r pkg("lifecontingencies", priority = "core")` provides the most popular functionalities for life actuarial mathematics, namely, survival/death probabilities, the present value of life annuities and (whole)-life insurance one, two or multiple heads. The package also propose S4 classes for handling lifetables, multiple decrement tables and actuarial tables.
- `r pkg("AnnuityRIR")` proposes different techniques for the approximation of the present and final value of a unitary annuity-due or annuity-immediate considering interest rate as a random variable.
- `r pkg("LifeInsuranceContracts")` provides R6 classes to model traditional life insurance contracts like annuities, whole life insurances or endowments with (discretionary) profit participation. This package provides a framework to model such contracts in a very generic (cash-flow-based) way and includes modelling profit participation schemes, dynamic increases or more general contract layers, as well as contract changes.
- `r pkg("MortCast")` provides a function `life.table` to compute survival/death probabilities.
- `r pkg("lifepack")` calculates insurance reserves, premiums using advanced numerical methods in order to facilitate accurate financial projections.

#### Mortality laws and prospective mortality models

- `r pkg("demography")` provides functions for demographic analysis including lifetable calculations; Lee-Carter modelling; functional data analysis of mortality rates, fertility rates, net migration numbers; stochastic population forecasting.
- `r pkg("HMDHFDplus")` allows to read Human Mortality Database and Human Fertility Database Data from the Web in conjunction with `r pkg("demography")`.
- `r pkg("StMoMo")` implements of the family of generalised age-period-cohort stochastic mortality models. This family of models encompasses many models proposed in the actuarial and demographic literature including the Lee-Carter (1992) `r doi("10.2307/2290201")` and Cairns-Blake-Dowd (2006) `r doi("10.1111/j.1539-6975.2006.00195.x")` models. It includes functions for fitting mortality models, analysing their goodness-of-fit and performing mortality projections and simulations.
- `r pkg("apc")` provides functions for age-period-cohort analysis. It can deal with: aggregate data indexed by age-cohort, age-period or cohort-period, for which a GLM allow a fit for 3, 2, 1 or 0 of the age-period-cohort factors; individual-level data for each of age, period, and cohort for which a GLM allow to fit repeated cross-section model.
- `r pkg("MortalityTables")` provides classes to implement and plot cohort life tables for actuarial calculations. In particular, birth-year dependent mortality tables using a yearly trend to extrapolate from a base year are implemented, as well as period life table, cohort life tables using an age shift, and merged life tables.
- `r pkg("StanMoMo")` implements of popular mortality models using the 'rstan' package, which provides the R interface to the Stan C++ library for Bayesian estimation.
- `r pkg("MortCast")` provides estimation and projection methods for Kannisto and Lee-Carter mortality models, as well as methods blending.
- `r pkg("MortalityLaws")` provides 27 parametric mortality distributions and construct full or abridged life tables given various input indices.
- `r pkg("MortalityGaps")` provides methods for forecasting male/female life expectancy based on analysis of the gap between male/female life expectancy in a country compared with the record level of female life expectancy in the world.
- `r pkg("GPRMortality")` estimate Bayesian statistical models for estimating child and adult mortality rates which its data likelihood is mortality rates from different data sources such as: death registration system, Censuses or surveys.
- `r pkg("IBMPopSim")` allows the efficient simulation of a wide class of individual based models where individuals are marked by their date of birth and a set of (discrete or continuous) characteristics.
- `r pkg("WH")` provides an enhanced implementation of Whittaker-Henderson smoothing for the gradation of one-dimensional and two-dimensional life insurance tables, based on Biessy (2023) `r doi("10.48550/arXiv.2306.06932")`. Among other features, it generalizes the original smoothing algorithm to maximum likelihood estimation, automatically selects the smoothing parameter(s) and extrapolates beyond the range of data.

See also the view `r view("Epidemiology")` for epidemiology topics and the view `r view("Bayesian")` for Bayesian inference.

#### Survival analysis and portfolio experience

For a general overview of survival analysis, see the view `r view("Survival")`.

- `r pkg("ELT")` provides functions to build experience life tables for three methods: the standardized mortality ratio, a semi-parametric relational model, a GLM Poisson with interactions between age and calendar years.
- `r github("mpascariu/lemur")` allows the user to selected mortality changes over the entire lifespan or at specific ages, as well as for overall mortality or for specific causes of death.

#### Life and pension reserving

- `r pkg("lifecontingencies", priority = "core")` for many life and pension computations.
- `r github("primact/SimBEL")` allows to carry out Monte-Carlo simulation of asset-liability cashflows for unit-linked insurance and retirement plans in France.
- `r github("ungolof/AffineMortality")` performs parameter estimation, goodness-of-fit analysis, simulation, and projection of future mortality rates for a set of affine mortality models for use in pricing and reserving, see Ungolo et al. (2024) `r doi("10.1017/S1748499524000149")`. 

### Non-life insurance

#### Loss modeling

The view `r view("Distributions")` provides a detailed list of probability distributions available in base R and CRAN packages.
Here we focus only on packages that implement distributions particularly designed for actuarial science.

- Pioneer package `r pkg("actuar", priority = "core")` provides functions and data sets for actuarial science: modeling of loss distributions; simulation of compound models, discrete mixtures and compound hierarchical models. It support for many additional probability distributions to model insurance loss size and frequency: 23 continuous heavy tailed distributions (e.g. the Feller-Pareto family of distributions); the Poisson-inverse Gaussian discrete distribution; zero-truncated and zero-modified extensions of the standard discrete distributions as well as phase-type distributions.
- `r pkg("fitdistrplus")` provides a user-friendly function to fit discrete/continuous probability distributions based on maximum likelihood estimation, quantile matching estimation, moment matching estimation, etc. Starting values for numerical algorithms for loss distributions of `r pkg("actuar", priority = "core")` are provided.
- `r pkg("mbbefd", priority = "core")` provides distributions that are typically used for exposure rating in general insurance, in particular to price reinsurance contracts.
- `r pkg("MBBEFDLite", priority = "core")` provides probability mass, distribution, quantile, random variate generation, and method-of-moments parameter fitting for the MBBEFD family of distributions used in insurance modeling as described in Bernegger (1997) without any external dependencies.
- `r pkg("NetSimR")` provides capped mean, exposure curves and increased limit factor curves (ILFs) for lognormal, gamma, Pareto, sliced lognormal-Pareto and sliced gamma-Pareto distributions. 
- `r pkg("Delaporte")` provides probability mass, distribution, quantile, random-variate generation, and method-of-moments parameter-estimation functions for the Delaporte discrete distribution.

#### A priori insurance pricing

A priori insurance pricing consists in fitting two models: one for claim frequency and one for claim severity. Classical pricing models rely on generalized linear models (GLM) that can be fitted in base R using `glm`.

- `r pkg("tweedie")` allows an alternative approach to model the aggregate claim amount directly using a Tweedie model.
- `r pkg("insurancerating")` helps actuaries to implement GLMs with all relevant steps needed to construct a risk premium from raw data. It provides a data driven strategy for the construction of insurance tariff classes.

More advanced statistical models can be found in the views `r view("Econometrics")` and `r view("MachineLearning")`. See also the view `r view("Spatial")` for analysis of spatial data.

#### A posteriori experience pricing

- `r pkg("actuar", priority = "core")` provides functions for credibility theory: `cm` is the unified front end for credibility models fitting and supports hierarchical models with any number of levels (with Bühlmann and Bühlmann-Straub models as special cases) and the regression model of Hachemeister. `cm` can also fit linear Bayes models, in which case usage is much simplified.
- `r pkg("actuaRE")` allows to fit a random effects model using either the hierarchical credibility model, a combination of the hierarchical credibility model with a generalized linear model or a Tweedie generalized linear mixed model.

#### Claims reserving

- `r pkg("ChainLadder", priority = "core")` provides various statistical methods and models which are typically used for the estimation of outstanding claims reserves in non-life insurance, including those to estimate the claims development result as required under Solvency II.
- `r pkg("clmplus")` implements the chain ladder model under the reverse time framework introduced in Hiabu (2017) `r doi("10.1080/03461238.2016.1240709")` and extensions that add flexibility to the individual development factors modeling by allowing practitioners to set their own hazard rate model.
- `r pkg("NetSimR")` provides functions that help model excess levels, capping and pure incurred but not reported claims (pure IBNR) and includes calculating pure IBNR exposure with lognormal and gamma distribution for reporting delay.

#### Ruin theory

- `r pkg("actuar", priority = "core")` provides infinite time ruin probability of Cramér-Lundberg and Sparre Andersen models, using phase-type distributions including mixtures of exponentials, Erlang and mixture of Erlang for both claim amount distribution and claim interarrival times.
- `r pkg("ruin")` implements a collection of common models of risk processes in actuarial science, represented as formal S4 classes. Each class (risk model) has a simulator of its path, and a plotting function. Further, a Monte-Carlo estimator of a ruin probability for a finite time is implemented, using a parallel computation. Currently, the package extends two classical risk models Cramer-Lundberg and Sparre Andersen models by including capital injections, that are positive jumps.

#### Claims generation

- `r pkg("SynthETIC")` creates an individual claims simulator which generates various features of non-life insurance claims. An initial set of test parameters, designed to mirror the experience of an Auto Liability portfolio, were set up and applied by default to generate a realistic test data set of individual claims (see vignette). The simulated data set then allows practitioners to back-test the validity of various reserving models and to prove and/or disprove certain actuarial assumptions made in claims modelling. The distributional assumptions used to generate this data set can be easily modified by users to match their experiences.
- `r pkg("SPLICE")` is an extension of `r pkg("SynthETIC")` , to simulate the evolution of case estimates of incurred losses through the lifetime of an insurance claim. The transactional simulation output now comprises key dates, and both claim payments and revisions of estimated incurred losses. An initial set of test parameters, designed to mirror the experience of a real insurance portfolio, were set up and applied by default to generate a realistic test data set of incurred histories.


### Reinsurance and extreme events

- `r pkg("ReIns", priority = "core")` follows the book "Reinsurance: Actuarial and Statistical Aspects" and provides basic extreme value theory (EVT) estimators and graphical methods, EVT estimators and graphical methods adapted for censored and/or truncated data, Splicing of mixed Erlang distributions with EVT distributions, value-at-risk (VaR), conditional tail expectation (CTE) and excess-loss premium estimates.
- `r pkg("ExtremeRisks")` provides a set of procedures for estimating risks related to extreme events via risk measures such as expectile, value-at-risk, etc.

For a comprehensive review of extreme value analysis, see the view `r view("ExtremeValue")`.


### Risk measures

- `r pkg("actuar", priority = "core")` provides functions to compute value-at-risk and conditional tail expectation.
- `r pkg("ActuarialM")` computes actuarial measures such as expected shortfall and value-at-risk using the Bell G family.
- `r pkg("atRisk")` provides actuarial measures such as expected shortfall and value-at-risk using a non-parametric approach or a parametric fit (via Gaussian or skew-t distributions).


### Miscellaneous

#### Data handling

- `r pkg("actuaryr")` contains functions to easily refer to the first or last (working) day within a specific period relative to a base date to facilitate actuarial reporting and to compare results.
- `r pkg("eiopaR")` provides EIOPA (European Insurance And Occupational Pensions Authority) risk-free rates.
- `r pkg("actxps")` helps to prepare data, summarize results, and create reports via a dedicated S3 class *Actuarial Experience Studies*.


#### Mortality databases

Mortality databases are generally provided by demography and/or statistical institutes by each country (see below). However, the Human Mortality Database project at [HMD](https://mortality.org) provides a collection of reliable mortality datasets after a careful and very detailed protocol. [HMD](https://mortality.org) is a keystone for actuaries to compute reliable mortality/longevity estimates.

- Australian database is available at [AHMD](https://aushd.org/)
- Canadian database is available at [CHMD](http://www.bdlc.umontreal.ca/CHMD/)
- French regional database is available at [FRD](https://frdata.org/). Mortality tables at regional are available at [FRD](https://frdata.org/fr/). The mortality by cause is provided by [INED](https://www.ined.fr/en/everything_about_population/data/france/deaths-causes-mortality/mortality-tables/)
- Japan database is available at [JMD](https://www.ipss.go.jp/p-toukei/JMD/index-en.asp)
- United States database is available at [USMD](https://usa.mortality.org/) from HMD. the death by cause is provided by [CDC](https://www.cdc.gov/) through [Wonder interface](https://wonder.cdc.gov/) at county level, which can used in conjunction with [Census Bureau](https://data.census.gov/) datasets.

#### Actuarial datasets

- `r github("dutangc/CASdatasets")` provides a large variety of actuarial datasets, originally for the book *Computational Actuarial Science with R*. Note that the package is not hosted on CRAN but on github, at [CNRS](http://dutangc.perso.math.cnrs.fr/RRepository/) and [UQAM](http://cas.uqam.ca/).
- `r pkg("raw")` organizes several sets of publicly available data of interest to non-life actuaries.
- `r pkg("insuranceData")` provides insurance datasets, which are often used in claims severity and claims frequency modelling. It helps testing new regression models in those problems, such as GLM, GLMM, HGLM, nonlinear mixed models.
- `r pkg("actuar")` provides functions to facilitate the generation of random variates from various probability models commonly used in actuarial applications, such as discrete mixtures and compound models where both the frequency and the severity components can have a hierarchical structure.
- An individual claims generator for claims reserving studies is provided by Wang & Wuethrich at `r github("JSchelldorfer/IndividualClaimsSimulator")`.
- An individual claims history simulation machine for annual cashflows is provided by Gabrielli & Wuethrich at [IndividualClaimsHistory](https://people.math.ethz.ch/~wueth/simulation.html); see also `r github("kasaai/simulationmachine")`.
- [Cellar](https://cellar.kasa.ai/) is a collection of community-curated open datasets for insurance analytics.
- `r pkg("DDPM")` provides some insurance-related datasets, some already in `r github("dutangc/CASdatasets")`.

#### Documentation and online courses

- A collection of computer labs in R is provided by [Antonio & Crevecoeur](https://katrienantonio.github.io/Risk-modelling-in-insurance/).
- A series of [textbooks in French](https://gitlab.com/vigou3) is proposed by Vincent Goulet, notably on [credibility theory](https://gitlab.com/vigou3/theorie-credibilite-avec-r), [loss modeling](https://vigou3.gitlab.io/modelisation-distributions-sinistres-avec-r/), and [numerical methods](https://gitlab.com/vigou3/methodes-numeriques-en-actuariat-avec-r).
- `r pkg("FinancialMath")` contains financial math functions and introductory derivative functions included in the Society of Actuaries and Casualty Actuarial Society *Financial Mathematics* exam, and some topics in the *Models for Financial Economics* exam.

See the view `r view("TeachingStatistics")` for usual documentation on teaching statistics.


## Bibliography

### Actuarial science using R references

- Charpentier, A., ed. (2014). Computational Actuarial Science with R, Chapman & Hall/CRC. `r doi("10.1201/b17230")`
- Kaas, R., Goovaerts, M., Dhaene, J. & Denuit, M. (2008). Modern Actuarial Risk Theory Using R, 2nd ed., Springer-Verlag. `r doi("10.1007/978-3-540-70998-5")`
- Bowers, N. L., Gerber, H. U., Hickman, J. C., Jones, D. A. & Nesbitt, C. J. (1997). Actuarial Mathematics, The Society of Actuaries.
- Teugels, J. & Sundt, B. (2004). Encyclopedia of Actuarial Science, Vol. 1, John Wiley & Sons. `r doi("10.1002/9780470012505")`

### Life insurance references

- Dickson, D., Hardy, M. & Waters, H. (2013). Actuarial Mathematics for Life Contingent Risks, 2nd ed., Cambridge University Press. `r doi("10.1017/9781108784184")`
- Macdonald, A., Richard, S. & Currie, I. (2018). Modelling Mortality with Actuarial Applications, Cambridge University Press. `r doi("10.1017/9781107051386")` 

### Non-life insurance references

- Frees, E. (2009). Regression Modeling with Actuarial and Financial Applications, International Series on Actuarial Science, Cambridge University Press. `r doi("10.1017/CBO9780511814372")`
- Jong, P. D. & Heller, G. (2008). Generalized Linear Models for Insurance Data, Cambridge University Press. `r doi("10.1017/CBO9780511755408")`
- Klugman, S., Panjer, H. & Willmot, G. (2019). Loss Models: From Data to Decisions, 5th ed., John Wiley & Sons.
- Charpentier, A. & Denuit, M. (2023). Non-life insurance mathematics [nonlife maths with R examples](https://nonlifemaths.github.io/)
