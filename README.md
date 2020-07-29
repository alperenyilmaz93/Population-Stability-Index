# Population-Stability-Index
What is the population stability index (PSI)?
PSI is a measure of how much a population has shifted over time or between two different samples of a population in a single number. It does this by bucketing the two distributions and comparing the percents of items in each of the buckets, resulting in a single number you can use to understand how different the populations are. The common interpretations of the PSI result are:

•	PSI < 0.1: no significant population change
•	PSI < 0.2: moderate population change
•	PSI >= 0.2: significant population change

# How is PSI used?

There are two different ways PSI can be used to make good decisions in a machine learning model building context

# Reactive Re-training Triggers

After a deploying a ML model into production, it will continue to provide estimates on the population it was trained on. As the population shifts over time, the estimates become less accurate and relevant to the current population, and monitoring the PSI score from the time of model training to current time can be used as automatic triggers to re-train the model when PSI passes a certain threshold (0.2 for example).

# Proactive Feature Selection

When choosing features to go into a model, certain features may have a lot of predictive power at the time of training, but if a feature is prone to rapid changes in distribution, it may not be a wise decision to include it in the model or it may prompt more frequent monitoring once deployed. PSI is an easy way to check the volatility of population changes for features by comparing populations for several previous time periods.

