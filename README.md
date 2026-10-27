# Airline Passenger Tweet Sentiment Analysis

An NLP project that explores US airline passenger tweets and compares text
classification models for three sentiment classes: negative, neutral, and
positive.

## Project contents

- `NLP_model_on_Airline_Passengers_Tweets_Da.ipynb` — exploratory analysis,
  tweet cleaning, TF-IDF feature extraction, and model comparison.
- `Tweets.csv` — the 14,640-row dataset with only the four fields used by the
  notebook: `airline`, `text`, `airline_sentiment`, and `negativereason`.
- `requirements.txt` — Python dependencies for running the notebook.
- `Visuals/` — exported charts and a guide to their contents.
- `MODEL_SUMMARY.md` — model setup, evaluation results, and limitations.

The dataset is derived from the Twitter US Airline Sentiment data attributed in
the notebook to Kaggle/Figure Eight. Check the dataset's original terms before
redistributing it in a public repository.

## Setup

Use Python 3.9 or newer. From the project directory, create and activate a
virtual environment, then install the dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Open the notebook in VS Code or Jupyter, select the environment created above
as the kernel, and run the cells in order. The notebook reads `Tweets.csv`
from the project directory. Some NLP cells download NLTK data packages the
first time they run.

## Highlights

- 14,640 tweets from six airlines.
- Three sentiment labels; negative tweets account for approximately 62.7% of
  the data, so macro-F1 is reported alongside accuracy.
- The saved notebook comparison reports the best macro-F1 for a clean-text
  Linear SVM. See [MODEL_SUMMARY.md](MODEL_SUMMARY.md) for all recorded scores.
- Charts are available in [Visuals/](Visuals/).

## Dataset fields

| Field | Description |
|---|---|
| `airline` | Airline named in the dataset |
| `text` | Tweet text used as the model input |
| `airline_sentiment` | Target label: negative, neutral, or positive |
| `negativereason` | Recorded reason for negative sentiment; blank for other rows |

## Notes

The notebook contains exploratory analysis and model-comparison code, but does
not save a trained model artifact. The scores in the model summary are from
saved notebook output and can change if the preprocessing, dependencies, or
data change.
