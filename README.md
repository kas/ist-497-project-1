# ist-497-project-1

Clickbait Tweet Classification

The aim of this project is to build an accurate binary classification model that can discriminate clickbait tweets from legitimate ones with high F-measure and AUC scores.

Each data instance consists of two parts: (1) the tweet itself, and (2) the actual news article (linked from the tweet).

**Rough Project Timeline**

1. Find features and models from below articles
2. Test features and models to find highest scores
3. Write project report

**Useful Articles for Features and Models**

- Potthast, M., Köpsel, S., Stein, B., & Hagen, M. (2016, March). Clickbait detection. In European Conference on Information Retrieval (pp. 810-817). Springer International Publishing.
  - 215 features
    - Three categories
      - Teaser message
        - Three categories
          - Basic text statistics
            - Bag-of-words features
            - Twitter-specific
            - Automatically generated image tags (Imagga tagging service)
            - Sentiment polarity (Stanford NLP Library)
            - Readability
            - Terrier stop word list and Dale-Chall list of easy words
            - Quantity of contradictions and punctuation use
            - Length statistics
          - Dictionary features
            - Checking if a tweet contains a word from a given dictionary of specific words or phrases
            - Dictionaries obtained from Gianotto
              - Common clickbait phrases
              - Clickbait patterns in the form of regular expressions
            - All 182 General Inquirer dictionaries
      - Linked web page
        - Bag-of-words features
        - Readability and length of the main content when extracted with Boilerpipe
      - Meta information
        - The tweet's sender
        - Whether media (e.g., an image or a video) has been attached to a tweet
        - Whether a tweet has been retweeted
        - Part of day in which the tweet was sent (i.e., morning, afternoon, evening, night)
  - Random forest classifier
  - Takeaways
    - Clickbaity BuzzFeed articles contain a cardinal number in their title, and 85% of the article titles started with that number
      - The same titles have strong nouns and adjectives to convey authority and sensationalism
      - The main articles consistently achieve easy readability according to the Gunning fog index
    - Phoricity
      - Discourse deixis
        - Using keywords like "This" in "This news will blow your mind."
    - They use Gianotto's rule set premises as features and as a basline for evaluation
      - http://downworthy.snipe.net/
- BIYANI, P.; TSIOUTSIOULIKLIS, K.; BLACKMER, J. (2016, Feb) "8 Amazing Secrets for Getting More Clicks": Detecting Clickbaits in News Streams Using Article Informality. AAAI Conference on Artificial Intelligence, North America.
- Chakraborty, A., Paranjape, B., Kakarla, S., & Ganguly, N. (2016, August). Stop clickbait: Detecting and preventing clickbaits in online news media. In Advances in Social Networks Analysis and Mining (ASONAM), 2016, IEEE/ACM International Conference on (pp. 9-16). IEEE.
- Wei, W., & Wan, X. (2017). Learning to Identify Ambiguous and Misleading News Headlines. arXiv preprint, arXiv:1705.06031.

**Definitions**

AUC Score: Area Under Curve score. AUC refers to area under ROC curve. ROC stands for Receiver Operating Characteristic. The ROC curve is created by plotting the true positive rate (TPR) against the false positive rate (FPR) at various threshold settings.

- http://fastml.com/what-you-wanted-to-know-about-auc/
- https://en.wikipedia.org/wiki/Receiver_operating_characteristic
- http://scikit-learn.org/stable/auto_examples/model_selection/plot_roc.html

Clickbait: Aims to exploit the "curiosity gap", providing just enough information to make readers of news websites curious, but not enough to satisfy their curiosity without clicking through to the linked content.

- https://en.wikipedia.org/wiki/Clickbait

F1 Score: A measure of a test's accuracy. It considers both the precision p and the recall r of the test to compute the score. p is the number of correct positive results divided by the number of all positive results returned by the classifier, and r is the number of correct positive results divided by the number of all relative samples (all samples that should have been identified as positive).

- https://en.wikipedia.org/wiki/F1_score
- http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html
- https://stackoverflow.com/questions/31421413/how-to-compute-precision-recall-accuracy-and-f1-score-for-the-multiclass-case

**How to Run**

1. Create a `data/` folder in the root of the repository
2. Paste the files downloaded from the link in the project description into that folder
