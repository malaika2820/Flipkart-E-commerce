# Flipkart-E-commerce
Natural Language Processing on Flipkart data-set to predict category of a product.

### Task :
Using the given dataset, predict the category of a given product based on its description. The task is divided into five main subtasks - 
1. Cleaning the given dataset
2. Visualizing patterns in dataset
3. Using a ML model to predict class of each data point
4. Measuring accuracy of the model
5. Ideas to improve the accuracy of the model

The product category tree containts numerous categories for each product, so for each product the primary category must be figured out before predicting it.

### Link to Dataset :

https://docs.google.com/spreadsheets/d/1pLv0fNE4WHokpJHUIs-FTVnmI9STgog05e658qEON0I/edit?usp=sharing

### About the Dataset :
The dataset consists of **20,000** data points and there are **15** columns namely 'uniq_id', 'crawl_timestamp', 'product_url', 'product_name', 'product_category_tree', 'pid', 'retail_price', 'discounted_price', 'image', 'is_FK_Advantage_product', 'description', 'product_rating', 'overall_rating', 'brand', 'product_specifications'.

Since description is the main category, data points which have null values for this column are removed. So the total count of data points is 19998.

### Solution

**1. Cleaning the data**

The preprocessing of the dataset involved several tasks such as - finding out primary category from product category tree, removing columns which did not contribute to determining  the class of a data point and bringing the data to a form able to be used by an algorithm. 

The columns removed from the dataframe were :
- product_rating
- overall_rating 
- crawl_timestamp
- product_url
- uniq_id
- retail_price
- discounted_price
- is_FK_Advantage_product
- image

After reducing the category tree to its primary category, there were **33** categories found, **Clothing** was the most frequent category of products and **Automation & Robotics** was the least frequent. 

Once the data was cleaned and all the unnecessary items removed, text preprocessing was the next step.

Text Processing included :
1. Removing punctuation
2. Converting each sample into tokens
3. Removing the stop words
4. Preprocessing Data : Using a Lemmatizer
5. Saving the cleaned data

These steps ensured that the data being fed into the model was concise and consistent, and contained the data suitable to make a prediction. 

**2. Visualizing Data**

Using bar graphs and histograms, we visualize the counts for distinct values in each of the columns. These visaulizations help us better understand the classification in the dataset. Using the "value_counts() function it is easy to calculate the count of each value in each column, and they can be plotted directly.

**3. Training the Model**

The data is now ready to be fed into the algortihms to be trained. Since this dataset has 33 main classes, so the algorithms mostly used for multiclass classification are :
- K-Nearest Neighbour
- Logistic Regression
- Support Vector Machine
- Decision Trees

Before the data can be fed into the models, it is essential to note that Machine Learning models do not directly work with text. They need to be converted into vectors of numbers. So the next step was converting text into vectors. For this TF-IDF(Term Frequency - Inverse Document Frequency) method is used.

The data once in the form of vectors is split into testing and training sets. 70% of the data is used for training and the rest is used for testing the model.

**4. Measuring performance of Algorithms**

The Algorithms used had the following accuracies :

- K-Nearest Neighbour

The accuracy noted was 0.8405 or 84.05%.

- Logistic Regression

The accuracy noted was 0.65716 or 65.716%.

- Support Vector Machine

The accuracy noted was 0.417 or 41.7%.

- Decision Trees

The accuracy noted was 0.4133 or 41.33%.

The highest accuracy was given by the K-Nearest Neighbour algorithm. Varying the parameters, such as value of n also improves the accuracy of the model.

**5. Improving the accuracy of the model**

There are several ways to improve the accuracy of the model
1. Changing the algorithm used

The first algortihm used was Logistic Regression, and even after varying the paramters there was not much significant change in accuracy. So other algorithms such as SVM, Decision Trees and K-nearest Neighbour was tried out, and accuracy for each was recorded. There are several other algorithms such as Naive Bayes, Random Forest that can also be tried out.

2. Including more data

The best way to increase accuracy is to provide more data to the models. These models are data centered and hence, more data can improve their perfomance significantly. Changing the ratios of test and training set may also contribute towards increasing the accuracy.

3. Including more columsn to determine the category

Description is the only attribute used to determine the category, other columns such as "pid", "brand", "product name" can also be added. This will definitely contribute towards increasing the accuracy of the model, as these attributes include word/words which point towards a particular category. 


