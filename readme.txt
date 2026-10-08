# 📄 ATS Resume Checker

Upload a resume (PDF, DOCX or TXT) and get an ATS score, a category breakdown,
prioritized improvements, missing keywords and example bullet rewrites.
Built with **Streamlit** and **Google Gemini Flash**.

## Features
- Overall ATS score (0-100) plus Formatting, Keywords, Content & Impact, Structure and Readability scores
- Prioritized improvement suggestions (High / Medium / Low)
- Optional job description for targeted keyword matching
- Missing keywords and before/after bullet rewrites
- Download the report as JSON

## Run locally
1. Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey).
2. Install and run:
   ```bash
   python -m venv venv
   source venv/bin/activate        # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   export GEMINI_API_KEY="your_key"   # Windows PowerShell: $env:GEMINI_API_KEY="your_key"
   streamlit run app.py
   ```
   You can also skip the environment variable and paste the key into the app's sidebar.

## Configuration
| Setting | Purpose | Default |
|---|---|---|
| `GEMINI_API_KEY` | Your Gemini API key | none (required) |
| `GEMINI_MODEL` | Gemini Flash model name | `gemini-2.5-flash` |

Set them as environment variables locally, or in Streamlit Cloud under
**App settings -> Secrets**:
```toml
GEMINI_API_KEY = "your_key"
```

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub (never commit your API key).
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
3. Click **Create app**, choose your repo, branch `main`, main file `app.py`.
4. Open **Advanced settings -> Secrets** and add `GEMINI_API_KEY = "your_key"`.
5. Click **Deploy**.

## Notes
- Scanned (image-only) PDFs can't be read; use a text-based PDF or DOCX.
- The score is an AI estimate, not the output of a real ATS.
- Resume text is sent to Google's Gemini API. Don't upload data you can't share.

## Project structure
```
app.py            # Streamlit app
requirements.txt  # Dependencies
README.md
```
