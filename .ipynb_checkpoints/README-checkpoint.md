# deep-learning-challenge
 
From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years.
As our main goal was to use the data to predict whether funding was used effectively or not we are able to delete the EIN and NAME columns from the data frame as they are not useful in prediction.
I then aggregated the data in the 'Application Type' and 'Classification' columns to combine "rare" categorical variables together in a new value called other in order to better train the model.
With the data cleaned, I set the 'Is Successful' column as the target so we can predict wheter an application would be used effectively, and the other 43 columns as features in the model.

My initial model two hidden layers and used RELU activation, it used all 43 of features as input, and the first layer used 80 neurons then the second layer 30. The third layer is the output layer using only one neuron for the out put and Sigmoid activation.
I trained the data using 70% of the data and 100 epochs, the training model was abel to get above 74% accuracy at some points and around 53% loss. Running this model with the remainin 30% of the data in the test set it returned 73% accuracy and 56% loss.

I tried three different approaches to optimize the training model but all three optimizations returned similar results.

The first optimization I added a third hidden layer and increased the number of neurons each layer had from 200 in the first, 100 in the second and 50 in the third. This model returned the results of accuracy: 72.89% & loss: 59.37%

The second optimization I added a dropout layer to the two hidden layers in the first model which prevents the neurons from overfitting by randomly deactivating neurons during each test so they dont over train. This model returned the results of Loss: 57.544%, Accuracy: 72.51%

The third optimization I used Leaky RELU activation instead of Relu as RELU sometimes runs into issues with neurons incorrectly parsing or dying, or getting stuck on 0, so Leaky RELU enhances some of these issues. The result of this model was Loss: 56.87%, Accuracy: 72.98%