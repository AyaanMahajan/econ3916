ECON 3916 — Problem Set 5: Right 93% of the Time

What I looked at
The lender's model says 93% accuracy, but around 93% of borrowers do not default. I simulated 8,000 loan applications and compared an approve-everyone baseline with logistic regression, LASSO, Ridge, and a random forest. I then checked the confusion matrix, ROC AUC, precision-recall AUC, model importance, and what different mistakes would cost the lender.
Main results
- The test set contained 2,000 applications and 6.95% defaults. Approving everyone gave 93.05% accuracy.
- Ridge logistic scored 94.40% accuracy and 0.598 PR-AUC. The forest scored 94.00% accuracy and 0.570 PR-AUC.
- LASSO removed 3 out of 4 deliberately irrelevant variables and kept all five genuine predictors.
- Under a 60% loss on missed defaults and a 10% cost on incorrectly declined good loans (8% interest plus 2% reputation), the test-set cost-minimising threshold was 0.201, not 0.50.
- On this simulated test set, that change reduced calculated mistake costs from about $1.16 million to $0.62 million. It still needs to be checked on newer data before any real use.
Phase 4 checks
I tested the forest versus Ridge on the same applications using McNemar's paired test. The discordant cases were b = 11 and c = 19, giving p = 0.201; the forest was not significantly better. I also compared the original probabilities with Platt scaling and isotonic calibration. Neither improved test-set Brier score, so the original 0.201 threshold remained the exploratory candidate. The notebook includes the AI prompt-and-reply transcripts and the verification work.
.
