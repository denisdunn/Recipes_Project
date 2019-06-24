# Recipes_Project
Overview:
  This project takes a machine learning approach to recipes and food. I have created a unique recipe generator using natural language processing and unsupervised machine learning. Along with unique recipes, I am able to cluster recipes into groups using the words in the directions and ingredients. Each cluster has a food theme that I find to be best illustrated using word clouds. Once a cluster is chosen based on a desired theme, my program asks for two optional ingredients that the user would like in the recipe and then returns a similar but unique recipe based on real recipe in the dataset. 
  
  
![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-23%20at%205.08.14%20PM.png) 


Data aquisition & cleaning:
  Through a mixture of webscraping and searching online I was able to amass over 33 thousand recipes. Processing the words from libraries in NLTK and Gensim I took out the nltk stopwords along with words that I felt needed to be taken out, and lowercased the recipes. I tokenized the words, and counted the words that are most referenced in the ingredients.
  
 ![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-19%20at%201.15.49%20PM.png)
 
 
  
Natural Language Processing:
  After testing a few different modeling techniques (Fasttext, one hot encoding, TFIDF), I settled on Word2Vec. Word2Vec uses two shallow neural networks to vectorize the words. I tested both the continuous bag of words model and skipgram models and didn't see much of a difference. After vectorizing the recipe columns I built a model using the words in the titles, ingredients, and  directions. I chose these three columns because I feel that the directions are an integral differentiator in recipes. I tested out a few other columns but the results didn't help with the clustering.
  
Dimensionality Reductions:
  After vectorizing the words in each recipe I reduced demensionality by summing each word vector together to create one overall recipe vector.
  
 Unsupervised Machine Learning:
  Most people pick a recipe based on an ingredient they have for example 'chicken' dishes, or they think of a regional cuisine that they are looking for like 'Italian' or 'Chinese'. Taking a new approach to choosing a recipe I tried a few different clustering models(Hierarchical agglomerative & kmeans), to see how a machine would group the recipes.  
    
