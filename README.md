# working_on_it
 MONOPRIX customer segmentation 


1. Clean the dataset 
_________________________

** Removed null values
** Removed observations with negative quantities 
** Converted Date into Date type 

2. Discover the dataset : EDA 
____________________________



? do i need to merge the 2 datasets : concatenated = pandas.concat([df1, df2]) DONE
? dayofweek : temp_data.loc[:, "Day of Week"] = data.InvoiceDate.dt.dayofweek

                     dayofweek_mapping = dict({0: "Monday", 
                         1: "Tuesday", 
                         2: "Wednesday" , 
                         3: "Thursday", 
                         4: "Friday", 
                         5: "Saturday", 
                         6: "Sunday"})
              temp_data["Day of Week"] = temp_data["Day of Week"].map(dayofweek_mapping)

   -> then see transactions by month, year, day of the week .. ( see notion for code ) DONE

*** unique customers per product VS unique customers DONE

______INSIGHT ON PRODUCTS :

-- 1 ..most populat Articles ( Article_ID vs total Quantity )  ---DONE
-- 2 ..Articles per Basket ID : frequency ( quantity ) of each article in Basket DONE
-- 3 ..total products purchased per 'rayon' nd per 'groupe' ( talkah f structure_ID )
-- 4 ..pourcentage of reorders per Article_ID 

=> most transactions happened in what period !!!!
=> most popular products !!! 1
=> most popular 'groups' !!! 3
=> most visited 'rayons' !!! 4


_____INSIGHT ON CUSTOMERS' behaviors :

-- how often a customer buys in a given unit of a lifetime 
-- RFM medeling ? => most profitable customers M | => customers with the most visits F | 


=> best times of sells !!!
_______________________________________________________________________________

**What i'm planning to do:


1. basket analysis : 
   if customer buys product A, he's most likely to buy product B as well 

NOTEBOOK __Market Basket Analysis : https://github.com/archd3sai/Instacart-Market-Basket-Analysis/blob/master/Data%20Description%20and%20Analysis.ipynb

/Lift : Increase in the sale of A when you sell B.
/Confidence : Likelihood that customer who bought both A and B. It is the ratio of the number of transactions involving both A and B and the number of transactions involving B.
/Support : Its the default popularity of an item. In mathematical terms, the support of item A is the ratio of transactions involving A to the total number of transactions.
/Apriori Algorithm: Apriori algorithm assumes that any subset of a frequent itemset must be frequent. Its the algorithm behind Market Basket Analysis. Say, a transaction containing {Grapes, Apple, Mango} also contains {Grapes, Mango}. So, according to the principle of Apriori, if {Grapes, Apple, Mango} is frequent, then {Grapes, Mango} must also be frequent.

2. Customer segmentation

3. Prediction : kmeans.predict ..

3. use collaborative system to recommend products to users 


-----------------------------------






For customer segmentation : she/he relied on ailes ( les rayons li ena lezmni nkharjhom ml structure_ID ) 

For deployment : customer lifetime prediction : https://github.com/mukulsinghal001/customer-lifetime-prediction-using-python/tree/main/model_deployment
                 Predict customer behaviour :

******** What is customer lifetime value ( CLV ) ?
  CLTV tell marketers, how much revenue they can expect from one customer over the course of the business relationship. The longer a customer continues to purchase from a company, the greater their lifetime value becomes.

_________________________________________________________________________

A cheatsheet for shell scripting : https://gist.github.com/LeCoupa/122b12050f5fb267e75f

I- Preparing the environment for the project : i need a UNIX shell, Anaconda and Git and Github 

---CONDA environment : 

  Conda has come to our rescue which allows us to create separate environments containing files, packages and their dependencies that are isolated from other environments.
 1. create a new env : conda create --name dswh_env
 2. conda activate dswh_env
 3. to deactivate the env : conda deactivate
 4. update the env after making changes to a specific file : conda env update --file /path/to/filename.yml --prune

Launching jupyeter notebook : simply write jupyter notebook in the path of your env ( conda prompt ) 
Export the env for 'with collegues sharing' ( collegues must have the same env characteristics so that the pjct can work on their computers as well )  : conda env export --file exported_environment.yml

--- Installing Git :



