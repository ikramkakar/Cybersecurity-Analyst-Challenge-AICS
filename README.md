# Cybersecurity-Analyst-Challenge-AICS

**Description:**
CyberSecurity in AI. This project explores cybersecurity challenges and solutions in the context of artificial intelligence.

## Overview

This project analyzes game account activity to detect security threats using a combination of:
- User and Entity Behavior Analytics (UEBA)
- DBSCAN (for anomaly clustering)
- Prophet (for time series anomaly detection)

It uses a synthetic gaming security dataset.

## Project Structure

- `cybersecurity_analyst_challenge(assignment).py` — Main analysis script
- `gaming_security_dataset.csv` — Required dataset (CSV file, must be in the same folder)

## Requirements

Install the required Python libraries:

```bash
pip install pandas scikit-learn matplotlib prophet
```

> Note: On some platforms, you may need to use `pip install prophet` or `pip install fbprophet`, depending on your Python version.

## Data Format

Your `gaming_security_dataset.csv` should have these columns:

- `UserID`: Unique user identifier
- `Timestamp`: Login time (will be converted to datetime)
- `IP_Address`: Source IP of login
- `Country`: Location of login
- `Device_Type`: PC / Mobile / Console
- `Login_Success`: Yes/No
- `Failed_Attempts`: Number of failed login attempts before success
- `Session_Duration_Min`: Duration of session in minutes
- `InGame_Purchase_USD`: Value of purchases in session

## How to Run

1. Place the dataset in the same folder as the script (expects `gaming_security_dataset.csv`).
2. Run the script:
   ```bash
   python cybersecurity_analyst_challenge(assignment).py
   ```
3. Outputs:
   - Prints heads, info, and statistics of your data
   - Builds user baselines and calculates behavior deviation
   - Creates UEBA risk scores and DBSCAN anomaly clusters
   - Uses Prophet for time-series anomaly detection on daily login counts
   - Displays graphs for login counts and Prophet's time-series model
   - Final security alerts and a summary are printed to the console

## How It Works (Pipeline Summary)

1. **Preprocessing:** Loads and processes data, parses timestamps, creates features (login hour, etc).
2. **User Baseline:** Aggregates by user to establish "normal patterns".
3. **Deviation Calculation:** Evaluates deviations from baseline for each activity.
4. **Feature Scaling:** Normalizes features using StandardScaler.
5. **DBSCAN:** Flags cluster outliers as anomalies.
6. **Risk Scoring:** Assigns risk based on behavior deviation weights.
7. **Prophet:** Models daily logins as a time series for anomaly detection.
8. **Alert Generation:** Combines anomaly signals to report suspicious users.

## Example Security Alerts

The output includes details like:
- UserID
- Timestamp
- Risk Score
- Anomaly cluster label (from DBSCAN)

## Customization & Extension
- Modify the risk score formula for your own priorities.
- Add more features for fine-tuned analysis.
- Integrate other detection rules as needed.

---

This repository is focused on addressing the intersection of cybersecurity and artificial intelligence, with all code and resources implemented in Python.
