The model performs very well at predicting the next character of a word. Since both English and
French share a lot of alphabets in common and lots of words like ‘declaration’ are common for
both the languages, using this model to perform language prediction may not be the greatest
idea. A simple logistic regression model performs much better
The other approaches I have explored include: 
1) Hyper parameter optimization
2) Using simple lstm and stacked lstm
3) Classification using language labels – all tough in real world language labels may not
always be available
4) Early stopping using validation split
5) Calculating distance between language profile and document profile by generating
ngrams for different languages.
5 ways to improve the model:
1) Limiting batch size to a number less than 1000
2) Running it for an optimal number of epochs to avoid overfitting. This can be achieved to
through enabling early stopping on validation loss by setting the patience variable.
By Early stopping, the model stops training as soon as it stops learning.
3) Adding multiple lstm stacks.
4) Enabling stateful = True in lstm. This helps the recurrent model to reuse the internal
states and the model along with the internal states are used as initial states for the next
batch
5) The categorical_crossentropy as loss variable and rmsprop works as optimizer works
best along with softmax activation – this model gave the best ROC AUC score and
accuracy.