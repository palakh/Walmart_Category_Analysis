# Walmart_Category_Analysis
Hierarchical Categorization of products om Walmart Website
![](https://specials-images.forbesimg.com/imageserve/82a018350ea24de796e60ae9d6a9c7da/960x0.jpg?fit=scale)


Walmart is an American multinational retail corporation that operates a chain of hypermarkets, discount department stores, and grocery stores, headquartered in Bentonville, Arkansas. Aside from this, Walmart also has a huge online base, with well over 65+ online banners under its name including Walmart.com. Naming a few such as Moosejaw, Bonobos, jet etc.

Our project is titled - Product Item Structure. The main area it focuses on is providing an overall consistent experience to customers across all banners. We achieve that by developing a consistent product categorisation based on learning and rule analysis from Walmart.com. 

Why do we need to work on this area - Customer Satisfaction. 
In the age where customers have multiple websites to select from, providing consistency across all the banners would put them at a superior position to gain loyalty from customers. Additionally presenting better visibility, will help how product descriptions need to be formed to provide better recommendations by search engines. 

Now, let’s talk about our dataset 

We scraped around 17000 products grouped into a 
3 level categorization 
                     - 5 cat0 (base level) 
                     - 20  cat1 
                     - 112 cat2 

After our analysis, we decided to work with product name and product description building our dataset to more than 3M + words.

Talking a little more extensively about our scraped data, it follows a hierarchical order. 
To give a little insight, let’s talk about one category 
for instance 

**Cat0- Food 
Cat 1 - Beverages, coffee, meal solutions and snacks  
Cat 2 - Energy Drinks, Juices, Soda Pop and water**

This is the hierarchical path, we aim to predict with our categorization models.
 
Our dataset combined with textual description therefore, we will use word embedding models to transform them into vectors.
We choose 3 main models 
             - tf-idf (baseline)
             - FastText 
             - pre-trained model Universal Sentence Encoder from Google

We performed cluster analysis and T-sne plots to understand which embeddings give us the best results and maximum variability in our data. Both our models presented USE as our best embedding model therefore we decided to run all our models with the USE embeddings. 

We implemeted multiple Classification models to get our hierarchical path
         - Random Forest
         - MLP
         - XgBoost
         - LDA
         - QDA
         - Linear SVC
         - Multinomial NB
         - Naive Model 

**Note** - Presently, we are working with a subset of our dataset, therefore we have comparable f1 and accuracy scores but we need to automate the model therefore consider f1 scores.

Best Model - Linear SVC

**Why not run this as a 112 class problem??**
This adds time and computation power. Addtionally this model has less accuracy and f1 score relative to our hierarchical model. 

Let’s talk a little more about the hierarchical model. For instance - Computers. Our model performs really well with the accuracy of 0.91 and f1 score 0.95. A very interesting insight we can get from our model is its ability to distinguish very ambiguous categories such as computer accessories and PC mode components. To give you a little more insights, these are a few examples of both 

Computer Accessories : Keyboard, Mouse etc
PC Components : CPU, Graphics card

Let’s discuss our final product now 

Final Product - Hierarchical Categorization 

Input - Product Description 
Output - Hierarchical Path

We have coded it in a black box format so that the customer doesn’t have to face any issues while using it or the person at Walmart’s end. 

After we implemented all this, we observed separability in our data even after the deepest level of categorization (cat2) therefore we formed one more hypothesis. 

**Hypothesis - we could form a further level of categorization (cat3 level) **

Clustering Algorithms Implemented
- kmeans
- Density-based spatial clustering (DBScan)
- Gaussian Mean Modeling (GMM)

We got impressive results with GMM clustering validating our hypothesis that we can create a deeper level of categorization. 
We had to implement Topic Modeling using  LDA ( Latent Dirichlet Allocation) to study these clusters. 

**Why perform Topic Modeling**
Features were not interpretable since they were embeddings and we had further implemented Principal Component Analysis further making them difficult to interpret.  


