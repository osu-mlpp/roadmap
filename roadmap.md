# Goal
The goal of this project is to try to define a more accurate way to evaluate a score's pp value on a map using existing map statistics and machine learning.


# General Algorithm Structure
The whole final MLpp project should consist of the following parts :
1. Data to % curve stats
2. % curve stats to pp estimation and estimated estimation accuracy
3. Generate new db with pp data from the new estimated pp values
4. Iterate multiple time on the new data to improve estimations
5. Build a Neural network to output
6. Neural network to output pp from a beatmap (trained by the generated estimations)
7. (Potentially) a pp estimator from a few neural network pp samples to improve real time pp estimation performances


# Roadmap (Things to do)
Note : Those parts and tasks are not needed to be done in order, and doing them in parallel should help advancing faster in the project.

At the end of each task is added a time needed estimation and objective.

## Part 1 - Theory

### Statistical part
#### General
> lenght: few hours - objective: mid june
- Improve the whole general data to stats curve algorithms/formulas definition
- redefine the stats curve to pp estimation function
- redefine the stats curve to estimated estimation accuracy function

#### Outliers
> lenght: 1-2 weeks - objective: end of june
- Find more outliers ?
- Improve outliers definitions
- Improve outliers handling technique definitions
- Find more outliers handling technique on existing outliers ?
- Write down formulas / algorithms for outliers handling

### Machine Learning part
> length: ??? - objective: end of july
- Define the different possible input / output shapes
- Define different possible network shapes
- Estimate and compare the different chances of sucess and potential estimation accuracy of the different input/output and network shapes


## Part 2 - Project Description
> lenght: few days - objective: mid june
- Rewrite a short and easily understable version of the project idea
- Finish/rewrite a complete description of the project and each of it's parts.


## Part 3 - Data Collection
> lenght: depends on other parts - objective: end of june
- List all needed and desirable data properly (depends on other parts)
- Define the rank to sampling density function required to achieve the best statistical accuracy.
- Convince peppy to start collecting the not yet collected data (1~3 months of data collection will be needed).  
Note 1 : Having some first impletation of the statistical part would probably help in convincing peppy that we can achieve good results, but at the same time the earlier the data collection starts, the better since we'll have to wait for the data to be collected to be able to actually do something with it.
Note 2 : While the data collection might take a while (mini 1 month), we can probably start to work with the first few weeks of data to get something running faster when the data will finally be ready.
- Possibly help in the implementation of the actual data collection


## Part 4 - Implementation
### 4.1 - Statisical pp
#### Statical pp estimator
> lenght: 1-2 weeks - objective: end of june
- Implement database data extraction functions
- Implement a function that returns the % of players of a defined pp range that can do more than a specified score (defined in acc/combo/miss)
- Implement a function that returns the 4D % curve in function of acc/combo/miss and player's pp group.
- Implement a basic 4D % curve to score pp estimator
- Implement the evaluation of the accuracy of the pp estimations
- Implement the outlier handlers to improve the pp estimations (Note : Only simple outliers handlers that only uses currently available data are expected to be implemented by the end of june, the others can be implemented later)
#### Iteration of pp estimator
> lenght: ~1 week - objective: mid july
- Implement the generation of a new database from the pp estimations
- Implement the iteration of the statistical pp estimation to improve estimations
#### Map-portion pp estimator
> lenght: ~1 weeks - objective: end of july
- Adapt the previous implementations to support the estimation of the pp value of map portions
#### Evaluation of the results
> lenght: 1~2 weeks - objective: ???
- Recruit experimented people to judge the quality of the generated pp estimations
- Ask those people to evaluate the quality of the results of the estimations


### 4.2 - Neural network
> lenght: 2~4 weeks - objective: end of august
- TBD


## Part 5 - Post-Implementation
> lenght: unknown - objective: none yet
### Neural network ouput analysis
- If the results are not satisfactory enough or if peppy doesn't want to use the network as it is in production, we can potentially try to analyse the outputs of the neural network to try to improve pp v2 or define a new pp algorithm from scratch.
- If the Neural nets produces satisfactory results but is too slow to recompute the pp value for every new score, we can implement a pp curve estimator using samples from the neural network output.
