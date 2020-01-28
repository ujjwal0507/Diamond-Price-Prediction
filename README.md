# Diamond-Price-Prediction

## Introduction: The project deals with creating a multivariate regression in order to
calculate the price of the diamonds based on various factors like - carat, cut, color,
clarity, depth, table, x, y, z. A Deep Artificial Neural Network has been used in order to
accomplish the given task.
## Dataset: The dataset contains various factors like carat, cut, color, clarity, depth, price,
table, x, y, z. As we can see labels of the dataset, we need to predict the price of the
diamonds based on the remaining factors. The different factors being:
a. Carat: Weight of the diamond
b. Cut: Quality of the cut of the diamond
c. Color: The quality of the color of the diamond
d. Clarity: Categorical measure of the clarity of the diamond
e. Table: Width of the top of the diamond relative to the widest point
f. Depth: Total depth percentage of the diamond
g. X - Length of diamond in mm
h. Y - Width of diamond in mm
i. Z - Depth of diamond in mm
j. Price - Price of the diamond in US$
## Data Visualization:
### Description of the data: This step basically gives us mean, median, standard
deviation, first quartile and the third quartile, the minimum and the maximum of the
dataset of all the numerical features of a dataset.
Description of the dataset:

From the above description table we can see the different numerical parameters for all the
seven numerical features of the diamond in the given dataset. However, we need to notice
that x, y and z have their minimum values as 0, which is not possible for the given
scenario as it is the measure of dimension of the diamond and it cannot be zero. This
implies that there are a few incorrect samples inside the dataset.
### Heatmap of Correlation: This will give us the individual coefficient of correlation
between the different parameters. In the given scenario, we are only interested in
obtaining the correlation coefficient between the label and all the different features. A
correlation coefficient of 1 indicates a perfect direct proportionality between the two
parameters at test and -1 indicating a perfect indirect proportionality between the two
parameters at test. The closer the correlation coefficient be to zero, the less of an effect
one value will have on the other.

As we can see, the value of price highly depends on the carat(0.92), x(0.89), y(0.87),
z(0.87). Price does not have much of an effect by the depth or the table, although they
will have some contribution towards deciding the price. From the heatmap, we cannot see
the relation of price with the categorical factors like cut, color or clarity for which we can
plot a different graph.
### Dataset Cleaning: The next step in the preprocessing of dataset should be cleaning
the data,.i.e, removing all the incorrect data values from inside the dataset. As we can see
that the price of the diamond highly depends on the values of x,y and z, we cannot use the
median substitution which is a very popular and a useful method of replacing the null
data. After this, we try to calculate the number of samples having the values of x,y and z
as 0 which comes out to be 8, 7 and 20 respectively. Hence, from a dataset of roughly
54000 entries, we can easily remove 35 entries without having much effect on the dataset
and the derived model.

### Pairplot: Plot of all the numerical labels of the dataset against each other to check
what will be the effect of one on another.

As we can see from the graph, carat shows an exponential relationship or a logarithmic
relationship with price, depth and table show a linear discontinuous relationship
confirming our previous derivation of the correlation coefficient between the two. X, y
and z form a rather linear or an exponential relation with the price. Therefore, we have
visualized our data against all the numerical values.
### Categorical Data Visualization: Next we try to figure out the relation between the
price and the categorical factors independent of any other factor. In order to accomplish
this task, we use the technique called boxplot. Boxplot will give us an idea of the
maximum price, minimum price, first, second and third quartiles of the price for that
particular category.
#### Price vs Cut:

As we can see, that the price is higher for a premium quality cut and lower for an ideal
quality cut.
#### Price vs Clarity:

The price is highest for clarities SI2 and I1 and lowest for categories WS1 and IF

#### Price vs Color:

The price is highest for J colored diamond and lowest for E colored diamonds.
As we can see from all three plots, the price of diamonds is not similar for all the
categories in dealing with categorical data points of this dataset. Therefore, we can
conclude that the categorical data points of cut, clarity and color have an impact on the
final price of the diamond.
## Data Preprocessing: Most of the features in the given dataset are numerical, however
there is a presence of three categorical features. This means that we will have to encrypt
the categorical data into some numerical form in order to feed it into the neural network.
For this, we will be using a technique called Softmax encoding, which is basically
encoding ‘n’ categories into bits of ‘n-1’ length. For example, if the four categories are
East, West, North and South, east can be encoded as 000, West as 100, North as 010 and
South as 001. Applying this technique on the 3 categorical features we have inside our
dataset, we be finally having a set of 23 features in order to predict the price of the
diamond.
## Neural Network: In this given scenario, I will be using a four layer deep neural network
with each of the four hidden layers having 100 neurons. The neural network will train for
100 epochs. There will be a 95 to 5 training and validation split of the dataset.
Results: Final Mean Squared Error -1381206.8905
Validation Mean Squared Error - 554719.6875
