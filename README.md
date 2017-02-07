**Experiment Design**
**Metric Choice**

**Number of cookies:** (dmin=3000)  I chose this as an invariant metric because this metric will not change. The number of cookies to view the course overview page will be the same regardless of whether the cookie is allocated to the control or the experimental group. It doesn't make sense to use it as an evaluation metric because it will not be affected by what the Course Overview page looks like.   
Number of user-ids: (dmin=50) I did not choose this metric as either an invariant or an evaluation metric because a person will not have a user-id unless they register for a course. Hence, it will not help in the experiment. 
**Number of clicks:** (dmin=240) I chose this as an invariant metric because people should be as likely to click on the Start Free Trial button regardless of whether they are in the experiment or the control group. It doesn't make sense to make 
**Click-through-probability:** (dmin=0.01) It is the number of unique cookies to click on the "Start Free Trial" button divided by the number of unique cookies to view the course overview page. This will make a good invariant metric because like Number of Clicks, the metric should be constant throughout both Experimental and Control groups. It will not, however, make a good evaluation metric because it is not subject to the screen that appears after the Start Free Trial button.  
**Gross conversion:** (dmin= 0.01) I chose this metric as an evaluation metric because this metric will help us see whether asking how much time a student is able to devote as an effect on the number of students that enroll and if the chances of student success are higher in the long run. This metric is affected by the screen that appears after clicking the "Start Free Trial" button -- it does not stay constant throughout experimental and control groups. It makes sense to not treat this as an invariant metric. 
**Retention:** (dmin=0.01) I did not choose this as an evaluation metric but it can be one as this metric will help us see if asking the students how much time they have to devote to the course sets more reasonable expectations and encourages them to continue the course after the 14-day period. 
**Net conversion:** (dmin= 0.0075) This can be chosen as an evaluation metric as this metric doesn’t remain consistent and differs depending on whether it is in the control or the experiment group. 




**Measuring Standard Deviation**

For a Bernoulli distribution with probability p and population N, the analytical standard deviation is std = sqrt(p * (1-p) / N).


**Gross Conversion**
```
p = 0.20625
N= 5000*0.08 = 400
std = sqrt(p * (1-p) / N) = 0.0202
```

The unit of analysis and unit of diversion are cookies. That is why the empirical and analytical standard deviations should be the same. 


**Retention**

p = 0.53
N = 5000*0.08 = 400
std = sqrt(p * (1-p) / N) = 0.019

The unit of analysis are user-ids and unit of diversion are cookies. That is why the empirical and analytical standard deviations should be different. 


**Net Conversion**
```
p= 0.1093125
N = 5000*0.08 = 400
std = sqrt(p * (1-p) / N)= 0.0156
```

The unit of analysis and unit of diversion are cookies. That is why the empirical and analytical standard deviations should be the same. 


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

Retention has the largest sample size. Hence, we require a total of 4741212. 


**Duration vs. Exposure**

Let us consider including the metric Retention for a second. If we do include Retention then we will have to have a sample size of 4741212. We will have to run the experiment for 4741212 / 40000 = 118 days. That's a very long time. We could exclude retention and use Gross Conversion and Net Conversion as evaluation metrics instead. 

We will direct 100% of the traffic to our experiment. Since 40000 is the baseline number of visitors per day, the length of the experiment would be 685325 / 40000 = 17.13 days 


When we say that 100% of the traffic goes to the experiment, we mean that 50% of the entire site traffic will go to the control group and 50% will go to the experiment group. 

This experiment does not exceed minimal risk which is to say that the particicpants of this experiment will not be exposed to anything that they would not be exposed to in daily life. Being exposed to the screen after clicking on the 'Start Free Trial' button does not exceed that risk. We are also not dealing with any sensitive data such as political attitudes, personal disease history or sexual preferences. 

The participants also have plenty of choices. There are a plethora of online educational websites like Udacity such as Udemy, Coursera, etc. Hence, you are not coercing any participant. 


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

The effect size tests show us that Gross Conversion is both statistically and practically significant but Net Conversion is not. The screener did filter those out who were not ready for the program. However, the screener also kept those students who were already enrolled in the Free Trial to enroll for the course. We can see that Net Conversion dropped in the experimental group. That was not our intention with the experiment. 

The launch of the screener is based upon two metrics and not one. Hence, it did not make sense to use the Bonferroni correction in the analysis phase. If we had decided to only use one metric out of the many to base our launch decision on then it would've made sense to use the Bonferroni Correction.

The sign tests are there to double-check the results and they tell us the same thing as the effect size tests. Gross Conversion is significant and Net Conversion is not. If we saw any differences in our results, further study would be needed. But in our case, the results from both tests are the same. Hence, We don't need further analysis. 


**Recommendation**
We could see from our results, that the screener filtered out the number of people who enrolled in the free trial but it did not increase the number of people who decided to enroll past the 14-day period. This actually harmed Udacity as our ultimate goal is to increase the number of people who enroll in the program past the 14-day period. The screener actually harmed the website, hence we should not use it. 


**Follow-Up Experiment**
A follow-up experiment that I would want to run is based on user engagement during the free trial period. The main question would be: Is there a way to encourage user engagement to maximize the number of user ids who enroll in the course?

We can measure user engagement by the proportion of the nanodegree that they are enrolled in that they complete. If they are on the right pace (for eg: they login everyday and spend about 45 mins actively engaged, working through a significant enough portion) then they need no encouragement. However, if you don't have them actively involved, then there could be a pop-up upon signing in that would have links to success stories of other students. 

The hypothesis here is that the pop-up might encourage those students who might've otherwise chosen to dropout to continue with the program. Those students who are already committed to the program do not need further encouragement. 

For this experiment, retention rate would be the best evaluation metric to test. We will also be diverting traffic between the control and experimental groups, the most suitable invariant metric will be the number of user-ids that completed checkout and enrolled in the free trial. This experiment will take longer to conduct as well because the inclusion of retention rate adds a significant amount of time to the duration. 
