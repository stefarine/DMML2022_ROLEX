# DMML2022_ROLEX
<p align="center">
<img height=200 src="https://user-images.githubusercontent.com/57952280/208384889-e102268f-0458-42e2-bb84-b92f1337bbfd.png">
</p>

## Brief description of the project
Within the context of the [Data Mining and Machine Learning](https://hecnet.unil.ch/hec/syllabus/descriptif/2457?dyn_lang=fr) course given by Prof. [Michalis Vlachos](https://www.linkedin.com/in/michalis-vlachos/) we have realized this project. It is about predicting the difficulty level of a sentence (A1-C2) using machine learning techniques. To carry out this task we have at our disposal a dataset of 5000 entries which contains annotated sentences to train our models. A competition related to this project is available on [kaggle](https://www.kaggle.com/competitions/detecting-french-texts-difficulty-level-2022/overview).

## Participants
[Mariam Davis](https://www.linkedin.com/in/mariam-davis-439385209/)
- Bsc Management, HEC Lausanne - University of Lausanne
- Msc Information Systems and Digital Innovation, HEC Lausanne - University of Lausanne 

[Stéphane Pacheco Fernandes](https://www.linkedin.com/in/stéphane-pacheco-fernandes)
- Bsc Infomation Systems, University of Geneva
- Msc Information Systems and Digital Innovation, HEC Lausanne - University of Lausanne 

My name is Stéphane I am 26 years old and I come from Geneva. I am curious by nature and I love to learn new things. I really enjoy working in teams on IT related topics and find solutions to problems. I love programming and in particular implementing Android applications.

## Approach
In order to complete this project, we had at our disposal an annotated dataset where each record corresponds to a sentence and the indication of its level. Here is an example:

| id | sentence |difficulty|
| ------------- | ------------- |----------|
| 95  | Mon ami ne répond pas au téléphone.	 |A1|
| 993  | Il m'a donné un coup de poing dans la figure.|B1|
| 1992	 | Il veut tout manger.	  |A2|
| 2079	 | Le village québécois s'appelait jadis "la descente des femmes"	  |C2|
| 3999  | Carlos Ghosn sera-t-il le dernier protagoniste de sa folle escapade à demeurer hors d'atteinte de la justice ?	  |B2|

At first, we worked on these data without using any data cleaning technique. We vectorized the sentences using TFIDF and used the obtained data to train some basic models for multiclass classification such as Logistic regression, k-nearest neighbors (kNN), Decision Tree and Random Forests. The results were not particularly good so we tried other models. For example, we can cite the naive bayes classifier for mulinomial models but the results were not much better. At this point it was the Logistic regression with cross validation that gave us the best results.

Then, we tried to combine several models to obtain better results by implementing a voting set. But once again, the results were not much better. So we decided to change our approach. We cleaned up our data by removing stopwords, punctuation and doing lemitization. Then, we processed the tokens using Doc2Vec. Following this, we trained our previously mentioned models, but the results were not much better. 

Finally, we chose a radically different method using a BERT (Bidirectional Encoder Representations from Transformers); this is a transformer-based machine learning technique for natural language processing (NLP) pre-training developed by Google. We specifically used camemBERT, which is very well adapted for pre-training in French.


## Summary of results table
|  | Logistic regression |kNN	| Decision Tree | Random Forests |camemBERT|
| ------------- | ------------- |----------| ------------- | ------------- |----------|
| Precision |0.4645|0.4007| 0.2987 | 0.4223 |x|
| Recall |0.4677|0.3138| 0.3009 | 0.4165 |x|
| F1-score | 0.4640|0.3022| 0.2947 | 0.4014 |x|
| Accuracy | 0.4667 |0.3187| 0.3000 | 0.4135 |x|

					
					
					



## Explainatory video
## Sources
- [Course GitHub](https://github.com/michalis0/DataMining_and_MachineLearning)
- [kNN Hyperparameter Optimization](https://www.kaggle.com/code/arunimsamudra/k-nn-with-hyperparameter-tuning)
