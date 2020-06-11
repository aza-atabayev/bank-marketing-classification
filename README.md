# Bank Marketing (Classification)

# Problem Statement
## Context
Some banking institutions use marketing campaigns to make clients subscribe to their services. One of those services is the term deposit, which restricts withdrawing the deposit until the term ends. This deposit allows a higher flexibility in budget management because it doesn't affect the "liquidity coverage ratio" (the amount of money that the bank has to be able to pay instantly). Therefore, predicting and identifying customers who are prone to subscribe to term deposits is beneficial.

## Goal
The goal is to predict what type of customers will probably subscribe to term deposits by answering the following questions:
* What kind of customers usually subscribe to term deposits?
* By adjusting which marketing parameters banking insitution can increase chances of subscription?
* What type of customers marketing team should focus on for their next marketing campaign?

# Data Collection
## Data Source
I used "Bank Marketing" dataset from Kaggle provided by user Henrique Yamahata. [https://www.kaggle.com/henriqueyamahata/bank-marketing?select=bank-additional-full.csv]

## Data description
Attributes can be divided into the following groups:

### Client data:
* Age (numeric)
* Job : type of job (categorical: 'admin.', 'blue-collar', 'entrepreneur', 'housemaid', 'management', 'retired', 'self-employed', 'services', 'student', 'technician', 'unemployed', 'unknown')
* Marital : marital status (categorical: 'divorced', 'married', 'single', 'unknown' ; note: 'divorced' means divorced or widowed)
* Education (categorical: 'basic.4y', 'basic.6y', 'basic.9y', 'high.school', 'illiterate', 'professional.course', 'university.degree', 'unknown')
* Default: has credit in default? (categorical: 'no', 'yes', 'unknown')
* Housing: has housing loan? (categorical: 'no', 'yes', 'unknown')
* Loan: has personal loan? (categorical: 'no', 'yes', 'unknown')

### Current campaign
* Contact: last contact communication type (categorical: 'cellular','telephone')
* Month: last contact month of year (categorical: 'jan', 'feb', 'mar',…, 'nov', 'dec')
* Dayofweek: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
* Duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no').
* Campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

### Previous campaign 
* Pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
* Previous: number of contacts performed before this campaign and for this client (numeric)
* Poutcome: outcome of the previous marketing campaign (categorical:'failure','nonexistent','success')

### Social and economic context attributes
* Emp.var.rate: employment variation rate - quarterly indicator (numeric)
* Cons.price.idx: consumer price index - monthly indicator (numeric)
* Cons.conf.idx: consumer confidence index - monthly indicator(numeric)
* Euribor3m: euribor 3 month rate - daily indicator (numeric)
* Nr.employed: number of employees - quarterly indicator (numeric)

### Output variable
* y - has the client subscribed a term deposit? (binary: 'yes', 'no')













# Conclusion
## Insights
* Clients over 60  and under 23 are 3-4 times more willing to subscribe for term deposits than average client.
* It is 3 times more efficient to call to cellular number (15% efficiency) than to telephone number (5% efficiency).
* The longer the duration of the call the higher chance of client subscribing.
* To cover 93% of all clients that might subscribe to the term deposit, the minimum of 15 calls is required.
* Clients that subscribed for previous campaign offer are 3 times more likely to subscribe for term deposit than those who rejected previous offer.
*  With high importance the lower number of employees (nr.employed) the higher chance of client subscribing.
*  Clients are more likely to subscribe to term deposit in october.
*  The lower euribor 3 month rate (euribor3m) the higher chance of client subscribing.
*  If client was contacted in the previous campaign (pdays < 999), then client is likely to subscribe to current offer.
*  If client is contacted via cellular there is a slight boost in probability that client will subscribe to term deposit.

## Recommended actions (produced value)
*  Target clients over 60  and under 23 for small-scale campaigns because the have the highest probability of subscribing.
*  Make calls on cellular phones. (To cover 93% of all clients that might subscribe to the term deposit, the minimum of 15 calls is required.)
*  Target clients that were contacted in the previous campaign, despite the previous result.
*  Target clients with low euribor 3 month rate.
**OR**
*  Use this model beforehand (90% accuracy).