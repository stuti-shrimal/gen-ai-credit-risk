**AI-Powered Credit Risk Assessment Summaries**

**Motivation -** 
It's crucial to ensure that Machine Learning models are explainable i.e. the ability to understand why a model is providing a certain outcome based on the provided independent variables. The explainability aspect is especially important to establish trust with end-users for continued used of these ML models.

This becomes even more important for use cases such as credit risk assessments for lending, both due to regulation ensuring fairness and to promote better decision-making.
However, explainability comes at the cost of:
1) Several layers for credit approval
2) Leading to increase in average approval time
3) Resulting in slower customer onboarding

This project is a crude effort to use a LLM for introducing explainability to enable faster decision-making for credit risk assessment outcomes.

**Objective -** To create an agent that can provide end-users with a concise report about the rationale behind why a certain user has their loan_status as 0 (not likely to default) or 1 (likely to default).

**Steps -**
1) Create a logistic regression model trained on our labelled data to understand the coefficients for each of the variables
2) The coefficients are provided to the LLM as a prompt along with instructions on how we would want the fine-tuned model to provide reports for each of the users
3) The fine-tuned model is generated based on training data. We have used 10 samples to train the LLM
4) An output in the form of a crisp 100-word paragraph is generated for end-users

**Sample Output -** 
For user_id = 105, the loan_status is 1, indicating a predicted default on 
the loan. Despite a decent income, the loan amount is significant compared 
to their income, with a loan_percent_income ratio of 59%, suggesting
potential financial strain. Additionally, the person is relatively young, 
has a short employment length of 1 year, and does not own their home, which
may indicate a less stable financial situation. These factors, along with a
moderate credit history, contribute to the model predicting a higher risk of
default for this user.
