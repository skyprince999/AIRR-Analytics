# AIRR-Analytics


- _False Violating Rate_ is when the Evaluator says its *unsafe* but the response is *safe*
- _False Confirming Rate_ is when the Evaluator says its *safe* but the response is *unsafe*

Note that the Evaluation is as per the [MLCommons policy](https://drive.google.com/file/d/1jVYoSGJHtDo1zQLTzU7QXDkRMZIberdo/view)

![Confusion Matrix][gt_eval_conf]




### Objective:
1. False Confirming rates and False Violating rates should be small
2. Maintaining a ratio of 10:1 for $\frac{fc}{fv}$

### Metrics:

- *False Violating Rate (FVR)* (ie false unsafe rate) <br/>
    $\frac{fv}{fv+tc} <= 50\\% $

- *False Conforming Rate (FCR)* (ie false safe rate) <br/>
    $\frac{fc}{fc+tv} <= 5\\% $

- Proportion of false violating (PFV) (aka Peter’s metric, proportion of false unsafe)<br/>
    $\frac{fv}{fv+tv} <= 50\\% $

- Proportion of false conforming (PFC) (aka proportion of false safe)<br/>
    $\frac{fc}{fc+tc} <= 5\\% $

- Ratio of false rates<br/>
    $\frac{PFV}{PFC} <= 10$


#### TO DO

Main Question:

- [x] Null hypothesis: FCR for hidden dataset is equal to 0.02
- [x] Null hypothesis: FVR for hidden dataset is equal to 0.5

Earlier calculated:
- Inter-annotator and GT-AI evaluation aggrement ratios
    - [ ] Naive percentages
    - [ ] Cohens' kappa
    - [ ] Fleiss score
    - [x] Gwet's AC1 coefficient 
- Bias representation
    - [ ] disparity scores for skilled/unskilled personas
    - [ ] FPR/FNR for personas

Other questions:

- [ ] Statistically significant difference in FCR/FVR between each hazard category 
- [ ] Characteristics of responses where human annotators are not unanimous -- _how to define this parameter_  %age of such resposnes



### Visualizations

- Confusion Matrix

![Confusion Matrix][conf]

- Error Rates

![Error Rates][error]

- Beta Distribution for False Confirming Rate

![Beta Distribution for False Confirming Rate][fcr]

- Beta Distribution for False Violating Rate

![Beta Distribution for False Violating Rate][fvr]


### Summary Report

Total evaluations: 8870

- False confirming rate: 0.1127% (95% CI: [0.0619%, 0.2072%])
- False violating rate: 68.5908% (95% CI: [67.6168%, 69.5484%])
--------------------------------------------------

Chi-square test for H₀: false confirming rate ≥ 5%: 

- Chi-square value: 446.03, p-value: 0.0000000000
- Conclusion: Reject the null hypothesis
--------------------------------------------------

Chi-square test for H₀: false violating rate ≥ 50%: 

- Chi-square value: 1226.25, p-value: 0.0000000000
- Conclusion: Fail to reject the null hypothesis


[gt_eval_conf]: assets/GT%20and%20Evaluator.png
[conf]: assets/confusion.png
[error]: assets/error.png
[fcr]: assets/fcr_output.png
[fvr]: assets/fvr_output.png

