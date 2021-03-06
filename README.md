# Recommendation-System
Recommendation-System with MovieLens Data


SUMMARY
================================================================================

We used 1,000,209 anonymous ratings of nearly 3,900 movies made by 6,040 MovieLens users to create the Movie Recommendation System.
After that, we separated the last 5 movies watched by users (using timestamps) as test data and the remaining data as training data.

RATINGS FILE DESCRIPTION
================================================================================

All ratings are contained in the file "ratings.dat" and are in the
following format:

UserID::MovieID::Rating::Timestamp

- UserIDs range between 1 and 6040 
- MovieIDs range between 1 and 3952
- Ratings are made on a 5-star scale (whole-star ratings only)
- Timestamp is represented in seconds since the epoch as returned by time(2)
- Each user has at least 20 ratings

MOVIES FILE DESCRIPTION
================================================================================

Movie information is in the file "movies.dat" and is in the following
format:

MovieID::Title::Genres

- Titles are identical to titles provided by the IMDB (including
year of release)
- Genres are pipe-separated and are selected from the following genres:

	* Action
	* Adventure
	* Animation
	* Children's
	* Comedy
	* Crime
	* Documentary
	* Drama
	* Fantasy
	* Film-Noir
	* Horror
	* Musical
	* Mystery
	* Romance
	* Sci-Fi
	* Thriller
	* War
	* Western

- Some MovieIDs do not correspond to a movie due to accidental duplicate
entries and/or test entries
- Movies are mostly entered by hand, so errors and inconsistencies may exist

MODEL
================================================================================
We embed both users and movies into 100-dimensional vectors. 
The model computes a match score between user and movie embeddings via a dot product and adds a per-movie and per-user bias.
The match score is scalled to the [0, 1] interval via a sigmoid (since our ratings are normalized to this range).

PERFORMANCE METRICS
================================================================================
- In order to evaluate model performance, accuracy score, precision score and recall score values were checked.
- Calculated loss using binary cross entropy. 
- Metric performances and related graphs are presented in the notebook.
- Jaccard Index can be used to more clearly observe the performance of the model.
  In this way, the movies suggested by the model can be compared with what the person watches.


REFERENCES
================================================================================

F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: History
and Context. ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4,
Article 19 (December 2015), 19 pages. DOI=http://dx.doi.org/10.1145/2827872
