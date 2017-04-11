# Bad Data Handbook 
Q. Ethan McCallum, O'Reilly

### How do we measure the quality of data?
1. Do we have all data we need to answer the question?
1. Are those data related to each other?
1. Are values in data correct?
1. Can we trace it? Can we know the source and destination of personal information for each one?

### How do we trace our data
1. Snapshotting/Imutable data
1. Adding source column on data at every transition steps
1. Scoring data source if there are multiple source for same data
1. Programable data source
1. Separating each transition steps

### How to create campaign on Kaggle
1. Defining a specific question that fit to your problem.
1. Prototyping and verifying if we can solve our problem by answering the question.
1. Preparing training data, and separating data to training, testing and answer.
1. (Optional) Extracting features.
1. Defining input/output and encoding data.
1. Describing qestion on Kaggle and answering questions from user.
1. Chosing best solution and integrating to our product.

### Data Science Trap
1. Assuming data is correct and complete.
   * We may find data lose by some simple sum or count.
   * We shouldn't assume the time range information on folder or file name is exactly match the data.
1. Limiting tools for data analysis.
   * Ad-hoc analysis always encounter new issues that need new tools to workround it.
   * It's better to prepare separated analysis envieronment from production.
1. Analysing for analysing
   * We must clarify target and questions before analysis
1. Not sharing
1. Expecting full-stack data scientist

### Biase Source on Survey
1. Estimated biased, how do we extimate on data miss?
    * Just use it
    * Replacing by admainistrative data
    * Weighting light
    * Dropping it
1. Wrong reporting
    * Is it random?
    * Does it happen on some specific fields?
    * Could we replace it by admanistrative data?
    * Could we reduce it by reorganize the survay?
1. Topcoding/bottomcoding
1. Proxy reporting
1. Sample selection

### Lab
1. Working together with whom made data. 
1. Experiments in Lab without steps log is invalid
1. Every value should be checked by workmate before inserting to database.
1. Limit field values and automatically filling excel to database
1. Always checking type, precondition, and reasonable value range. Including measure in variable naming rule

