Build a predictive model that answers the question: “
- what sorts of people were more likely to survive?
using passenger data (ie name, age, gender, socio-economic class, etc).

study the "data dictionary" on kaggle


We have tabular data (data is in the form of a table -> use DataFrame)

Do something about N/A values. (fill them with the mode or mean or 0 or whatever)


take the logarithm on columns with a long tail distro. log(0) = inf so we often need to add one to every value in the column.


replace non-numeric fields with numbers. create dummy variables?


create independent and dependent variables. Both should be pytorch tensors.

create a random coefficient for each column in the independent tensors. guess these coefficients are the weights?

we see that one column have much bigger values than the rest, which is a problem. make all columns contain numbers between 0 and 1.


multiply the weights with the independent variables, sum it along axis 1 and there we have our first predictions.
the sum of the values in a row in the product is a prediction.

create a loss function

split the data into training and validation sets



n(leaf) = 1
n(t(A, B)) = 1 + n(A) + n(B)


on(leaf) = 0
on(t(A, B)) = n(A) + n(B) - on(A) - on(B)


n(t(t(leaf, leaf), leaf)) = 1 + n(t(leaf, leaf)) + n(leaf)
                          = 1 + (1 + n(leaf) + n(leaf)) + 1
                          = 1 + 1 + 1 + 1 + 1 
                          = 5


on(t(t(leaf, leaf), leaf)) = n(t(leaf, leaf)) + n(leaf) - on(t(leaf, leaf)) - on(leaf)
                           = 3 + 1 - (n(leaf) + n(leaf) - on(leaf) - on(leaf)) - 0
                           = 3 + 1 - (1 + 1 - 0 - 0) - 0 
                           = 4 - 1 - 1 = 2

A = leaf, B = t(t(leaf, leaf), leaf)
on(t(leaf, t(t(leaf, leaf), leaf))) = n(leaf) + n(t(t(leaf, leaf), leaf)) - on(leaf) - on(t(t(leaf, leaf), leaf))
                                    = 1 + 5 - 0 - 2
                                    = 4


                                    