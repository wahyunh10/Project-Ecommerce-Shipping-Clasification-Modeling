# Project-Ecommerce-Shipping-Clasification-Modeling
 Data source : https://www.kaggle.com/prachi13/customer-analytics

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#project-overview">Project Overview</a>
    </li>
    <li><a href="#background-and-problem">Background and Problem</a></li>
    <li><a href="#exploratory-data-analysis">Exploratory Data Analysis</a></li>
    <li><a href="#data-processing">Data Processing</a></li>
    <li><a href="#modelling">Modelling</a></li>
    <li><a href="#business-recommendations">Business Recommendations</a></li>
  </ol>
</details>

## **Project Overview** 
• Stage 1 : We focus on Data Exploration, Exploratory Data Analysis, Business Insight and Visualization <br>
• Stage 2 : We focus on Data Cleansing and Feature Engineering <br>
• Stage 3 : And then on last stage, We focus Modeling and Evaluation <br>

Overall Project : <br>
• Seek insight from the dataset with Exploratory Data Analysis <br>
• Performed data cleansing, data processing, data engineering to prepare data before modeling <br>
• Built a model to predict whether the shipping deliveries will be received late or on time by the customers <br>
• Developt  recommendations & benefit analysis based on insights and model prediction 
<br>

## **Background and Problem**
An international e-commerce company that sells electronic products want to discover key insights from their customer database. Currently, most of the shipping deliveries are late. 
<br>

## **Exploratory Data Analysis**
| Variable | Type | Definition | Example |
| ----------- | ----------- | ----------- | ----------- |
| ID | Nominal | Customer ID Number | 10, 15, 10995, 10996
| Warehouse_block | Nominal | Warehouse to Store the Product | A, B, C, D, F
| Mode_of_Shipment | Nominal | Mode of Product Shipping | Flight, Road, Ship
| Customer_care_calls | Discrete | Number of Calls Made | 1, 2, 5, 6
| Customer_rating | Ordinal | Company Rating by Customers | 5: Best - 4: Better - 3: Neutral - 2: Bad - 1: Worst
| Cost_of_the_Product | Discrete | Cost of Product in US Dollars | 177, 216, 236, 182
| Prior_purchases | Discrete | Number of Prior Purchase | 3, 2, 6
| Product_importance | Ordinal | Product Importance Parameter | Low, Medium, High
| Gender | Nominal | Customer Gender | Male, Female
| Discount_offered | Discrete | Product Discount in US Dollars | 65, 10, 16
| Weight_in_gms | Continous | Product Weight in grams | 4953, 5676, 2171
| Reached.on.Time_Y.N | Nominal | Target Variable, 1: NOT reached on time - 0: REACHED on time | 1, 0

1. 59.7% of e-commerce shipping deliveries are late received by the customers (6.563 of 10.999 customers).
![image](https://user-images.githubusercontent.com/80570935/126962808-11ff1d40-e71b-4d71-b0ed-e561ae408e3a.png)

2. Ship & Warehouse F has the highest frequency of delivery. But it looks almost the same based on the percentage. There's an assumtion that the late is influenced by other factors.
![image](https://user-images.githubusercontent.com/80570935/126960264-5f61c973-91f9-4ab3-b1a3-ca4f236ec0a4.png)

3. Every product that gets a discount above 10 is confirmed Late. There is an assumption that this happens in specific months, but needs further checking. 
![image](https://user-images.githubusercontent.com/80570935/126960668-055ad318-7bd9-4674-a2c5-73211b8215e6.png)

4. Shipping delivery is confirmed late when the product weight is between 2-4 kg.
![image](https://user-images.githubusercontent.com/80570935/126961078-28049344-6c62-4168-b92e-c347c8b80930.png)

<br><br>
## **Data Processing**<br>
• Check missing & duplicate values<br>
• Remove outliers with z-score<br>
• Ordinal encoding for `Importance` column & feature encoding the rest of categorical columns<br>
• Select best features for modeling<br>
• Normalize & Standarize all selected features <br>
<br><br>
## **Modelling**<br>
• Split features & target<br>
• Split data into data train & data test<br>
• Train model with 5 different algorithm such as Decision Tree, Logistic Regression, Random Forest, XGBoost , KNN, & Lightgbm<br>
• Evaluate model with Accuracy, Precision, Recall, F1-Score and AUC and focus on AUC Score<br>
• Hyperparameter tuning<br>
• Select the best model<br>
<br><br>
## **Model Evaluation**
<br> 

<table>
  <tr>
    <th>Model</th>
    <th>Accuracy</th>
    <th>Precision</th>
    <th>Recall</th>
    <th>F1-Score</th>
    <th>AUC</th>
  </tr>
  <tr>
    <td>Decision Tree</td>
    <td>0.65</td>
    <td>0.72</td>
    <td>0.66</td>
    <td>0.69</td>
    <td>0.65</td>
  </tr>
  <tr>
    <td>Logistic Regression</td>
    <td>0.58</td>
    <td>0.58</td>
    <td>1.00</td>
    <td>0.73</td>
    <td>0.50</td>
  </tr>
  <tr>
    <td>lightgbm</td>
    <td>0.66</td>
    <td>0.76</td>
    <td>0.60</td>
    <td>0.67</td>
    <td>0.739</td>
  </tr>
  <tr>
    <td>KNN</td>
    <td>0.66</td>
    <td>0.78</td>
    <td>0.56</td>
    <td>0.65</td>
    <td>0.67</td>
  </tr>
  <tr>
    <td>Random Forest</td>
    <td>0.68</td>
    <td>0.82</td>
    <td>0.56</td>
    <td>0.67</td>
    <td>0.70</td>
  </tr>
  <tr>
    <td>XGBoost</td>
    <td>0.65</td>
    <td>0.71</td>
    <td>0.67</td>
    <td>0.69</td>
    <td>0.65</td>
  </tr>
</table>
Based on the model evaluation (AUC Score And Recall), We Choose Decision Tree algorithm .


## **Business Recommendations**<br>
### Short terms
• Add estimatedarrival time to assure the package arrived on time<br>
• Give credit points as a compensations to retain customer loyalty<br>
### Long terms
• Add more features to give more specific & accurate insights<br>
• Perform operational audit based on the insights<br>
