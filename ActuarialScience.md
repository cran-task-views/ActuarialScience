---
name: ActuarialScience
topic: Actuarial science
maintainer: Christophe Dutang, Vincent Goulet
email: dutangc@gmail.com
version: 2023-05-11
source: https://github.com/cran-task-views/ActuarialScience/
---

Classical references on actuarial mathematics are (in chronological order):

- both life and non-life insurance: 
  - Bowers, N. L., Gerber, H. U., Hickman, J. C., Jones, D. A. & Nesbitt, C. J. (1997), Actuarial
Mathematics, The Society of Actuaries.
  - Teugels, J. & Sundt, B. (2004), Encyclopedia of Actuarial Science, Vol. 1, John Wiley & Sons
  <doi:10.1002/9780470012505>.

- non-life insurance: 
  - Taylor, G. (2000), Loss Reserving : An Actuarial Perspective, Kluwer Academic Publishers, Boston <doi:10.1007/978-1-4615-4583-5>.
  - Charpentier, A. & Denuit, M. (2004), Mathématiques de l’assurance non vie, Vol. 1 & 2, Economica.
  - Buehlmann, H. & Gisler, A. (2005), A Course in Credibility Theory and its Applications, Springer <doi:10.1007/3-540-29273-X>.
  - Wuethrich, M. & Merz, M. (2008), Stochastic Claims Reserving Methods in Insurance, Wiley Finance <doi:10.1002/9781119206262>.
  - Jong, P. D. & Heller, G. (2008), Generalized Linear Models for Insurance Data, Cambridge
University Press <doi:10.1017/CBO9780511755408>. 
  - Frees, E. (2009), Regression Modeling with Actuarial and Financial Applications, International Series on Actuarial Science, Cambridge University Press <doi:10.1017/CBO9780511814372>.
  - Klugman, S., Panjer, H. & Willmot, G. (2019), Loss Models : From Data to Decisions, 5th edn, Wiley.

- life insurance: 
  - Hardy, M. (2003), Investment Guarantees : Modeling and Risk Management for Equity-Linked Life Insurance, Wiley.
  - Moller, T. & Steffensen, M. (2007), Market-Valuation Methods in Life and Pension Insurance, Cambridge University Press <doi:10.1017/CBO9780511543289>.
  - Dickson, D., Hardy, M. & Waters, H. (2013), Actuarial Mathematics for Life Contingent Risks, 2nd edn, Cambridge University Press <doi:10.1017/9781108784184>.
  - Macdonald, A., Richard, S. & Currie, I. (2018), Modelling Mortality with Actuarial Applications, Cambridge University Press <doi:10.1017/9781107051386>.

Books on actuarial mathematics in R are: 

- Kaas, R., Goovaerts, M., Dhaene, J. & Denuit, M. (2008), Modern Actuarial Risk Theory Using
R, 2nd edn, Springer <doi:10.1007/978-3-540-70998-5>.
- Charpentier, A., ed. (2014), Computational Actuarial Science with R, Chapman and Hall-CRC.


The maintainers gratefully acknowledge Patrice Kiener, Quentin Guibert for their numerous comments and suggestions.


### Table of contents
- [Life Insurance](#Life) 
  - [Life contingencies](#LifeCont)
  - [Mortality laws and prospective mortality models](#Mortality)
  - [Survival analysis and portfolio experience](#PtfExperience)
  - [Life and pension reserving](#LReserving)
- [Non Life Insurance](#NonLife) 
  - [Loss modeling](#Loss)
  - [Insurance pricing](#AprioriPricing)
  - [Experience pricing](#AposteriorPricing)
  - [Claim reserving](#NLReserving)
  - [Risk and ruin theory](#RiskRuin)
  - [Claim generators](#ClaimGen)
- [Reinsurance and extreme events](#Reinsurance)
- [Misc](#Misc)
  - [Data handling](#Datahandling)
  - [Actuarial datasets](#Datasets)

# [Life Insurance:]{#Life}

## [Life contingencies:]{#LifeCont}

- `r pkg("lifecontingencies", priority = "core")` provides the most wanted functionalities
for life actuarial mathematics, namely, survival/death probabilities, 
the present value of life annuities and (whole)-life insurance one, two or multiple heads.
The package also propose S4 classes for handling lifetables,  multiple decrement tables
and actuarial table.
- `r pkg("AnnuityRIR")` proposes different techniques for the approximation of the present 
and final value of a unitary annuity-due or annuity-immediate considering interest rate 
as a random variable.
- `r pkg("LifeInsuranceContracts")` provides R6 classes to model traditional life insurance
contracts like annuities, whole life insurances or endowments with (discretionary) 
profit participation. This package provides a framework to model such contracts
in a very generic (cash-flow-based) way and includes modelling profit participation 
schemes, dynamic increases or more general contract layers, as well as contract changes.
- `r pkg("MortCast")` provides a function `life.table` to compute survival/death probabilities. 

## [Mortality laws and prospective mortality models:]{#Mortality}

- `r pkg("demography")` provides functions for demographic analysis including lifetable calculations;
Lee-Carter modelling; functional data analysis of mortality rates, fertility rates, net migration
numbers; and stochastic population forecasting.
- `r pkg("HMDHFDplus")` allows to read Human Mortality Database and Human Fertility Database 
Data from the Web in conjunction with `r pkg("demography")`.
- `r pkg("MortalitySmooth")` allowed mortality smoothing but is currently archived.
- `r pkg("StMoMo")` implements of the family of generalised age-period-cohort stochastic mortality
models. This family of models encompasses many models proposed in the actuarial and demographic
literature including the Lee-Carter (1992) <doi:10.2307/2290201> and the Cairns-Blake-Dowd (2006)
<doi:10.1111/j.1539-6975.2006.00195.x> models. It includes functions for fitting mortality models,
analysing their goodness-of-fit and performing mortality projections and simulations.
- `r pkg("apc")` provides functions for age-period-cohort analysis. 
It can deal with (i) Aggregate data indexed by age-cohort, age-period or cohort-period, for
which a GLM allow a fit for 3,2,1 or 0 of the age-period-cohort factors; (ii) 
Individual-level data for each of age, period, and cohort for which a GLM allow 
to fit repeated cross-section model. 
- `r pkg("MortalityTables")` provides classes to implement and plot cohort life tables for 
actuarial calculations. In particular, birth-year dependent mortality tables using a yearly 
trend to extrapolate from a base year are implemented, as well as period life table, 
cohort life tables using an age shift, and merged life tables.
- `r pkg("StanMoMo")` implements of popular mortality models using the 'rstan' package, 
which provides the R interface to the 'Stan' C++ library for Bayesian estimation. 
- `r pkg("MortCast")` provides estimation and projection methods for Kannisto and Lee-Carter 
mortality models as well as methods blending. 
- `r pkg("MortalityLaws")` provides 27 parametric mortality distributions and construct full
or abridged life tables given various input indices. 
- `r pkg("MortalityEstimate")` contains methods for estimating age-specific 
death rates and life tables based on demographic indicators other than 
death counts and population exposure to risk using linear or log-quadratic models. 
- `r pkg("MortalityGaps")` provides methods for forecasting male/female life expectancy 
based on analysis of the gap between male/female life expectancy in a country compared 
with the record level of female life expectancy in the world. 
- `r pkg("GPRMortality")` estimate Bayesian statistical models for estimating child and adult 
mortality rates which its data likelihood is mortality rates from different data sources 
such as: Death Registration System, Censuses or surveys.
- `r pkg("IBMPopSim")` allows the efficient simulation of a wide class Individual Based Models 
where individuals are marked by their date of birth and a set of (discrete or continuous) characteristics. 



## [Survival analysis and portfolio experience:]{#PtfExperience}

- for a general overview of survival analysis, we refer to the [Survival Analysis view](https://cran.r-project.org/view=Survival)
- `r pkg("ELT")` provides functions to build experience life tables for three methods:
the standardized mortality ratio, a semi-parametric relational model, a GLM Poisson with
interactions between age and calendar years.
- `r pkg("lemur")` allows the user to selected mortality changes over the entire 
lifespan or at specific ages, as well as for overall mortality or for specific causes of death.


## [Life and pension reserving:]{#LReserving}

- computations can be carried out using `r pkg("lifecontingencies", priority = "core")`. 

# [Non-Life Insurance:]{#NonLife}

## [Loss modeling]{#Loss}

- for a detailed list of probability distributions, we refer to the [Distributions view](https://cran.r-project.org/view=Distributions)

- pioneer `r pkg("actuar", priority = "core")` package provides functions and data sets for
actuarial science: modeling of loss distributions; simulation of compound models, discrete 
mixtures and compound hierarchical models. It support for many additional probability distributions
to model insurance loss size and frequency: 23 continuous heavy tailed distributions 
(e.g. the Feller-Pareto family of distributions); 
the Poisson-inverse Gaussian discrete distribution; zero-truncated and zero-modified 
extensions of the standard discrete distributions as well as phase-type distributions.
- `r pkg("fitdistrplus")` provides a user-friendly function to fit discrete/continuous 
probability distributions based on maximum likelihood estimation, quantile matching estimation,
moment matching estimation,... Starting values for numerical algorithms 
for loss distributions of `r pkg("actuar", priority = "core")` are provided in this package.
- `r pkg("mbbefd", priority = "core")` provides distributions that are typically used 
for exposure rating in general insurance, in particular to price reinsurance contracts. 
- `r pkg("OpVaR")` provides functions for computing the value-at-risk in compound Poisson models.
The implementation comprises functions for modeling loss frequencies and loss severities with 
plain, mixed or spliced distributions using Maximum Likelihood estimation and Bayesian approaches.
- `r pkg("NetSimR")` provides capped mean, exposure curves and increased limit factor curves 
(ILFs) for LogNormal, Gamma, Pareto, Sliced LogNormal-Pareto and Sliced Gamma-Pareto distributions. 

## [A priori Insurance pricing]{#AprioriPricing}

- (a priori) insurance pricing consists in fitting two models: one for claim frequency and
one for claim severity. Classical models use GLM which are available in base R function `glm`.
An alternative approch is to model directly the aggregate claim amount typically with a 
Tweedie model, see `r pkg("tweedie")`.
- more advanced statistical models can be found in the 
[Econometrics view](https://cran.r-project.org/view=Econometrics), 
[Machine learning view](https://cran.r-project.org/view=MachineLearning).
- `r pkg("insurancerating")` helps actuaries to implement GLMs within all relevant steps 
needed to construct a risk premium from raw data. It provides a data driven strategy 
for the construction of insurance tariff classes.



## [A posteriori Experience pricing]{#AposteriorPricing}

- `r pkg("actuar", priority = "core")` provides functions for credibility theory: the `cm()`
is the unified front end for credibility models fitting and supports hierarchical models 
with any number of levels (with Buehlmann and Buehlmann-Straub models as special cases)
and the regression model of Hachemeister. 
`cm` can also fit linear Bayes models, in which case usage is much simplified. 
- `r pkg("actuaRE")` allows to fit a random effects model using either the hierarchical 
credibility model, a combination of the hierarchical credibility model with a generalized 
linear model or a Tweedie generalized linear mixed model. 
- `r pkg("nlirms")` provided a rate-making system based on a bonus-malus system introduced by Lemaire (1995) but is archived.

## [Claim reserving]{#NLReserving}

-  `r pkg("ChainLadder", priority = "core")` provides various statistical methods and models which
are typically used for the estimation of outstanding claims reserves in general (i.e. non-life)
insurance, including those to estimate the claims development result as required under Solvency II.
- `r pkg("clmplus")` implements the chain ladder model under the reverse time framework 
introduced in Hiabu (2017) <doi:10.1080/03461238.2016.1240709> and extensions that add 
flexibility to the individual development factors modeling by allowing practitioners 
to set their own hazard rate model.
- `r pkg("NetSimR")` Provides functions that help model excess levels, capping and pure 
Incurred but not reported claims (pure IBNR) and includes calculating pure IBNR 
exposure with LogNormal and Gamma distribution for reporting delay.

## [Risk and ruin theory]{#RiskRuin}

- `r pkg("actuar", priority = "core")` provides infinite time ruin probability of 
Cramér-Lundberg and Sparre Andersen models, using phase-type distributions
including mixtures of exponentials, Erlang and mixture of Erlang for both claim amount
distribution and claim interarrival times.
- `r pkg("ruin")` implements a collection of common models of risk processes in actuarial science,
represented as formal S4 classes. Each class (risk model) has a simulator of its path, and a
plotting function. Further, a Monte-Carlo estimator of a ruin probability for a finite time is
implemented, using a parallel computation. Currently, the package extends two classical risk models
Cramer-Lundberg and Sparre Andersen models by including capital injections, that are positive jumps.

## [Claim generators]{#ClaimGen}

- `r pkg("SynthETIC")` creates an individual claims simulator which generates various features 
of non-life insurance claims. An initial set of test parameters, designed to mirror the experience
of an Auto Liability portfolio, were set up and applied by default to generate a realistic test 
data set of individual claims (see vignette). The simulated data set then allows practitioners to
back-test the validity of various reserving models and to prove and/or disprove certain actuarial
assumptions made in claims modelling. The distributional assumptions used to generate this data 
set can be easily modified by users to match their experiences.
- `r pkg("SPLICE")` is an extension of `r pkg("SynthETIC")` , to simulate the evolution of case
estimates of incurred losses through the lifetime of an insurance claim. 
The transactional simulation output now comprises key dates, and both claim payments and 
revisions of estimated incurred losses. 
An initial set of test parameters, designed to mirror the experience of a real insurance 
portfolio, were set up and applied by default to generate a realistic test data set of 
incurred histories.

# [Reinsurance]{#Reinsurance}

- for a comprehensive review of extreme value analysis, we refer to the [Extreme value view](https://cran.r-project.org/view=ExtremeValue)
- `r pkg("ReIns", priority = "core")` follows the book "Reinsurance: Actuarial and 
Statistical Aspects" and provides basic extreme value theory (EVT) estimators and graphical methods,
EVT estimators and graphical methods adapted for censored and/or truncated data,
Splicing of mixed Erlang distributions with EVT distributions, 
Value-at-Risk (VaR), Conditional Tail Expectation (CTE) and excess-loss premium estimates.
- `r pkg("ExtremeRisks")` provides a set of procedures for estimating risks related to extreme events via risk measures such as Expectile, Value-at-Risk,...


# [Misc]{#Misc}
## [Data handling]{#Datahandling}
- `r pkg("actuaryr")` contains functions to easily refer to the first or last (working) day 
within a specific period relative to a base date to facilitate actuarial reporting 
and to compare results.
- `r pkg("eiopaR")` provides EIOPA (European Insurance And Occupational Pensions Authority)
risk-free rates.
- `r pkg("actxps")` helps to prepare data, summarize results, and create reports 
via a dedicated S3 class "Actuarial Experience Studies".
- `r pkg("MortalityLaws")` provides functions to read from the Human Mortality Database (HMD),
the Australian Human Mortality Database (AHMD), the Canadian Human Mortality Database (CHMD),
the Japanese Mortality Database (JMD).



## [Actuarial datasets]{#Datasets}

- `r pkg("CASdatasets", priority = "core")` provides a large variety of actuarial datasets,
 originally for the book 'Computational Actuarial Science with R'. Note that the package is 
 not hosted on CRAN but at [CNRS](http://dutangc.perso.math.cnrs.fr/RRepository/) and [UQAM](http://cas.uqam.ca/).
- `r pkg("raw")` organizes several sets of publicly available data of interest to 
non-life actuaries. 
- `r pkg("insuranceData")` provides insurance datasets, which are often used in claims severity 
and claims frequency modelling. It helps testing new regression models in those problems, 
such as GLM, GLMM, HGLM, non-linear mixed models. 
- `r pkg("actuar")` provides functions to facilitate the generation of random 
variates from various probability models commonly used in actuarial applications:
discrete mixtures; compound models where both the frequency and the severity components 
can have a hierarchical structure. 
- `r pkg("Distributacalcul")` calculated expected values, variance, different moments 
(kth moment, truncated mean), stop-loss, mean excess loss, Value-at-Risk (VaR)
and Tail Value-at-Risk (TVaR) but is archived. 
- An Individual Claims Generator for Claims Reserving Studies is provided by Wang & Wuethrich
at [IndividualClaimsSimulator](https://github.com/JSchelldorfer/IndividualClaimsSimulator/).
- An Individual Claims History Simulation machine for annual cashflows is provided by Gabrielli & Wuethrich
at [IndividualClaimsHistory](https://people.math.ethz.ch/~wueth/simulation.html).




