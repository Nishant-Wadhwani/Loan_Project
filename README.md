# Loan_Project
This project consists of two approaches trying to classify and predict whether or not the borrower paid back their loan in full, first approach inculcates the Random-Forest Classification Machine-Learning model while another includes a deep-learning classification neural network model. We have taken a large dataset containing around 4-Lakh entries for consideration so that we can compare the two models properly and able to perform descriptive and inferential analysis. 
For this project, we will be exploring publicly available data from LendingClub.com. Lending Club connects people who need money (borrowers) with people who have money (investors). Hopefully, as an investor, you would want to invest in people who showed a profile of having a high probability of paying you back. 

We will try to create a model that will help predict this.  The lending club had a very interesting year in 2016, so let's check out some of their data and keep the context in mind. This data is from before they even went public.  We will use lending data from 2007-2010 and be trying to classify and predict whether or not the borrower paid back their loan in full. LendingClub is a US peer-to-peer lending company, headquartered in San Francisco, California. It was the first peer-to-peer lender to register its offerings as securities with the Securities and Exchange Commission (SEC) and to offer loan trading on a secondary market. LendingClub is the world's largest peer-to-peer lending platform.


For this particular dataset, a decent amount of exploratory data analysis and data pre-processing needs to be done, along with feature selection engineering. This will help us to enhance our results as well as help us to improve our accuracy. While working with the deep-learning model, the number of neurons can be equal to the number of features involved after feature engineering and hidden-layers can be used according to your choice. For the activation function, we are using 'relu', loss function as binary-cross entropy, and optimizer as adam. And before using random-forest classification, we will aslo use decision trees to get the importance of the ensemble trees and it's role in random-forest classification in order to improve the accuracy, to decorrelate some of the unuseful features, bagging and to avoid over-fitting. And for deep-learning model, we will be adding drop-out layer too in order to avoid over-fitting of data as well as data leakage.

After performing descriptive statistics, predictive and inferential analysis, we can compare these two by measuring accuracy, precision,recall, and f1-score. We will also predict a class for new data using these two following models so that one can get the idea of accuracy and other parameters.


  Here are what the columns represent:  
0	loan_amnt	The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.
1	term	The number of payments on the loan. Values are in months and can be either 36 or 60.
2	int_rate	Interest Rate on the loan
3	installment	The monthly payment owed by the borrower if the loan originates.
4	grade	LC assigned loan grade
5	sub_grade	LC assigned loan subgrade
6	emp_title	The job title supplied by the Borrower when applying for the loan.*
7	emp_length	Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.
8	home_ownership	The home ownership status provided by the borrower during registration or obtained from the credit report. Our values are: RENT, OWN, MORTGAGE, OTHER
9	annual_inc	The self-reported annual income provided by the borrower during registration.
10	verification_status	Indicates if income was verified by LC, not verified, or if the income source was verified
11	issue_d	The month which the loan was funded
12	loan_status	Current status of the loan
13	purpose	A category provided by the borrower for the loan request.
14	title	The loan title provided by the borrower
15	zip_code	The first 3 numbers of the zip code provided by the borrower in the loan application.
16	addr_state	The state provided by the borrower in the loan application
17	dti	A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LC loan, divided by the borrower’s self-reported monthly income.
18	earliest_cr_line	The month the borrower's earliest reported credit line was opened
19	open_acc	The number of open credit lines in the borrower's credit file.
20	pub_rec	Number of derogatory public records
21	revol_bal	Total credit revolving balance
22	revol_util	Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.
23	total_acc	The total number of credit lines currently in the borrower's credit file
24	initial_list_status	The initial listing status of the loan. Possible values are – W, F
25	application_type	Indicates whether the loan is an individual application or a joint application with two co-borrowers
26	mort_acc	Number of mortgage accounts.
27	pub_rec_bankruptcies	Number of public record bankruptcies


Results Obtained:-
1. Deep-Learning Classification model with Dropout Layer:-
          precision    recall  f1-score   support

           0       0.98      0.44      0.61     15658
           1       0.88      1.00      0.93     63386

    accuracy                           0.89     79044
   macro avg       0.93      0.72      0.77     79044
weighted avg       0.90      0.89      0.87     79044

2. Decision-Trees Classification Model :-
            precision    recall  f1-score   support

           0       0.56      0.60      0.58     15658
           1       0.90      0.89      0.89     63386

    accuracy                           0.83     79044
   macro avg       0.73      0.74      0.74     79044
weighted avg       0.83      0.83      0.83     79044

3. Random-Forest Classification Model, with 300 decision trees:-
            precision    recall  f1-score   support

           0       0.97      0.45      0.61     15658
           1       0.88      1.00      0.93     63386

    accuracy                           0.89     79044
   macro avg       0.92      0.72      0.77     79044
weighted avg       0.90      0.89      0.87     79044


Hence, we can see that, Random-Forest Classification Model and Deep-Learning Model has accuracy of around 89% that seems fine, this is due to because of the biasness present in the data, note that number of people who have paid their  amount are very large as compared to people who haven't paid, that's why we are getting this much accuracy. Note Decision-Tree is getting 83% accuracy which is okayish in this case since we already know that 80% of the people have paid the full loan amount as seen during exploratory data analysis.
