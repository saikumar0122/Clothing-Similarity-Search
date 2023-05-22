# Clothing-Similarity-Search

This code provides a simple implementation of a clothing similarity model that utilizes cosine similarity and TF-IDF vectorization to find similar clothing items based on their textual descriptions.

Usage:
1. Data Preparation:
   - Ensure that your clothing data is stored in a CSV file named 'dataset.csv' in the same directory as the code file.
   - The CSV file should contain a column named 'Item' that represents the textual description of each clothing item.

2. Library Installation:
   - Install the required libraries by running the following command:
     ```
     pip install pandas scikit-learn
     ```

3. Running the Model:
   - Execute the code in a Python environment.
   - The code will load the clothing data, preprocess it, and build a similarity matrix.
   - Afterward, it will prompt you to enter a query (textual description of a clothing item).
   - The model will return the top 5 similar clothing item suggestions along with their URLs.

Code Overview:
- The code first imports the necessary libraries: pandas, cosine_similarity from sklearn.metrics.pairwise, and TfidfVectorizer from sklearn.feature_extraction.text.
- It then reads the clothing data from the 'output.csv' file into a DataFrame using pandas.
- A value 'n' is set to determine the number of similar items to be suggested (default is 5).
- A TfidfVectorizer object is created for text vectorization.
- The item names are extracted from the DataFrame and fitted to the vectorizer to learn the vocabulary and IDF weights.
- The item names are transformed into TF-IDF vectors using the fitted vectorizer.
- Cosine similarity is computed based on the TF-IDF vectors to build the similarity matrix.
- The 'cloth_predict' function is defined to accept a query and find the top 'n' similar items.
- Inside the function, the query is transformed into a vector using the vectorizer.
- Cosine similarity is computed between the query vector and the vectorized item names.
- The top 'n' indices of the most similar items are retrieved based on the similarity scores.
- The URLs of the similar items are extracted from the DataFrame.
- The function then prints the top 5 suggestions along with their indices.

Note:
- Ensure that the 'dataset.csv' file is in the correct format and contains the required 'Item' column.
- Modify the code as per your specific requirements, such as changing the input file, modifying the number of suggestions, or customizing the output format.
