# Case-study-with-random-forest
# Charles Book Club — Tree Classification & Random Forest (Florence Offer)

This project uses the **Charles Book Club** case study to build predictive models that help the club **target customers most likely to buy the “Florence” offer**, reducing wasted mailings while minimizing misclassification (false positives vs. false negatives).


## Goal  
Predict which customers are likely to buy the **Florence** offer, so the book club can **target promotions more effectively**.  
The model classifies each customer as **Florence = 1 (buyer)** or **Florence = 0 (non-buyer)** based on past behavior (book interests, spending, recency/frequency, etc.).

## Models Tested  
- **Decision Tree (rpart):** default tree, cutoff tuning, and pruning  
- **Random Forest:** tested different `mtry` values, cutoff tuning, and class weighting

## Evaluation Metrics  
- **Accuracy:** overall percent correct  
- **Sensitivity (Recall for buyers):** how many real buyers we correctly identified  
- **Specificity:** how many non-buyers we correctly avoided

## Key Takeaway  
Because buyers are **rare**, some models get **high accuracy** by predicting **almost everyone as non-buyer**.  
When we adjusted cutoffs/weights to catch more buyers, it increased **false positives** (mailing to people who won’t buy).

## Conclusion 
Tree + Random Forest were **not optimal** under these settings (either low sensitivity or overfitting). Next steps:  
- Try **Logistic Regression** (interpretable and strong baseline for response prediction)  
- Try **Boosting models** (XGBoost/LightGBM) or **Neural Networks**  
- Choose the classification cutoff using **business profit/cost** (mailing cost vs value of a buyer), not just accuracy  

