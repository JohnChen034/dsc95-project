---
title: Home
layout: home
---

# Missingness guide

## Introduction

This page guide you through the types of missingness we learned in DSC80. The lecture slides already have
a good explantion on them, but if you want to have a more intuitive understanding, this page is for you.
It is important to understand this concept for project 3 and tests. I will mainly be focusing on NMAR since
(in my interpretation) it is the most difficult one to understand.

## Types of missingness

- Missing by design (MD).
- Not missing at random (NMAR). Also called "non-ignorable" (NI).
- Missing at random (MAR).
- Missing completely at random (MCAR).

## Missing by design (MD)

MD is the type of missingness that is not missing at random. It is missing by design.


> notes from lecture (I will use this to represent notes from lecture)):
> - the designers of the data collection process intentionally decided to not collect data in that column,
    because it can be recovered from other columns.
> - If you can determine whether a value is missing solely using other columns, then the data is missing by design.
    This confusion in design in one or several columns can be well understood by the other columns in the same
    dataframe.

> example from lecture:
> ![img.png](img.png)


note: I think MD is very easy to understand with class materials, I can add more if anyone think more is needed.

## Not missing at random (NMAR)

{I dont know if this makes sense, but here is my interpretation of it. Also incorporate my thoughts about in what level
of
understanding we should have in dsc80}

> The chance that a value is missing depends on the actual missing value!

This statement was very confusing to me at first by reading the text itself. so here are examples from class.

> Example: On an employment survey, people with really high incomes may be less likely to report their income.
>
> If we ignore missingness and compute the mean salary, our result will be biased low!
>
> Example: A person doesn't take a drug test because they took drugs the day before.
>
> When data is NMAR, we must reason about why the data is missing using domain expertise on the data generating
> process – the other columns in our data won't help.


Emmm, I still don't understand (me from the past): **If you say that "result can be biased low" because of the kind of
people that reports, isn't this just MAR? Then how would you differentiate NMAR and MAR?**

In the sense dsc80, I think instead of arguing in depth whether some missingness is truely NMAR or MAR, we are more
focused on
how you can differentiate a NMAR senario from a MAR senario. In short, we are looking at
> When data is NMAR, we must reason about why the data is missing using domain expertise on the data generating
> process – the other columns in our data won't help. (or reason about collecting more data)
> 
> Data is MAR if the chance that a value is missing depends on other columns, but not the actual missing value itself.

*Especially in project 3, we are more focused on whether you can correctly argue for NMAR and MAR.*

There isnt a big different in NMAR and MAR, they differentiate in the existence of dependencies on the
missingness in the dataframe. In MAR, we can use other columns to determine the missingness, but in NMAR, we can't. It
is important
to notice that at some level, NMAR and MAR are interchangeable based on the columns given by the dataframe. For example,
in the employment survey example, if we have a column that indicates the job title, we can use that column to determine
the missingness of the income column. In this case, the missingness is MAR. However, if we don't have that column (or
any relevant column), we can't determine the missingness of the income column. In this case, the missingness is NMAR.
In the drug test example, if we have a history of drug usage column, we can use that column to determine the missingness
of the drug test column. In this case, the missingness is MAR.

These are some easy domain knowledge to acquire, but in some cases, it is not that easy.
For example, In a voluntary survey, the decision to participate can be influenced by the very subject the survey seeks
to measure.
This can introduce a form of selection bias:

- Dissatisfied Employees: Those who are dissatisfied might be more inclined to participate as they see the survey as a
  platform to express their grievances. Conversely, they might also choose not to participate due to a sense of futility
  or disengagement.
- Satisfied Employees: Similarly, satisfied employees might be more likely to respond to show their positive
  experiences.
  However, they might also not participate if they feel there’s nothing to add or if they are complacent.
  These uncertainties can lead to one direction of bias due to the questions on surveys or some other factors.

These questions are always hard to answer, and a big part of resolution to this is incorporate these uncertainties into
survey design or imputation.

Aside from the ones we learned in class, there can be:

- Model-Based Imputation: These methods use statistical models (like regression models) to predict missing values based
  on the observed data. These models can be quite sophisticated, taking into account various factors that might influence
  the likelihood of missingness.
- Hot Deck Imputation: This method involves filling in missing values with observed responses from similar respondents.
  The 'similar' respondents are typically identified based on other variables in the dataset.

## Missing at random (MAR)

[working on it]

## Missing completely at random (MCAR)

[working on it]
    
    
