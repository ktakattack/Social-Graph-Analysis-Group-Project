# Grandma’s Cookbook: An Analysis of Ingredients Associated with Cuisines
<em>This is a group project completed for Graph and Social Network Analysis at Kent State in Fall 2020.</em>
### By: [Anthony Bryson](https://github.com/AnthonyBryson), [Jacob Lebowitz](https://github.com/AugmentedMode), [Nicholas Potts](https://github.com/nickpotts3) and [myself](https://github.com/ktakattack)

### Project Overview
The goal was to provide a **network analysis** of a dataset. Our idea was to incorporate a recipe and ingredient dataset found on Kaggle (see sources). Through this particular dataset, we could see ingredient correlation by cuisine. This made us ask if forming a network on this dataset could help expand a users' palettes and showing connections to new cuisines based on their existing favorite foods.

There were two objectives: 
1. Essential ingredients for a favorite cuisine
2. Ingredient recommendation system--for example, if you like 3 types of cuisine, find top similar ingredients

To analyze the data a bit further, Python and Jupyter notebook were used. See our [Jupyter Notebook](./init-insights.ipynb).

### Data Cleansing
The Kaggle dataset we used provided cleaned data in JSON files. However, since we were doing some natural language processing, this required us to refine the data. For example, the dataset had "diced tomatoes" and "canned tomatoes." For the purposes of our project, we wanted to clean modifiers, so that became "tomatoes." 

### Machine Learning
Now that the data was prepared, we were able to being creating prediction about the relationships between ingredients in the dataset.

Using Word2vec algorithms, we formed a **model.** Once the model was built, we tested a recipe, "jalapeno chili", to see what ingredients were predicted. Below shows the corresponding ingredients, all with a greater than 90% prediction to the recipe.
![image](https://user-images.githubusercontent.com/30424160/104357442-31806080-54db-11eb-93c3-50eea2b1cc17.png)

Then we tested the inverse. We entered in two uncorrelated ingredients to see if the model would know they were unrelated. We thought "fresh pineapple" and "milk" would be a good test. The screenshot below shows that there was only about 6% correlation between those ingredients. <br>
![image](https://user-images.githubusercontent.com/30424160/104357458-380ed800-54db-11eb-85e7-a4c46d883a31.png)

Since we were confident in our model, we created it into a **network.** We plotted the network for the ingredient "romaine lettuce" and it returned an accurate network of correlation with other ingredients.
![image](https://user-images.githubusercontent.com/30424160/104357676-83c18180-54db-11eb-8ce4-880c53cc42ef.png)

### Web App
For the purposes of presenting our project to our instructor and class, we created a web app using Flask as our framework. Here's a screenshot of what our app looked like: 
![](https://user-images.githubusercontent.com/30424160/104356195-a5216e00-54d9-11eb-84e8-d4270f0093f4.png)
When the user types an ingredient in the search bar, it returns the most correlated ingredients in order from most to least. Also, the user could select one of the cuisine buttons at the top and see what ingredients were most associated with each cuisine.

#### Libraries used:
- Pandas
- Seaborn
- Matplotlib
- Numpy
- NTLK 
- Gemsim 
- Pickle 
- Scikitlearn

### Sources:
Kaggle ingredient dataset - https://www.kaggle.com/kaggle/recipe-ingredients-dataset?select=train.json
