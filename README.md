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
- `public/` - Front-end assets (served by Vercel CDN)
- `NLP_PROJECT.ipynb` - Exploration notebook
- `requirements.txt` - Python dependencies

## Setup
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Run
```bash
vercel dev
```
Then open `http://localhost:3000`.

If you only need the API locally (no static assets), you can still use:
```bash
python app.py
```
Then open `http://127.0.0.1:5000`.

## Deploy (Vercel)
```bash
vercel
```
Follow the prompts. Vercel will detect the Flask app in `app.py`, install from `requirements.txt`, and serve assets from `public/`.

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
