      categorical data → non numerical type

○      nominal → Represents categories with no inherent order or ranking  say colours

○      ordinal → Represents categories with a specific order or ranking.  say grades

○      **chi-square test.**    

○       

      OneHot/Label → for colour column you create new column for each colour and match 1 if red else 0


      StandardScaler → mean 0, std 1, good for normal-like data.  

○      MinMaxScaler → rescale to [0,1], good for neural nets but sensitive to outliers.

      Outlier treatment using  

○      IQR → Measures the middle 50% of data (Q3 – Q1).  else outlier

○      Z-score → normal distrbn if out of 3 s.d then outlier

       

       

      **. “What ML algorithms have you used?”**

○      **Linear Regression** → Predict numbers using straight-line relationship  

○      **Logistic Regression** → Classification using sigmoid probability

○      **Decision Tree** → Rule-based splits on features

○      **Random Forest** → Many trees  ↔  reduce overfitting

○      **KNN** → Predict using nearest neighbors

○      **SVM** → Best separating line with maximum margin

○       

○      **6. “Explain R², MAE, MSE.”**

○      **R²** – variance explained by model

■      R² = **Explained Variance / Total Variance**  

      Value ranges from **0 to 1**

      **0** → Model explains nothing

      **1** → Model explains everything perfectly

      Higher R² = better fit (but not always perfect)

      Used mainly in **regression models**

○      **MAE** – mean absolute error

○      **MSE** – penalizes large errors (squared) Average of the **squared** differences between predicted and actual values.   

○      MSE > MAE sensitivity

○      Used together to check accuracy + error pattern.

       

       

      **NLP Mention — expect “What NLP techniques do you know?”**

○      Keep it simple:

■      Tokenization

■      Stopword removal → Removing common words that do not add much meaning   

■      Lemmatization → Convert a word to its **root meaningful form** (lemma).  running lemma is root word run

■      Text vectorization (TF-IDF, embeddings)

      Converting text into **numerical vectors** so ML models can understand it.

○      Two main types:

○      a) TF-IDF   

■      Counts how important a word is in a document.

■      High score = unique word

■      Low score = common word

■      Example: like resume ATS scanner

      “machine learning” appears rarely → high TF-IDF

      “the”, “is” → low TF-IDF

○      b) Embeddings (Word2Vec, GloVe, BERT)

■      Converts words to dense vectors capturing meaning and context.

■      “King” and “Queen” become close in vector space.

■      Models can understand similarity.

■      Prompt engineering basics

○       

       

      **Mandatory to revise before call (5 mins):**

○      Linear vs Logistic Regression

○      Bias-variance

○      Overfitting = low test accuracy, high train accuracy. Fix it using cross-validation, regularization, simpler models, early stopping, dropout, pruning, more data, and feature reduction.   

○      Train-test split → 70-80 and 30-20

○      Feature engineering examples

○       

○      **Scaling:**

■      StandardScaler → mean 0, std something like bell curve +,-,0  

■      MinMaxScaler → 0 to 1

      Values are adjusted **feature-wise**.

■      Most ML models: SVM, Logistic Regression, KNN, PCA

■      When features have different units (kg, cm, ₹)

○      **Normalization:**

■      Text data, NLP vectors

■      KNN, K-means (distance-based)

■      When sparse vectors should be normalized row-wise

○      **Normalization:**

■      L1 Normalization → sum of absolute values = 1

■      L2 Normalization → Euclidean length = 1

      Values adjusted **sample-wise (row-wise)**.

○      Explain random forest in 6 lines

○      Cross-validation types

       

      **What Cross-Validation does?**

○      **It repeatedly tests the model on different subsets of data.**

○      Example: **5-Fold CV**

■      Split data into 5 parts

■      Train on 4 parts, test on 1

■      Repeat 5 times by rotating the test part

■      Average the performance

○      **Benefit:**

○      Cross-validation **forces the model to prove itself** on unseen data again and again →  

○      so it **cannot overfit** easily.

       

      **Regularization — Simple Explanation**

○      **Problem:**

○      In overfitting, the model learns too much detail and creates very large weights/coefficients.

○      **What Regularization does?**

○      Regularization **penalizes large weights** → pushes the model to be **simpler and smoother**.

○      Two types:

○      **L1 Regularization (Lasso)**

■      Pushes some weights to **zero**

■      Helps in **feature selection**

○      **L2 Regularization (Ridge)**

■      Shrinks weights

■      Prevents model complexity

■      Reduces variance

○      **Intuition:**

○      Without regularization:

○      Model → “I will memorize everything.”

○      With regularization:

○      Model → “No. Keep things simple. Don’t overreact to noise.”