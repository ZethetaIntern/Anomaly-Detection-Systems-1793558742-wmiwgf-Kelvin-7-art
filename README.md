# Market Sentinel — Market Anomaly Detection

A browser-based prototype that simulates market trades, identifies unusual price and volume activity, and provides a workflow for reviewing alerts.

## Dashboard Preview

<!-- Replace the path below with your dashboard screenshot. -->
![Market Sentinel dashboard](https://github.com/Kelvin-7-art/Anomaly-Detection-Systems/blob/main/Anomaly%20Detection%20Systems/anomaly.png)

## Features

- Generate batches of 20 simulated trades.
- Detect unusual price and volume movements using statistical scoring.
- Compare trades against recent data for the same symbol.
- Prioritise alerts by anomaly score.
- Filter alerts by priority or investigation status.
- Start investigations and resolve alerts.
- Mark reviewed alerts as false positives.
- Add investigation notes.
- View recent trade context for a selected alert.
- Reset the session to a fresh sample dataset.

## Technologies

- HTML5
- CSS3
- Vanilla JavaScript
- Font Awesome icons via CDN

No backend, API keys, or package installation is required.

## Project Structure

```text
market-sentinel/
├── market-sentinel.html
├── README.md
└── images/
    └── dashboard.png
```

## Getting Started

1. Download or clone the project.
2. Open `market-sentinel.html` in a modern browser.
3. The dashboard loads with simulated trades and sample alerts.

An internet connection is needed to load the Font Awesome icons.
The simulation and review logic run locally in your browser.

## How to Use

1. Click **Simulate 20 trades** to generate additional activity.
2. Use **All**, **High/Critical**, or **Open** to filter alerts.
3. Select an alert to inspect its details.
4. Click **Start investigation** to begin reviewing it.
5. Click **View trade context** to see recent trades for that symbol.
6. Enter investigation notes and click **Save notes**.
7. Choose **Resolve alert** or **Mark selected as false positive**.
8. Click **Reset session** to clear the session and load fresh sample data.

## Anomaly Detection

The prototype compares each new trade with up to 50 previous trades
for the same symbol.

It calculates price and volume z-scores:

```text
z-score = (current value − historical mean) / historical standard deviation
```

These values feed a heuristic anomaly score. A trade becomes an alert
when its score exceeds 45.

Detected patterns include:

- Volume spikes
- Unusually low volume
- Upward or downward price gaps
- Combined price and volume deviations

### Priority Levels

| Priority | Score |
|----------|-------|
| Critical | 85–100 |
| High | 70–84 |
| Medium | 50–69 |
| Low | Below 50 |

Scores are heuristic indicators, not probabilities of fraud.

## Simulated Symbols

AAPL, MSFT, TSLA, NVDA, AMZN, META, JPM, XOM, BTC-USD, and ETH-USD.

All prices and volumes are synthetic.

## Data and Session Behaviour

Trades, alerts, investigation statuses, and saved notes are stored
in browser memory for the current page session.

Refreshing the page, closing it, or resetting the session clears this data.
There is no database or persistent storage.

## Limitations

- Uses simulated data rather than a live market feed.
- Uses statistical heuristics rather than a trained machine-learning model.
- Does not verify fraud or market manipulation.
- False-positive reviews do not retrain or adapt the detector.
- Does not include authentication, shared investigations, or export features.

This project is intended for learning and demonstration.

## Possible Future Improvements

- CSV import and report export
- Persistent investigation history
- Live market-data integration
- Interactive price and volume charts
- Configurable detection thresholds
- Trained anomaly-detection models
- User accounts and audit logs
