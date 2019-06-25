# Recipes_Project
Overview:
  This project takes a machine learning approach to recipes and food. I have created a unique recipe generator using natural language processing and unsupervised machine learning. Along with unique recipes, I am able to cluster recipes into groups using the words in the directions and ingredients. This process creates a theme of both the ingredients in the recipe and also how the meals are prepared. Themes like 'Thanksgiving',or 'Grilling' come to mind and I find them best illustrated using word clouds. Once a cluster is chosen based on a desired theme, my program asks for two optional ingredients that the user would like in the recipe and then pulls out a recipe from the dataset, processes the ingredients using Word2Vect and an extra layer I created. The process looks for similar words in the ingredients list using cosine similiarity and replaces a few very similar ingredients creating a very unique and delicious recipe. 
  
  
![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-23%20at%205.08.14%20PM.png) 


Data aquisition & cleaning:
  Through a mixture of webscraping and searching online I was able to amass over 33 thousand recipes. Processing the words from NLTK and Gensim libraries. I took out repetitive & nltk stopwords, lowercased and tokenized the rest.  I counted the most referenced ingredients in the corpus (minus salt and pepper).
  
 ![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-19%20at%201.15.49%20PM.png)
 
 
  
Natural Language Processing:
  After testing a few different modeling techniques (Fasttext, one hot encoding, TFIDF), I settled on Word2Vec. Word2Vec uses two shallow neural networks to vectorize the words. I tested both the continuous bag of words model and skipgram model. Both performed very similarly, The Continuous bag of words has the context and looks for the targeted word which was more appropriate for this project. After vectorizing the recipe columns I built a model using the words in the titles, ingredients, and  directions. I included the directions because I feel that they an integral differentiator in recipes. I tested out a few other columns as well but the results didn't help with the clustering.
  
Dimensionality Reduction:
  After vectorizing the words in each recipe I wanted to group recipe words together, and help with potential sparce matrix issues. I reduced the demensionality by summing each word vector together to create one overall recipe vector.
  
 Unsupervised Machine Learning:
  Most people pick a recipe based on an ingredient they have for example 'chicken' dishes, or they think of a regional cuisine that they are looking for like 'Italian' or 'Chinese'. Taking a new approach to choosing a recipe I tried a few different clustering models(Hierarchical agglomerative & kmeans), to see how a machine would group the recipes. I found Calinski Harabaz scores to see where the number of clusters lose their variance. While the scores show the elbow is around 40 clusters I found that 100 clusters made the project more interesting to the user. Here is a graph of the scores:
  
 ![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-19%20at%201.12.34%20PM.png)
 
  Here is a truncated dendrogram of the clusters:
    
![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-19%20at%201.10.38%20PM.png)

Next Steps:
    Clustering recipes based on ingredients and directions creates very interesting groupings. I am going to explore the groupings more to gain better insight. I am going to explore using tensorflow and more in depth neural networks to improve the preditive capabilities of my model. I would like to predict more of the recipe making and improve the accuracy. I am also going to word on other dimensional reduction techniques (LSA, PCA). I am also going to improve the visualization of the final recipe. Here is a unique recipe example created by my project:

![Plot](https://github.com/denisdunn/Recipes_Project/blob/master/Screen%20Shot%202019-06-25%20at%209.34.50%20AM.png)
