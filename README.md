# NLP Project 4 - Sentiment Analysis Web App

Flask web app that trains a text sentiment classifier on startup and serves
predictions through a simple UI and JSON API.

## Features
- Cleans and vectorizes text with TF-IDF
- Trains a LinearSVC classifier from `CHATGPT.csv`
- Browser UI for manual testing
- `/predict` JSON endpoint for programmatic use

## Tech Stack
- Python, Flask
- pandas, NumPy
- scikit-learn

## Project Structure
- `app.py` - Flask app and model training logic
- `CHATGPT.csv` - Training data (required)
- `templates/index.html` - UI
- `static/` - Front-end assets
- `NLP_PROJECT.ipynb` - Exploration notebook

## Setup
```bash
python -m venv .venv
source .venv/bin/activate
pip install flask pandas numpy scikit-learn
```

## Run
```bash
python app.py
```
Then open `http://127.0.0.1:5000`.

## API
`POST /predict`

Request body:
```json
{"review":"The app is fast and accurate."}
```

Response:
```json
{"sentiment":"positive"}
```

## Notes
- Training runs on app startup and uses `CHATGPT.csv` in the project root.
- If training fails, the server will not start.
# Sentiment-Analysis-of-Mobile-App-Reviews
