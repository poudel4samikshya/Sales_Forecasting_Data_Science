<head>
<p>Samikshya Poudel, Michael Ipri, Jack Trimboli</p>
<p>Dr. Pantelis</p>
<p>CS 301-101</p>
<p>November 28th, 2021</p>
<h1><b>CS-301 Course Project: Predicting Future Sales</b></h1>
<h4><a href="https://www.youtube.com/watch?v=DdDv1JUjPcE">Video Presentation Link</a>
<h4><a href="https://colab.research.google.com/drive/1MPDH9xI4NoBybuRofFlF04n_F_2AxKlz?usp=sharing">Google Colab Link</a>
	
<h2><b>Abstract:</b></h2>
	</head>
		
<p>Our problem was a prediction or forecasting problem. Our idea was taken from kaggle, and it deals with forecasting future sales based on previous sales data. Specifically we are given daily sales data for different shops and products, some information included is the product price and how many units were sold per day. The data runs from January 2013 to October 2015. We are then asked to predict the monthly item count or the number of units sold per month. Our approach was to use the given data and  and fit it into a model. The thing we are interested in finding is the number of items sold per month. We find this in two different ways. First we find the total number of products sold per month for each store regardless of the product. Second we find the total number of products sold per month for each product regardless of the shop. These two values are the key results. The final thing we do is get a predicted y value or y hat and compare it to the actual y value. The dataset in kaggle does not have y values to compare with predicted y values, in order to solve this we split the training dataset given into 80/20. This way we can use 80% of the data to train the model and 20% of the data to test our model. Now we have a table consisting of actual y values, and a y hat or predicted y value.</p>


<h2><b>Introduction:</b></h2>
	<p>For our project, we were presented with the issue of needing to forecast the total amount of products sold on a monthly basis for all shops in a provided test set. In summary, we achieved this by using python3 libraries to programmatically prepare our test dataset to match our training dataset. Once complete, we fed our training data to our Random Forest Regression model. This allowed the Random Forest Regressor to form decision trees which it then used to make sales predictions when analyzing our test dataset. As a result, we were able to create a diagram of projected monthly product sales for the test data.</p>
 	<p>This issue is extremely important in today’s society because it impacts both businesses and individual citizens. For businesses, sales forecasting algorithms are crucial for understanding what future profits will look like. This affects important business decisions such as what products a business offers, how much staff that business may need, if layoffs are necessary, and much more. For citizens who are not involved in owning a business, this affects what investments they might make based on what products are projected to sell well. This is becoming more and more relevant as investment apps increase in popularity and more citizens become involved in trading.</p>
	
<h2><b>Related Work:</b></h2>
	<p>One of the benefits of using data from Kaggle was the ability to draw inspiration from individuals who worked with the same data as us. By reading through the discussion pages, we were able to find a wealth of documentation which helped us gain insight on how others decided to manipulate the data we were using. One post entitled ‘Sales Prediction- Regressions and Deep Learning’, written by Pralabh Poudel was particularly helpful. This post helped us better understand what the data actually represented and how to manipulate the data for use in our own research. This ultimately drove our decision to use the Random Forest Regression algorithm. This was because no one else had documented the use of this algorithm for this problem, and we were eager to see the data visualized in a new way.</p>
	<p>Our reference material was not just limited to Kaggle, however. We found a great resource article on the Random Forest Regression algorithm on gitconnected.com, which gave us more insight on how the algorithm utilizes decision trees to make predictions. Additionally, we used the documentation on SciKit-learn.org to learn more about how to use their open source python libraries to manipulate the data programmatically. This was especially helpful because it removed much of the legwork required to apply the algorithm to our dataset.</p>
	
<h2><b>Data:</b></h2>

<p>At the start of our experiment we had a set of files which we received from Kaggle containing a test and training dataset, as well as other chunks of raw data containing information such as product and shop information. Our training data came from a file named ‘sales_train.csv’ and was used to train the model we created. Specifically, this file contained daily historical data from January 2013 to October 2015. One issue we initially ran into was that the training dataset contained more fields than the test dataset:</p>
<table>
<tr>
  <th>
	  Test
  </th>
  <th>
	  Sales_Train
  </th>
</tr>
<tr>
  <td>
    <ul>
      <li>ID</li>
      <li>Shop_ID</li>
      <li>Item_ID</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>Date</li>
      <li>Date_Block_Num</li>
      <li>Shop_ID</li>
      <li>Item_ID</li>
      <li>Item_Price</li>
      <li>Item_Cnt_Day</li>
    </ul>
  </td>
</tr>
</table>
 <p><cite><i><small>*Above shows the two datasets and the features that each one initially holds*</small></i></cite></p>
<p>In order to make the test data comparable to the training data, we had to pre-processing on the test data. First we tried taking some information from the training dataset and adding it to the test dataset based on the matching IDs of each item. However this resulted in more issues and inaccurate results. To solve this issue we split the ‘sales_train.csv’ file into two parts. The first part consisting of 80% of the data will be used for training, and the second part 20% was used to test the model. This was done with the permission of Professor Pantelis. This process was necessary because when making our  model, we need to allocate our training data into X and Y training sets where X represents the important features and Y represents the values that should be predicted. By splitting the ‘sales_train.csv’ file we are able to guarantee that the training data and test data will be formatted the same and we will have the exact Y values to compare our predictions to. Another bit of preprocessing we did was change the item_cnt_day value to item_cnt_month since we are trying to predict item sales per month instead of daily sales, it was necessary to change this value.</p>

<h2><b>Methods:</b></h2>

<p>The approach we took to solving the problem of predicting future sales was to use Random Forest Regression. In the article “Random Forest Regression” by Chaya Bakshi, the author talks about Random Forest Regression and gives us a definition. The text says, “Random Forest Regression is a supervised learning algorithm that uses ensemble learning method for regression. Ensemble learning method is a technique that combines predictions from multiple machine learning algorithms to make a more accurate prediction than a single model” (Bakshi). In this case a random forest uses multiple trees to make a better prediction. We think this is the best approach because Random Forest Regression is useful when you have many different features or pieces of data. Random Forest Regression is perfect for us because we have many different features, and do not want to be limited in the number of features we can use when building our model, training our data, and making predictions.
 We did consider alternative approaches, one in particular was facebook prophet. We liked the prophet's model a lot. The one drawback to the prophet model was that it limited the amount of features allowed in order to train the model. This for us was a big problem. We were given a lot of features for each piece of data and we wanted to take full advantage of the data we were given as this would help us make the best prediction, this is why Random Forest Regression is the better option compared to facebook prophet.</p>
<p>To go into more detail about our specific approach using Random Forest Regression we split the problem into two different problems. We are trying to predict the item count per month for each product at each store. To do this we first predict item count per month for each store. This is regardless of the product. Then we predict item count per month for each product, regardless of the store. These are two halves to the prediction we are trying to make. We use this to then predict the item count per month of each product at each store. This then gets compared to the actual y value. We now have a table of y hats or predicted y’s and actual y values.</p>

<h2><b>Experiments:</b></h2>
	<p>After we finished preprocessing our data, we were ready to start creating our model. As stated in the ‘methods’ section. We achieved this in python code using a library called sklearn. This gave us access to the Random Forest Regressor, which performs the legwork of actually implementing the algorithm in code. This allowed us to easily feed 80% of our sales_train data to the model, effectively training it to accurately predict the items sold each month. Using our test data, we performed trials to verify that the regression model was working properly. After confirming this, we stored the results in a Dataframe in key value pairs, with each predicted item
count mapping to its corresponding shop ID. This initial result represented the predicted sales for each individual item, in each store:</p>
<img src="https://github.com/JackTrimboli/CS301-101-Group7/blob/main/docs/Res/img1.png" width="500" align="center"/>

<p>After arriving at this result, we knew we needed to find the total items sold for each shop, per month. By summing the items counts for each store. Below is the result we obtained:</p>
<img src="https://github.com/JackTrimboli/CS301-101-Group7/blob/main/docs/Res/img2.png" width="500" align= "center"/>

<p>The next thing we did was predict the item count per month for each item:</p> 
<img src="https://github.com/JackTrimboli/CS301-101-Group7/blob/main/docs/Res/img3.png" width="500" align= "center"/>


<p>Once again we find the total items sold for each item per month regardless of the shop they were sold from. We then get the result below:</p>
<img src="https://github.com/JackTrimboli/CS301-101-Group7/blob/main/docs/Res/img4.png" width="500" align= "center"/>

</p>The last thing we did is use the Random Forest Regressor to make a prediction about the number of items sold per month while taking into account the specific item and store. Before we were just looking at one of these factors now we are looking at both. This is the result we wish to obtain, and is our predicted y value or y hat. We then compare this value to the actual y value which is given in the sales_train data and since we split the sales_train data 80/20 into training and test data respectively it makes it very easy to compare our predictions to the ground truths.</p>
<img src="https://github.com/JackTrimboli/CS301-101-Group7/blob/main/docs/Res/img5.png" width="500" align= "center"/>



<h2><b>Conclusion:</b></h2> 
	<p>Our key results are found in the data table directly above and it shows the accuracy of our model. It is easy to tell that our model could have been a lot more accurate. We were able to observe that as the actual y values increased in value our model’s performance decreased. Overall our model was able to predict the future sales of products to some degree. Upon further analysis, we found various potential ways to improve our accuracy. The most notable of these strategies was to use the K fold cross validation method. This method would maximize the accuracy by providing a range of accuracies that our data set can give across different training and testing data. By doing this, we could pick the right training and testing data from the dataset, which would lead to more reliable predictions. However, due to technical limitations, our local machines struggled to complete this task even with many hours of processing.</p>



<hr /> 


<h3 align="center"><b>Works Cited</b></h3>
<ul>
<li>Bakshi, Chaya. “Random Forest Regression - Level Up Coding.” Medium, 9 June 2020, levelup.gitconnected.com/random-forest-regression-209c0f354c84.</li>
<li>“Sklearn.Ensemble.RandomForestClassifier.” Scikit-Learn, scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html. Accessed 28 Nov. 2021.</li>
<li>Poudel, Pralabh. “Sale Prediction- Regressions and Deep Learning.” Kaggle, 12 Nov. 2021, www.kaggle.com/pralabhpoudel/sale-prediction-regressions-and-deep-learning.</li>
<li>Lakshmanan, Swetha. “How, When, and Why Should You Normalize / Standardize / Rescale Your Data?” Towards AI — The World’s Leading AI and Technology Publication, 29 May 2020, towardsai.net/p/data-science/how-when-and-why-should-you-normalize-standardize-rescale-your-data-3f083def38ff.</li>
</ul>
