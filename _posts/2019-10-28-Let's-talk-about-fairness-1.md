This series of posts is a summary of fairness issues in machine learning. Fairness is a wide subject to study, spanning various disciplines including computer science, social science, law etc. My posts mainly focus on the different definitions for fairness and algorithms to achieve the fairness in machine learning models. As a huge number of fairness measurements emerged recent years, I will mainly talk about the significant ones, e.g., demographic parity, equalized odds, counterfactual fairness. 

For this post, I want to motivate why studying fairness in machine learning is important and I will give an concrete real-world example to show the prevalence of unfairness decisions made my algorithms and another example to illustrate the subtlety in studying fairness.

### A Real Case
In 2014, Amazon tried to use machine learning algorithms to review the resume and score the applicants based on the recruitment data over the ten years. However, they soon spotted that the algorithm was not rating the candidates in gender-neutral way. Learning from the past data that men have been dominating the techonology industry, the algorithm treated words like "woman" as an indicator for score deduction. Soon, the team working this algorithm was discharged and the project was abandoned. This short-lived attempt to making decisions using algorithms proves to be not as impartial as people imagine and brought up real undesirable impact in terms of employment. Clearly, in this case, the training data is "poisoned" and this is very common in real world applications. Recent studies has listed this as one of the most important reason leading to unfairness.

### A Tricky Case
In 1973, UC Berkeley was sued for its gender bias against female applicants. From the statistics, the admission rate of female applicants is significantly lower than that of male applicants. See Table 1.
|       | Applicants | Admitted |
|:-----:|:----------:|:--------:|
|  Men  |    8442    |    44%   |
| Women |    4321    |    35%   |
Table: Table 1

However, if we look into the admission data for each department, then interesting thing happens. It appears that 6 out of 85 deparments are significantly biased against men, while only 4 deparments are significantly biased against women. The reason behind this, according to Bickel et al., is that women tended to apply for more-competitive departments with low admission rate.
This tricky case serves as a warning that we need to analyze fairness problems with great care and a superficial analysis can lead to very wrong conclusion. Reporting false unfairness, just as unfairness, is also undesirable. This admission example servers as an important test cast to justify if a new fairness measurement is appropriate. 