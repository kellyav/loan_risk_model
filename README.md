# Modelling risk of loan default based on comsumer credit
Use logistic regression and decision trees to measure risk associated with loans and associated credit. 
Lessons on financial models from DataCamp. Information below:


## What is loan default?
The area of credit risk modeling is all about the event of loan default. Now, what is loan default? When a bank grants a loan to a borrower, which could be an individual or a company, the bank will usually transfer the entire amount of the loan to the borrower. The borrower will then reimburse this amount in smaller chunks, including some interest payments, over time. Usually, these payments happen monthly, quarterly, or yearly. Of course, there is a certain risk that a borrower will not be able to fully reimburse this loan. This results in a loss for the bank.

## Components of expected loss (EL)
The expected loss a bank will incur is composed of three elements. The first element is the probability of default, which is the probability that the borrower will fail to make a full repayment of the loan. The second element is the exposure at default, or EAD, which is the expected value of the loan at the time of default. You can also look at this as the amount of the loan that still needs to be repaid at the time of default. The third element is loss given default, which is the amount of the loss if there is a default, expressed as a percentage of the EAD. Multiplying these three elements leads to the formula of expected loss.

    EL= PD x EAD x LGD
where:

PD= probability of default

EL= expected loss

EAD= exposure at default

LGD= loss given default


## Information used by banks
Banks keep information on the default behavior of past customers, which can be used to predict default for new customers. Broadly, this information can be classified in two types. The first type of information is application information. Examples of application information are income, marital status, et cetera. The second type of information, behavioral information, tracks the past behavior of customers, for example, the current account balance, and payment arrear history. Let's have a look at the first ten lines of our dataset.

## The data
This data set contains information on past loans. Each line represents one customer and his or her information, along with a loan status indicator, which equals 1 if the customer defaulted, and 0 if the customer did not default. Loan status will be used as a response variable, and the explanatory variables are the amount of the loan, the interest rate, grade, employment length, homeownership status, the annual income, and the age. The grade is the bureau score of the customer, where A indicates the highest class of creditworthiness and G the lowest. This bureau score reflects the credit history of the individual and is the only behavioral variable in the dataset.

## CrossTable
For an overview of the data structure for categorical variables, you can use the CrossTable() function in the gmodels package. Applying this function to the home_ownership variable, you get a table with each of the categories in this variable, with the number of cases and proportions. Using loan status as a second argument, you can look at the relationship between this factor variable and the response. By setting prop r equals to TRUE and the other proportions listed here equal to FALSE, you get the row-wise proportions. Now, what does this result tell you? It seems that the default rate in the homeownership group OTHER is quite a bit higher than the default rate in, for example, the homeownership group MORTGAGE, with 17.5 versus 9.8 percent of defaults in these groups, respectively.
