# Project visuals

The PNG files in this folder are static exports generated from `Tweets.csv`.
Counts and percentages are descriptive statistics for this dataset, not
predictions.

| File | What it shows |
|---|---|
| `sentiment_distribution.png` | Number and share of tweets in each sentiment class |
| `tweets_per_airline.png` | Tweet volume for each of the six airlines |
| `sentiment_by_airline.png` | Within-airline percentage split by sentiment |
| `negative_reasons.png` | Most frequently recorded reasons for negative tweets |
| `tweet_length_by_sentiment.png` | Distribution of tweet word counts by sentiment |
| `top_terms_by_sentiment.png` | Frequent non-stopword terms for each sentiment |
| `model_macro_f1.png` | Saved macro-F1 scores for each model and preprocessing variant |

The word-frequency chart is a simple descriptive view, not a model
explanation. The model chart uses the recorded comparison results documented
in [MODEL_SUMMARY.md](../MODEL_SUMMARY.md).

## Dataset highlights

- 62.7% of all tweets are negative (9,178 of 14,640).
- US Airways has the highest negative share (77.7%); Virgin America has the
  lowest (35.9%).
- Customer Service Issue is the most common recorded negative reason (2,910
  tweets).
- Negative tweets average 19.7 words, compared with 14.4 neutral and 14.0
  positive words.
