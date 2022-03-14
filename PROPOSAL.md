
<h1>PROPOSAL CS301-101</h1>

<h2>Group 7 - Jack Trimboli, Samikshya Poudel, Michael Ipri</h2>

<h4>1. What is the problem that you will be investigating? Why is it interesting?</h4>
<p>
  For our project, we are presented with the issue of needing to forecast the total amount of products sold in every shop in a provided test set. We will do this using a dataset which contains daily historical sales data. We found this topic interesting because it provided us with an opportunity to create a robust model that can handle changes in our data, such as the list of shops and products. 
</p>
<h4>2. What reading will you examine to provide context and background?</h4>
<p>
 In order to provide a clear end goal to this project, we will be reading the documentation of other similar projects, as well as comparing their data and results to our own. Additionally, we will reference the discussion and code tabs from Kaggle, to provide insight on how others approached this issue. Lastly, we found an article that utilizes linear regression for similar sales forecasting issues. We will use this as inspiration when creating our own diagram. This is the current list of URLs which we plan to use:
  <ul>
    <li>https://www.academia.edu/43317073/An_Effective_Approach_for_Sales_Forecasting</li>
    <li>https://www.kaggle.com/c/competitive-data-science-predict-future-sales/discussion</li>
    <li>https://www.kaggle.com/c/store-sales-time-series-forecasting</li>
    <li>https://www.kaggle.com/c/competitive-data-science-predict-future-sales/code</li>
  </ul>
</p>
<h4>3. What data will you use? If you are collecting new data, how will you do it?</h4>
<p>
   We will be using data provided by kaggle. The data provided includes a training set and a test set. The training set is from January 2013 to October 2015. The test set is from November 2015. Also provided is some background information about the items, products, item categories, and shop categories.
</p>
<h4>4. What method or algorithm are you proposing? If there are existing implementations, will you use them and how? How do you plan to improve or modify such implementations? You don’t have to have an exact answer at this point, but you should have a general sense of how you will approach the problem you are working on.</h4>
<p>
  The current algorithm we plan to apply to our dataset utilizes random forest regression. There is an existing similar implementation which we have provided a link to in response to question 2. We plan to modify this implementation to fit our specific data, as well as address the primary issue we are presented with, which is allowing our algorithm to function properly despite changes in attributes such as the list of shops or products.
</p>
<h4>5. How will you evaluate your results? Qualitatively, what kind of results do you expect (e.g. plots or figures)? Quantitatively, what kind of analysis will you use to evaluate and/or compare your results (e.g. what performance metrics or statistical tests)?</h4>
<p>
  Our finished product will consist of two results: a linear regression which reflects our dataset, and a number which represents the total amount of products sold in every shop. We will also analyze how different variables impact the various possible outcomes. Lastly, we will compare our results with the projects and readings we previously mentioned in questions 2 and 4. 
</p>
