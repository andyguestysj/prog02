---
title: Assessment Exercise 3
permalink: /docs/assess-ex-3/  
---

[Video Brief]()  

This exercise is a little different. You don't get a started project to work from. You should create a new project yourself and then follow the instructions below. 

## Bank Accounts

1. **Standard Account**

Make a class for a standard bank account, following the instructions below. NB money can only be withdrawn if it is available in the account.  

* Create a class called `BankAccount` which represents a bank account, having as attributes: `accountNumber` (integer type), `name` (name of the account owner as string type), `balance`.
* Create a **constructor** with parameters: `accountNumber`, `name`, `balance`.
* Create a `deposit()` method which manages the deposit actions.
* Create a `withdrawal()` method which manages withdrawals actions.
* Create an `bankFees()` method to apply the bank fees with a percentage of 5% of the balance account.
* Create a `display()` method to display account details.

2. **Savings Account**

Make a new class that follows the rules for the standard account except the bank fees are 0% (i.e. there are no fees) and there is a £100 withdrawal limit.  

* create a `accrueInterest()` method (for savings account) which adds 5% interest to the balance.

3. **Overdraft**

Add an `addOverdraft()`  method which adds an overdraft limit (passed as a parameter). A user with an overdraft can withdraw money until they run out of overdraft. A savings account cannot have an overdraft.

### Marking

25 marks are available for this exercise. This breaks down as follows.

1. Bank Account - 10 Marks
2. Savings Account - 5 Marks
3. OVerdraft Changes - 10 Marks

### Submission

Your project should be uploaded to your gitlab account and you should submit a link to the gitlab project, alongside the rest of the assessment, through moodle, by 12 noon 16/05/22.  