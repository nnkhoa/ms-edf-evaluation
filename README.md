# ms-edf-evaluation
Google Trends data used for evaluation in the paper "Contextualizing Emerging Trends in Financial News Articles"

TODOs:

* Explain the evaluation file (the format, loading, how to evaluate, etc.)

* Example for creating the golden standard using Google Trends data

Data Loading:

```
import pickle
with open('ggtrend_data_stable.pickle', 'rb') as f:
    google_trend_data = pickle.load(f)
```

Converting the date index to the appropriate formate and aggregate them into monthly frequency 

```
google_trend_data.index = pd.to_datetime(google_trend_data.index)
google_trend_data = google_trend_data.groupby(pd.Grouper(freq='MS')).mean()
```
