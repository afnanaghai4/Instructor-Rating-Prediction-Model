# Instructor-Rating-Prediction-Model


 ## Introduction:
 
“How is xyz teacher learning and grading wise?”
This is a question which is most frequently asked by the students before the semester starts. Every student goes for a teacher that has good reviews. But the question is, in tons of reviews present on Facebook and university sites, how many reviews can a person read since many of them are too long? In order to solve this problem, university decided to rate each teacher on the yearly reviews of the students so that it would become easier for the students to decide which teacher’s course they should enroll in. Not only students, university will also be able to judge the performances of teachers based on the reviews along with many other factors like course outline etc. Furthermore, university also decided to put up 5 highly rated reviews of the teachers with the ratings so that students could have a much better idea.
But the problem was, reviews are in a bulk and it is impractical to give a rating to each review manually. This is where we were brought in to develop a model using the current directory of reviews that are rated and predict the ratings of the reviews that have been coming this whole year and automate the process of labelling each review.

## Data and It’s Cleaning:

The data comprised of 3080 reviews which were rated and given for training of the model. Whereas, there were 1321 unrated reviews in the testing dataset. Dataset contains 3 columns:

ID: each review is given a unique ID for its identification.


RATING: each review is given its rating. There are 5 levels of rating a review;
1.	Awesome
2.	Good
3.	Average
4.	Poor
5.	Awful
REVIEW: this column contains the review about the teacher that the student has written.

The quality of the data can be considered to be average since there are a lot of spelling mistakes in the review column and this is pivotal because it contains wrong spellings of words which are crucial in predicting about the rating of the review. Although, ratings are all written without any mistakes.


![stack Overflow](/images/1.png)



Now, the first thing which we wanted to do was remove unnecessary columns and rows. We removed the ID column since it does not play much of a role in the predictions of ratings.
We also removed stop words which do not carry much importance, words like “is”, “a”, “an”, “the”, “then”, “in”, “has”, “had” etc. By doing this, we made it easier for our model to learn on the training dataset and give more accurate results. We also replaced contractions with full forms like “what’s” replaced with “what is”, “wouldn’t” replaced with “would not” etc.

 ## MODEL AND EVALUATION:

The PC used for modelling is an i5-6300U 8gb RAM DDR4 and 500gb HDD.
To create the model, we used multiple model building techniques including Random forest, Gaussian Naïve Bayes, Decision tree classifier etc. Train data was split into a 9:1 ratio and we used 90% for model building while tested the model on the remaining 10%. We also used k-means clustering technique but it did not result in an increase in the accuracy so we stopped using it.
Multinomial Naïve Bayes was the method which gave us the highest accuracy among all the techniques that we tried. We applied the method with Count vectorizer using unigrams and bigrams and max features limited to 8667. With these features restriction, we managed to get an accuracy of 0.5681(about 57%) which was the highest among all the different methods we had tried earlier.
	

This is the Multinomial Naïve Bayes code snippet along with its accuracy.
Before Multinomial NB we had tried Random forest, Decision tree, Ensemble techniques including Adaboosting and Gradient boosting. We also tried Gaussian Naïve Bayes but still it gave lesser accuracy than multinomial Naïve Bayes.

This is decision tree classifier code snippet along with its accuracy.
 
This is Gaussian Naïve Bayes code snippet along with its accuracy.
The language used in building the model is Python along with Jupyter IDE. The libraries we used are Sklearn, Pandas, keras, wordcloud, matplotlib, seaborn, numpy. Sklearn, Pandas, keras numpy were used in the processing of the data while matplotlib, seaborn and wordcloud are used for data visualization like graphs and wordclouds.








Above graph shows the total count of the reviews for each category of rating. According to the graph, “awesome” category has the most count of reviews.







Above picture shows the wordcloud of the reviews that are in the training dataset.
## Limitations and Deployment:

After building the model, there were still many limitations that came up. There are still words present in the reviews column which need to be changed or should not be included in model building. If enough manpower and time is put into doing this, accuracy can be increased to a greater extent.
The model will be deployed on the university’s website and will be used at the end of each semester when university will collect reviews about teachers from students through faculty evaluation. Furthermore, the model will also run before the time of enrollment, when students are giving reviews on different social media platforms. All the reviews will be collected by university’s administration and will be copied on an excel sheet. Then the model will run and predict each review’s rating which the administration will use to generate ratings of each teacher which will be used by the university to judge a teacher’s performance and which will also prove to be beneficial for the students at the time of their enrollment.
The model will need maintenance every 2 years. This is because the incoming batch of students will have different experiences and might express feedback differently than the old students. So the new reviews by younger students would have a different structure than the old reviews on which the model was trained. This means using different words representing different feelings about a teacher. Due to this reason, data cleaning techniques will need an update like changing stop words etc. 

