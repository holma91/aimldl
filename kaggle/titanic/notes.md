# Description

Create a model that predicts which passengers survived the Titanic shipwreck.

### Input

A file of passengers.

### Output

Predictions on whether the individual passengers survived or not.

### Data

We have tabular data, with the following **features**:

- PassengerId
- Survived
- Pclass
  A proxy for socio-economic status (SES). 1st upper, 2nd middle and 3rd lower.
- Name
- Sex
- Age
- Sib Sp
  number of siblings / spouses aboard the Titanic
- Parch
  of parents / children aboard the Titanic
- Ticket
- Fare
- Cabin
- Embarked

### Thoughts

So we get a training set and a test set. We should split the training set into "training-training set" and a validation set.

The features I think will matter the most are Pclass, Sex, Age and Cabin.
