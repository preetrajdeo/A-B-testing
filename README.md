**Experiment Design**
**Metric Choice**

**Number of cookies:** (dmin=3000)  I chose this as an invariant metric because this metric will not move. The number of cookies to view the course overview page will be the same regardless of whether the cookie is in the control or the experiment group. 
Number of user-ids: (dmin=50) I did not choose this metric as either an invariant or an evaluation metric because a person will not have a user-id unless they register for a course. Hence, it will not help in the experiment.
**Number of clicks:** (dmin=240) I chose this as an invariant metric because people should be as likely to click on the Start Free Trial button regardless of whether they are in the experiment or the control group.
**Click-through-probability:** (dmin=0.01) I did not choose this metric to be an invariant metric but it can be one since this metric doesn’t move either.
**Gross conversion:** (dmin= 0.01) I chose this metric as an evaluation metric because this metric will help us see whether the asking how much time a student is able to devote as an effect on the number of students that enroll and if the chances of student success are higher in the long run. 
**Retention:** (dmin=0.01) I did not choose this as an evaluation metric but it can be one as this metric will help us see if asking the students how much time they have to devote to the course sets more reasonable expectations and encourages them to continue the course after the 14-day period. 
**Net conversion:** (dmin= 0.0075) This can be chose as an evaluation metric as this metric doesn’t remain consistent and differs depending on whether it is in the control or the experiment group. 




**Measuring Standard Deviation**

For a Bernoulli distribution with probability p and population N, the analytical standard deviation is std = sqrt(p * (1-p) / N).


**Gross Conversion**
```
p = 0.20625
N= 5000*0.08 = 400
std = sqrt(p * (1-p) / N) = 0.0202
```


The unit of analysis is the user id that clicks on the “Start Free Trial” button and the unit of diversion is measure by a cookie that clicks on the start free trial button. Personally I visited the Udacity page multiple times from different devices before I decided to start the free trial. I think it would be a good idea to get more data and confirm our results empirically. 


**Net Conversion**
```
p= 0.1093125
N = 5000*0.08 = 400
std = sqrt(p * (1-p) / N)= 0.0156
```


Here too our unit of analysis is the number of user ids that click on the Start Free Trial button, while the unit of diversion is calculated by the number of cookies that perform the action. It would be a good idea to measure the results empirically if there’s more time and data to be safe. 


**Sizing**

Number of Samples vs. Power
I decide not to use the Bonferroni correction. 


**Gross Conversion:** 
```
Baseline conversion rate: 0.20625
d_min: 0.01
Required number of samples: 25835
According to these metrics, the number of clicks on the start free trial should be 25835 / 0.08 * 2 = 645875. Hence, we will have 645875 pageviews.
```


**Retention:**
```
Baseline conversion rate: 0.53
d_min: 0.01
Required number of samples: 39115
According to these metrics, the number of clicks on the start free trial should be 39115 / 0.08 / 0.20625 * 2 = 4741212
```


**Net conversion.**
```
Baseline conversion rate:  0.1093125
d_min: 0.0075
Required number of samples: 27413
According to these metrics, the number of clicks on the start free trial should be 27413 / 0.08 * 2 = 685325 pageviews
```




**Duration vs. Exposure**


We will direct 50% of the traffic to our experiment. Since 40000 is the baseline number of visitors per day, the length of the experiment would be 685325 / (40000 * 0.5) = 34.3 days 


When we say that 50% of the traffic goes to the experiment, we mean that 25% of the entire site traffic will go to the control group and 25% will go to the experiment group. This can be a large risk because we a quarter of our site traffic will be going to a feature that is not evaluated. If the feature does not have the intended effect, it can reduce the number of people who click on “Start Free Trial”. 


**Experiment Analysis**

**Sanity Checks**

|                                         | Lower Bound  | Upper Bound | Observed Value  | Pass    |
|-----------------------------------------|--------------|-------------|-----------------|---------|
| Number of Cookies                       | 0.4988       | 0.5012      | 0.5006          | Passed  |
| Number of Clicks on “Start free trial”  | 0.4959       | 0.5041      | 0.50046         | Passed  |


**Result Analysis**
**Effect Size Tests**

|                  | Lower Bound  | Upper Bound | Observed Value  | Practical and Statistical Significance         |
|------------------|--------------|-------------|-----------------|------------------------------------------------|
| Gross Conversion | -.0291       | -.0120      | 0.5006          | Practically and statistically significant      |
| Net Conversion   | -0.0116      | 0.0019      | 0.50046         | Not practically and statistically significant  |












**Sign Tests**
```
Gross Conversion p-value: 0.0026
0.0026<0.05. Hence the Gross Conversion p-value is statistically significant
Net Conversion p-value: .6776
0.6776>0.05. Hence the Net Conversion p-value is statistically significant
```










**Summary**

State whether you used the Bonferroni correction, and explain why or why not. If there are any discrepancies between the effect size hypothesis tests and the sign tests, describe the discrepancy and why you think it arose.
I did not choose to use the Bonferroni correction because only one variation is being tested here. However, it could be useful to use the Bonferroni correction if we want to segment our results even further. For example, if we decide to see device type, age or gender, etc. 


**Recommendation**
I recommend that you use the question because while it did not help in converting the enrollment into a payment, it did reduce the number of students who signed up for the free trial to begin with. Hence, I think it helps in making sure the students have a realistic idea of how much work a course would take. 


**Follow-Up Experiment**
A follow-up experiment that I would want to run is user engagement. I would like to see how engaged those users are who 
Give a high-level description of the follow up experiment you would run, what your hypothesis would be, what metrics you would want to measure, what your unit of diversion would be, and your reasoning for these choices.


