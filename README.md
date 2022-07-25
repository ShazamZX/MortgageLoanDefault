MORTGAGE LOAN DEFAULT PREDICTION:


The data set mortgage is in panel form and reports origination and performance observations for 50,000 residential U.S. mortgage borrowers over 60 periods. The periods have been deidentified. As in the real world, loans may originate before the start of the observation period (this is an issue where loans are transferred between banks and investors as in securitization). The loan observations may thus be censored as the loans mature or borrowers refinance. The data set is a randomized selection of mortgage-loan-level data collected from the portfolios underlying U.S. residential mortgage-backed securities (RMBS) securitization portfolios and provided by International Financial Research (www.internationalfinancialresearch.org)

Key variables include:
◾ id: Borrower ID
◾ time: Time stamp of observation
◾ orig_time: Time stamp for origination
◾ first_time: Time stamp for first observation
◾ mat_time: Time stamp for maturity
◾ balance_time: Outstanding balance at observation time
◾ LTV_time: Loan-to-value ratio at observation time, in %
◾ interest_rate_time: Interest rate at observation time, in %
◾ hpi_time: House price index at observation time, base year = 100
◾ gdp_time: Gross domestic product (GDP) growth at observation time, in %
◾ uer_time: Unemployment rate at observation time, in %
◾ REtype_CO_orig_time: Real estate type condominium = 1, otherwise = 0
◾ REtype_PU_orig_time: Real estate type planned urban development = 1, otherwise = 0
◾ REtype_SF_orig_time: Single-family home = 1, otherwise = 0
◾ investor_orig_time: Investor borrower = 1, otherwise = 0
◾ balance_orig_time: Outstanding balance at origination time
◾ FICO_orig_time: FICO score at origination time, in %
◾ LTV_orig_time: Loan-to-value ratio at origination time, in %
◾ Interest_Rate_orig_time: Interest rate at origination time, in %
◾ hpi_orig_time: House price index at origination time, base year = 100
◾ default_time: Default observation at observation time
◾ payoff_time: Payoff observation at observation time
◾ status_time: Default (1), payoff (2), and nondefault/nonpayoff (0) observation at observation time


Project Summary:

The dataset contains loan records taken for 50000 customers at different timestamps, our goal is to take the timestamp at which the loan is either paid off or there is a default and try to use this new dataset to create a model to predict the chances of default in Mortgage Loans. We mainly use the values recorded during the origination time of the loan but for the values which are unavailable at the origination time we consider the first observed value. The full stepwise process and approach can be understood by going through the Working Notebook.

Result Analysis:

We have trained 2 models - XGBoost and Random Forest, both have achieved above 70% train and test accuracy (There's very minimal performance loss between train and test data showing that our model is very stable and there's no overfitting). The XGB has slightly outperformed the RF model. When it comes to the Classification measures, the models have shown a better precision than recall which stems from the fact that number of defaulting observations in the dataset were lesser than the number of good loans. However the models are highly stable and we can look to get a performance gain if we put in more data for training.