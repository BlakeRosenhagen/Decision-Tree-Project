# meta idea of project 
final tree generation is contained within a function that takes bool args or parameters from decision tree parameter optimization note books


web application that plots graphs of your statistic tree graphs.

overall project will have a jupyter notebook version and a dash plotly version

# meta structure of project


## Module 1 feature selcection/ dimensionality , 
Feature selection / dimensionality reduction is used to increase accuracy scores on very high dimensional data sets 

Advantages: 
    Nice interpretation: Feature importance is the increase in model error when the feature’s information is destroyed.

    Feature importance provides a highly compressed, global insight into the model’s behavior.

    A positive aspect of using the error ratio instead of the error difference is that the feature importance measurements are comparable across different problems.
Double Edge:
    The importance measure automatically takes into account all interactions with other features. By permuting the feature you also destroy the interaction effects with other features. This means that the permutation feature importance takes into account both the main feature effect and the interaction effects on model performance. This is also a disadvantage because the importance of the interaction between two features is included in the importance measurements of both features. This means that the feature importances do not add up to the total drop in performance, but the sum is larger. Only if there is no interaction between the features, as in a linear model, the importances add up approximately.

Disadvantages:
    Unclear whether you should use training or test data to compute the feature importance.

    Permutation feature importance is linked to the error of the model. This is not inherently bad, but in some cases not what you need. In some cases, you might prefer to know how much the model’s output varies for a feature without considering what it means for performance. 

    You need access to the true outcome. If someone only provides you with the model and unlabeled data – but not the true outcome – you cannot compute the permutation feature importance.



    The permutation feature importance depends on shuffling the feature, which adds randomness to the measurement. When the permutation is repeated, the results might vary greatly. Repeating the permutation and averaging the importance measures over repetitions stabilizes the measure, but increases the time of computation.


    If features are correlated, the permutation feature importance can be biased by unrealistic data instances.The permutation of features produces unlikely data instances when two or more features are correlated. When they are positively correlated (like height and weight of a person) and I shuffle one of the features, I create new instances that are unlikely or even physically impossible (2 meter person weighing 30 kg for example), yet I use these new instances to measure the importance. In other words, for the permutation feature importance of a correlated feature, we consider how much the model performance decreases when we exchange the feature with values we would never observe in reality. Check if the features are strongly correlated and be careful about the interpretation of the feature importance if they are.

    another tricky thing: Adding a correlated feature can decrease the importance of the associated feature by splitting the importance between both features. 

    @@@@@@ more on this down below


2. scikit learn provides a module for feature selection that can be executed a number of ways including for a small variety of data descriptions. The following four types of feature selection/dimensionality reduction methods are to be used when considering coefficients of a linear model

    1. removing features with low variance, since I would assume that their wouldnt be enough range in certain

    2. Univariate feature selection works by selected features based on how they score on univarite statistical tests

    3. Recursive feature elimination which goes about selected incrementally smaller sets of features

    4. feature selection using SelectFrom Model, features that do perform under a threshold parameter are taking from the selected features as they are deemed unimportant

    There is a underlining potental problem when it comes to using the four stated methods desscribed above when selecting important features. That is when your dataset consist of non-linear or hiding estimators that are not apparnet when looking at the variables as univariate. 

    Further complocation arise when we are dealing with features that are highly correlated with each other

    In the following section, we will discuss the solution/mitigation to this complex issue.

2. Permutation Feature importance
"The permutation feature importance is defined to be the decrease in a model score when a single feature value is randomly shuffled 1. This procedure breaks the relationship between the feature and the target, thus the drop in the model score is indicative of how much the model depends on the feature."

Permuation feature importance can "shake-up" variables as features are randmly shuffled  a set amount of times detailed as n_reapeats. Each sample of importances in this collection of permutations is then evaluated through mean decrease accuracy
    
2. 
    
    Even with using permutation importance as a method, you still may be missing nuances in the data. This is because there is a possibility that some features are highly correlated with each other.

    In this instance, as said above using standard feature selection methods as well as standard permutation importance may cause features to split their importance among the groups of features that are correlated with each other. For example if you have 2 features among 30 that are highly correlated, then the scorer will assign a similar amount of performance that individually each feature should earn, but instead the each one is only granted a portion of importance. This can be very harmful to the overall model if those misunderstood features are then discarded for not reaching a set threshold then their predictive ability is wasted.. As well, other less important features's importance can be overstated in comparison.


To find if any of your features are multicollinear, so that we can assign weigths appropriately, we will create a hierarchy dendrogram and



So what now? It certainly seems like I am stating that any method of feature selection/dimension is not          . Each of the methods I have described have their use cases, so it is up to the user to find the apprioate method for your data set. 




# Decision Tree Classifier Parameters

The minimum weighted fraction of the sum total of weights (of all the input samples) required to be at a leaf node. Samples have equal weight when sample_weight is not provided. weights can be provided by permutation importance










part of final product: matric structure of classification
    https://scikit-learn.org/stable/auto_examples/tree/plot_iris_dtc.html#sphx-glr-auto-examples-tree-plot-iris-dtc-py



used for completed documentation
    https://towardsdatascience.com/how-to-tune-a-decision-tree-f03721801680

    https://stackoverflow.com/questions/54812230/sklearn-min-impurity-decrease-explanation




# References
Interpretable Machine Learning: A Guide for Making Black Box Models Explainable.
by
Christoph Molnar
https://christophm.github.io/interpretable-ml-book/feature-importance.html


All Models are Wrong, but Many are Useful: Learning a Variable's Importance by Studying an Entire Class of Prediction Models Simultaneously
by
Aaron Fisher, Cynthia Rudin, Francesca Dominici
https://arxiv.org/abs/1801.01489


Random Forests
by
Leo Breiman
https://link.springer.com/article/10.1023%2FA%3A1010933404324
