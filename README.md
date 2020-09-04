Data Preprocessing 

-There were duplicate entry in training data (train.csv), for same employee there were two inputs. So
I removed duplicate entries. There were 21 of them.

-And there were duplicates in remarks.csv, which were removed.

-To have access to unique employees I used “emp+comp” column which contains tuple containing
‘emp’ and ‘comp’.

Features
1. comp_code
mean encoding for categorical feature, here we have company
for each company comp_code = fraction of employees left the specific company
2. company_rating
Let’s say an employee in training data is from company ‘x’ and lastratingdate for employee
was ‘d’, this feature is average of rating given by employees of company ‘x’ in last 15 days
i.e. in [d-15,d] interval of time.
3. rating
This feature average of last 2 ratings of an employee.
4. num_remarks
number of remarks given by an employee

After using Logistic regression, SVM, Randon Forest I finally used XGB which gave maximum
public score.

Then for training I used XGB with GridSearchCV
