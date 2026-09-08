## Core research idea

Investigate which measurable characteristics of My Little Pony fanfiction stories on Fimfiction are associated with **reader engagement / story success**.

The study is deliberately restricted to Fimfiction rather than fanfiction across multiple fandoms, because different fandoms have substantially different audience sizes and cultures. Restricting the study to one platform and fandom reduces the confounding effect of fandom popularity.

The eventual goal may include producing a downloadable statistical model that authors can run locally against their own fic to estimate how its characteristics compare with stories historically associated with higher or lower reader engagement.

A further possible goal is to evaluate how accurately such a model predicts engagement for stories that were not used to create it.

---

## Current methodological principle

The study should be designed **before accessing/analysing the dataset**.

The intention is not to obtain a large dataset and then search for arbitrary correlations. Candidate variables and hypotheses should be identified first, with the final confirmatory hypotheses and analysis plan defined before the relevant data is examined.

Possible exploratory analysis can be distinguished from the preregistered/confirmatory analysis.

The eventual modelling approach remains undecided. It may involve a conventional statistical model, such as a multiple linear regression model or another regression-based method, or it may involve a machine-learning model. The choice should depend on the outcome variable, the distribution of the data, the number and type of predictors, and the primary purpose of the model.

If the main purpose is explanation and estimation of associations, a conventional statistical model may be preferable. If the main purpose is prediction, a machine-learning approach or a predictive statistical model may be appropriate. These possibilities are not mutually exclusive.

---

## Null / alternative hypothesis framework

Initial conceptual null hypothesis:

> **H₀:** No individual candidate factor has a statistically significant association with the predefined measure of story success/reader engagement.

Individual hypotheses would then test specific candidate factors.

There may ultimately be a large number of candidate hypotheses (initially conceptualised as H₁ through H₄₀ and beyond).

The direction of effects should **not** be assumed in advance unless there is a strong theoretical justification.

### Two-tailed testing

The planned analyses should generally be two-tailed.

The question is:

> Does X have an association with story engagement?

rather than:

> Does X improve story engagement?

This deliberately permits a factor to be positively associated, negatively associated, or unrelated to engagement.

Example:

> Early post-publication editing could potentially be associated with higher engagement, lower engagement, or no difference.

---

## Dependent variable / definition of success

A precise operational definition of "success" / "reader engagement" needs to be established **before data collection**.

One previously used conceptual metric is:

> **Like/dislike ratio relative to read count**, with story age taken into account.

Rationale:

- Read counts can increase through rereading.
    
- An individual reader can only like/dislike a story once.
    
- Therefore likes/dislikes and reads represent different types of accumulated behaviour.
    
- Story age matters because older stories have had more time to accumulate reads and rereads.
    

Potentially retain the raw counts as well as any derived engagement metric.

Potential engagement variables visible on the site may include:

- reads
    
- likes
    
- dislikes
    
- comments
    
- follows
    
- favourites
    
- other available engagement statistics
    

It remains undecided whether "success" should be represented by one predefined composite metric or whether different forms of engagement should be treated as separate dependent variables.

The outcome variable must be defined before model development. If the outcome is a continuous measure, a regression-based model may be appropriate. If it is converted into categories such as high- versus low-engagement stories, classification methods may be appropriate. The choice of outcome definition will affect both the statistical analysis and the type of model that can be saved and evaluated.

---

## First-impression hypothesis

A major conceptual motivation is:

> **First impressions count.**

The first chapter is therefore of particular interest.

Every story has at least one chapter, whereas stories can have very different numbers of chapters. Analysing the first chapter provides a consistent textual unit across stories without having to control for arbitrary total chapter counts.

Potential question:

> Are characteristics of the first chapter associated with eventual reader engagement?

The first chapter is intended to represent what a prospective reader encounters initially.

---

## Candidate textual variables

### Grammar / proofreading

Use **LanguageTool** as a local grammar-analysis system.

Potential measurements include raw grammar/proofreading error counts and normalised measures such as errors per number of words.

Use **Vale** as a second local textual-analysis system.

LanguageTool and Vale are intended to capture different aspects of writing quality/style rather than being collapsed immediately into one score.

Potential questions include whether measurable grammatical/style characteristics of the first chapter are associated with engagement.

The direction of any relationship is not assumed.

### Word-frequency / lexical analysis

Potential feature identified:

> Frequency distribution of words within the document/chapter.

A word-cloud-style representation was considered as a possible way of visualising this, but the actual research interest is in **measurable statistics derived from word-frequency distributions**, rather than identifying individual "popular words."

Stop/filler words may be filtered for some analyses or visualisations, while retaining the underlying corpus where appropriate.

Potentially useful measurements could include characteristics of the overall frequency distribution and other lexical statistics.

This remains a **candidate feature family**, not yet a defined hypothesis.

---

## Editing behaviour

Potential candidate variable:

> **Editing occurring shortly after publication**, particularly within the first 48 hours.

The theoretical connection is to first impressions.

Important distinction:

### Pre-publication editing

Should **not** be treated as part of the first-impression editing variable.

Fimfiction allows authors to write/edit chapters on the site before publication and can allow proofreaders access before publication.

Therefore:

> Editing performed before the chapter is made publicly available represents the author's preparation process, not changes to the reader's initial experience.

### Post-publication editing

Potentially distinguish:

- edits within the first 48 hours
    
- edits after the first 48 hours
    
- number of edits
    
- timing of edits
    

The precise variable depends on what historical editing information Fimfiction makes available.

Important data question:

> Does Fimfiction expose a complete revision/edit history, or only a publication/current-modification timestamp?

A current "last modified" date alone may not be sufficient to reconstruct early editing behaviour.

---

## Possible secondary editing study

A later/secondary study could investigate whether subsequent edits are associated with proofreading feedback from readers.

Potential question:

> Among stories that are edited after publication, do later edits correlate with comments containing proofreading/grammar feedback?

This is separate from the primary first-impression analysis.

Possible conceptual sequence:

> Reader comments → proofreading feedback → subsequent author edits

The purpose would be to investigate whether post-publication editing appears to respond to reader feedback.

This should not be retroactively folded into the primary hypothesis if discovered after examining the data.

---

## Candidate metadata variables / covariates

Variables already identified as potentially relevant include:

- publication date
    
- chapter publication date
    
- story age
    
- number of chapters
    
- whether/how often the story is edited
    
- timing of edits
    
- story tags
    
- genre/category
    
- other metadata exposed by Fimfiction
    
- author characteristics/history, where observable
    
- potentially prior author success/engagement
    

The exact set remains to be determined by investigating what data Fimfiction actually captures and makes available.

---

## Potential confounders

### Story age

A major potential confounder.

Older stories have had more time to accumulate:

- reads
    
- rereads
    
- likes/dislikes
    
- comments
    
- follows/favourites
    

Therefore publication date / story age needs to be explicitly considered in the analysis.

### Number of chapters

Stories do not all have the same number of chapters.

This cannot simply be controlled by analysing "the first N chapters" because some stories have only one chapter.

The first chapter provides a consistent minimum unit:

> Every story has one or more chapters.

Total chapter count may nevertheless be a useful story-level covariate.

### Reader demographics

Potentially relevant but difficult or impossible to observe directly:

- reader age
    
- reader education level
    
- reader experience with the fandom
    
- other demographic characteristics
    

These may represent unmeasured confounders.

Do **not** assume account creation date represents reader age.

For example, a user who joins Fimfiction recently could be:

- a young person newly discovering G4 through TikTok/YouTube/etc.
    
- an older person returning to the fandom
    
- someone who has simply never previously had a Fimfiction account
    

Therefore registration cohorts may not provide a reliable direct measurement of reader age.

### Changes in the Fimfiction audience over time

The readership itself may change over time.

For example, renewed interest in Generation 4 My Little Pony content through YouTube, TikTok, Reels, etc. could introduce new readers at different points in the site's history.

This makes temporal variables particularly important and potentially complicates attempts to infer reader demographics from account-registration cohorts.

---

## Corpus inclusion/exclusion and data safety

### Prohibited / offensive material

The research corpus will explicitly exclude stories containing illegal or otherwise prohibited/offensive material.

A specific example is sexually explicit material involving minors or otherwise prohibited sexual content.

The purpose of this exclusion is both methodological and practical:

- Such material is not required for the research question.
    
- The researcher does not want prohibited/offensive material downloaded or retained on local storage.
    
- Text analysis should therefore be performed only on the permitted research corpus.
    

### Timing of exclusion

The exclusion criteria should be defined **before data collection**.

Where possible, prohibited material should be identified using metadata/content classifications available from Fimfiction **before downloading the story text**.

The preferred approach is therefore:

> Identify eligible stories → exclude prohibited categories → download/analyse permitted corpus.

Rather than:

> Download all stories → inspect/analyse them → remove prohibited material afterwards.

This minimises the amount of prohibited material that ever reaches local storage.

### Methodological consequence

Excluding these stories may introduce **selection bias**.

The resulting model would not necessarily describe every story hosted on Fimfiction. Its population would instead be the defined eligible research corpus.

This limitation should be explicitly documented in the methodology.

The exclusion should remain fixed throughout the confirmatory analysis rather than being altered based on observed statistical results.

### Data retention

Only data necessary for the research should be retained.

The study should avoid retaining excluded story text, and the final dataset should contain only stories meeting the predefined inclusion criteria.

---

## Data acquisition questions

Before finalising the study, determine what Fimfiction publicly exposes and/or what can be obtained through its API.

The initial task is therefore to examine:

> **What data exists behind the statistics that Fimfiction displays?**

Rather than beginning with the assumption that every desired variable is obtainable.

Potentially investigate:

- story metadata
    
- chapter metadata
    
- publication timestamps
    
- modification/edit timestamps
    
- revision history
    
- tags
    
- genre/category
    
- rating
    
- reads
    
- likes
    
- dislikes
    
- comments
    
- follows/favourites
    
- author history
    
- other available engagement statistics
    

---

## Contact with Fimfiction

Before large-scale data collection, approach the site owner/administrators regarding:

- API/data access
    
- acceptable data-collection methods
    
- rate limits
    
- acceptable request frequency
    
- whether bulk access is available
    
- whether historical statistics are available
    
- whether revision/edit histories are available
    
- whether there are restrictions on storing/analyzing story text
    
- preferred method for obtaining the data
    

The study should be designed to avoid placing unnecessary load on Fimfiction's systems.

Potential safeguards:

- rate limiting
    
- local caching
    
- avoiding repeated requests
    
- sequential rather than aggressive concurrent requests
    
- only requesting the information actually required
    
- complying with the site's stated requirements
    

---

## Important distinction: observable vs. derived vs. unobservable

For every candidate variable, determine which category it belongs to.

### Directly observable

Information supplied by Fimfiction.

Examples:

- publication date
    
- tags
    
- reads
    
- likes/dislikes
    
- chapter information
    

### Derived

Information calculated from directly observed data.

Examples:

- story age
    
- errors per 1,000 words
    
- engagement rate
    
- chapter-length statistics
    
- lexical statistics
    

### Unobservable / latent

Things that may theoretically matter but cannot be reliably measured from the available data.

Examples:

- reader age
    
- reader education
    
- individual reader motivation
    
- whether a specific reader abandoned a story because of grammar
    
- subjective reader preferences
    

Unobservable factors should be acknowledged as potential limitations rather than replaced with unjustified proxies.

---

## Model development and validation

The model should be evaluated on stories that were not used to fit or create it.

A possible initial design is to reserve approximately **20% of the stories as test data**, while using the remaining 80% as the training or development data.

The 20% test set should be held out from the beginning and not used for:

- selecting predictors
    
- choosing transformations
    
- tuning model parameters
    
- deciding which hypotheses to retain
    
- evaluating competing models
    
- making repeated informal checks during development
    

The model would be created using the remaining 80%, then applied once to the held-out stories to estimate out-of-sample performance.

The exact split is still undecided. Depending on the final modelling approach and dataset size, alternatives may include:

- a training/validation/test split
    
- cross-validation within the development data, followed by one final evaluation on the held-out test set
    
- bootstrap validation
    
- repeated cross-validation
    
- temporal validation, in which newer stories are used as the test set
    

A random 80/20 split may be inappropriate if stories are strongly clustered by author or publication period. If multiple stories by the same author are included, stories from the same author may need to remain in the same partition to avoid information leakage. A time-based split may also be useful if the intended application is to predict engagement for future stories.

The validation strategy should be defined before examining the test-set results.

---

## Statistical model versus machine-learning model

It is not yet necessary to decide whether the final approach will be called a "statistical model" or a "machine-learning model."

A conventional regression model, such as multiple linear regression, can be saved and later applied to new observations. The fitted model consists of estimated parameters, such as regression coefficients and an intercept, together with the preprocessing rules used to construct the predictors. Those components can be stored and reused to generate predictions for new stories.

Other conventional models, including logistic regression, Poisson or negative-binomial regression, ordinal regression, and generalized linear models, can likewise be fitted, saved, and applied later.

Machine-learning models work similarly in this respect: after training, the fitted model and its preprocessing steps can be saved and used to predict outcomes for new data.

The distinction is therefore not whether a model can be saved for later use. Both conventional biostatistical models and machine-learning models can be saved and tested on new observations. The more important distinctions concern:

- the type of outcome being modelled
    
- whether the primary goal is explanation or prediction
    
- how flexible the model is
    
- how model complexity is controlled
    
- how uncertainty is reported
    
- how performance is evaluated
    
- how interpretable the resulting model is
    

The final model should preserve all preprocessing information required for later use, including:

- word-count rules
    
- stop-word handling
    
- text-cleaning procedures
    
- LanguageTool and Vale settings
    
- transformations of predictors
    
- scaling or standardisation parameters
    
- handling of missing values
    
- encoding of categorical variables
    
- any feature-selection rules
    

The local author-facing tool should apply exactly the same preprocessing pipeline used during model development.

---

## Possible performance measures

The appropriate performance measures depend on the final outcome and model type.

For a continuous engagement outcome, possible measures include:

- mean absolute error
    
- root mean squared error
    
- correlation between predicted and observed values
    
- calibration or agreement between predicted and observed values
    
- explained variance or related measures
    

For a binary or categorical outcome, possible measures include:

- accuracy
    
- sensitivity
    
- specificity
    
- precision
    
- recall
    
- F1 score
    
- area under the receiver operating characteristic curve
    
- calibration
    

Performance should be reported on the held-out test data, with uncertainty estimates where feasible.

A model that finds statistically significant associations is not necessarily a model that predicts new stories accurately. Inferential results and predictive performance should therefore be treated as related but distinct objectives.

---

## Current project workflow

The intended order is:

1. Identify the research question.
    
2. Define what "success" / reader engagement means.
    
3. Identify candidate features and predictors.
    
4. Identify potential confounders and covariates.
    
5. Define corpus inclusion and exclusion criteria.
    
6. Determine what variables are actually observable from Fimfiction.
    
7. Determine what variables can be derived locally from the available data.
    
8. Determine which candidate hypotheses are sufficiently well-defined and defensible.
    
9. Decide whether the primary goal is explanation, prediction, or both.
    
10. Define the statistical/model-development plan.
    
11. Define the confirmatory hypotheses and operational definitions.
    
12. Define the validation strategy, including any held-out test set.
    
13. Publish/preregister the planned test.
    
14. Approach Fimfiction regarding data/API access.
    
15. Acquire the data without unnecessarily stressing the site.
    
16. Construct the development and test partitions without using the test data for model decisions.
    
17. Run the predefined analysis and develop the model using only the development data.
    
18. Evaluate the final model on the held-out test data.
    
19. Clearly distinguish confirmatory results from any subsequent exploratory analyses.
    
20. Potentially package the final model and preprocessing pipeline for local use.
    

---

## Potential practical output

If the analysis produces a useful predictive model, a second-stage application could allow an author to run their own fic through the analysis locally.

The tool could extract the same predefined textual features—potentially including LanguageTool, Vale and lexical statistics—and provide a prediction based on the statistical model.

The model and its preprocessing pipeline could be saved in a reusable format so that the application can apply them to new stories without refitting the model.

The intended interpretation would be:

> How similar are this story's measurable characteristics to characteristics historically associated with reader engagement on Fimfiction?

It should **not** be represented as an objective measure of whether a story is "good."

The tool should also communicate that predictions are estimates based on historical data and may be less reliable for stories that differ substantially from the stories used to develop the model.