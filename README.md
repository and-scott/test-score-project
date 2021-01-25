# Project 1: Standardized Test Analysis

## Overview

You might wonder if you're ready to start doing data science. While you still have **tons** to learn, there are many aspects of the data science process that you're ready to tackle. Project 1 aims to allow you to practice and demonstrate these skills.

For our first project, we're going to take a look at aggregate SAT and ACT scores and participation rates in the United States. We'll seek to identify trends in the data and combine our data analysis with outside research to address our problem statement.

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

## Problem Statement

My project is going to analyze the impact of educational spending on college entrance exam testing outcomes on a per state basis.
This aims to help educators, lobbyists, and state budget planners make more informed decisions when asking whether increased state investment is helpful or necessary.
I hypothesize that increased educational spending on a per student basis will have a strong positive relationship with testing outcomes.


## Datasets

### Provided Data

Of the 10 datasets included in the (./data/) folder for this project I chose to work with the following:

* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))

### Additional Data

This data was made from a state education budget spreadsheet. Since I only needed to be concerned with education budget, I was able to pull education spending per student by state so I can use that as my proxy for educational spending.
* [`expenditure.csv`](./data/expenditure.csv): 2018 per student budget spending state ([source] handcrafted from (https://www.governing.com/finance/Education-Spending-Per-Student-By-State.html)

### **Data Dictionary:**

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|2018, 2019 ACT and SAT|The name of the state to which the test scores correspond|
|participation|float64|2018, 2019 ACT and SAT|The participation rate for test takers within the state|
|composite|float64|2018, 2019 ACT|The average score across all sections of the ACT within the state| 
|total|int64|2018, 2019 SAT|The average sum of the scores between both sections of the SAT within the state|
|perstudentspending|float64|2018, 2019 ACT and SAT|The investment by the state into education per student|


### Analysis

Surprisingly investment on a per student basis does not correlate with testing outcomes as heavily as I would have suspected. The return on investment between the SAT and ACT is somewhat staggering, however, as the ACT outcomes do tend to increase as state investment increases with a corellation score of around .4, compared to the negative correlation score between the SAT and investment of around -.2. Out of surprise I attempted to see if I could explain this through diminishing returns on investment.To do this I used an outperform feature which would just look at the difference between the states investment compared to the national average. This did not correct anything, but did show that increased investment over the national average wouldhelp ACT scores, while it would actually do nothing for SAT scores.

So what can we see from this data? Very little relationship between per student spending and participation, but even more astounding is the very clear negative relationship between participation and test outcomes. This could suggest that students that are eager would take the tests anyway, and they are outperforming, but the students that otherwise would not take the testbut by mandate are underperforming. This could make a great deal of sense as there are many different expectations at an individual level that might prohibit excellence on an exam. 


### Conclusions and Recommendations

While it is difficult to examine such complex individual hurdles that might lead to lower performance there are some
shortcomings in my own data, as well. I was only able to get perstudentspending from a 2018 report, and since these scores are from 2018 and 2019, the data might be skewed. Additionally this perstudentspending is not specific to testing, it is generic budget spending, with no sub-categories which might be more specific and valuable to a states budget planners. It might be worth analyzing the differential in spending from a year-to-year basis and seeing that relationship to the testing outcomes. My other recommendations would not necessarily be to stop enforcing testing mandates, as more participation is likely important for the good of the individuals future and therefore the states. However, after careful consideration of alternate pathways into careers, a state might consider that college entrance exams might not be necessary if there is a robust infrastructure for careers outside of higher education. There is a lot more to look at, and purging the data of subcategories like the individual components of the test scores might have warranted slightly different conclusions. Such as analyzing whether math scores or verbal scores were indivudally affected by investment, moreso than the total. This could give us a future glimpse into whether
the subcategories of educational spending are worth a look.

Overall, this data does suggest that keeping up with the national average of per student spending is a worthy goal and one that will ensure at the very least that the students are given adequate opportunities to test well, with the exception of if the state is more focused on the ACT, as there is a moderate relationship between increased spending beyond the national average and student outcomes.
