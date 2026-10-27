ECON 3916 Problem Set 2: The Survey That Wasn't Random
Question
The product team saw satisfaction rise from about 3.6 to 4.3 after an onboarding redesign and wanted to say the redesign worked. I used a simulation where the real population improvement is only about 0.10 points so I could check what the survey was actually measuring.
What I did
I simulated 50,000 users before and after the redesign with engagement, support ticket status and satisfaction. Then I added a response process where happier users were more likely to answer and that selection became much stronger after the redesign.

I used a manual bootstrap and scipy bootstrap to measure uncertainty, checked interval coverage with repeated surveys, ran a two sample test with an effect size, and did power calculations. I also tested inverse probability weighting using engagement and support ticket status.
Main result
The observed survey means are about 3.59 before and 4.31 after, but the true population means are about 3.29 and 3.39. The survey therefore makes a small real improvement look much larger because the people who answer after the redesign are much more selected by satisfaction.

The main lesson is that more responses do not solve a biased response process. A better design would survey a random sample of users with the same collection process before and after the redesign.
