# Movie-recommendation-using-Apriori-algorithm
This project aims to perform fruitful recommendations on big data of movie names using Apriori algorithm with pyspark and no inbuilt libraries.

## Puzzle time:-
![This is an image](https://static.wixstatic.com/media/a27d24_9cfa03c3305d486586dd3d8a04129639~mv2.png/v1/fill/w_640,h_446,al_c,lg_1,q_85,enc_auto/a27d24_9cfa03c3305d486586dd3d8a04129639~mv2.png)

Are the questions valid? Even if Valid How much chance in reality would increase the sale?

## Solution :-
Yes they are valid and how they are valid or how much it would increase the sale is the interesting topic dealt by Aprirori algorithm.

### What is Apriori algorithm? :- 
It is one of the data mining algorithm in which rules of association are formed which are nothing but suggestions of arrangement in markets or movies that can be watched. ***(here apriori algorithm is used in later case)***.

## Methodolgy :- 
 ### Input files :- 
  2 textfiles in which one file denotes how many movies are watched by each user. And other textfile denotes what are these movies mapped to.
 * From these input files at first frequent itemsets of sizes 2,3,4 are created. This is based on number of most occurences of items, initially 2 sized items are created. From then 3 and 4 are created in iteration manner. ***(Note we calculate support in formation of frequent itemsets which will be used later)***.
 * Now association rules needed to be formed because these rules are suggestions depending on the situation where apriori algorithm is used.
 * Formation of rules are done by formula called confidence. The formulas are as below :- 
 ![This is an image](https://t4tutorials.com/wp-content/uploads/support-and-confidence-formula.webp).
 (Here support is used in calculating confidence with which we say validity of rule, if calculated confidence crosses threshold confidence then that rule is valid).
 
 *  In the above picture A->B is a rule. where A and B are items and this rule says if A is watched then B will be recommended. But in this project case as 2,3 and 4 frequent itemsets are formed we get left size of the arrow to be elements of size 2,3 and 4.
 *  Therefore we get many combinations of numerator and denominator and this is dealt by ***Backtracking algorithm***. 
 *  The rules which have confidence above 0.85 are written to file.
## Output :- 
A huge text file of Association rules of movies with confidences sorted in descending order.
