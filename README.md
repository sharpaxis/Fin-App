

# 📈 Fin-App: Automated Financial News Classification & Sentiment Intelligence

Fin-App is an end-to-end NLP system designed to help traders, analysts, and researchers automatically extract insights from real-time financial news.

It fetches market headlines from Yahoo Finance, classifies whether the news is financial or non-financial, performs sentiment analysis on relevant articles, stores everything in PostgreSQL, and can optionally generate summaries for actionable insights.

⸻

🚀 Key Features

🔍 1. Real-time Yahoo Finance News Fetching

Automatically pulls the latest headlines and summaries for any ticker.

🤖 2. Two Fine-Tuned Transformer Models

📌 Model 1 — Financial/Non-Financial Classifier (DistilBERT)
Repo: https://huggingface.co/Sharpaxis/distilbert-news-classification
	•	Determines if a news article is relevant to finance
	•	Fine-tuned on your custom curated dataset (280k+ articles)

📌 Model 2 — Sentiment Classifier (FIN-BERT)
Repo: https://huggingface.co/Sharpaxis/FIN_BERT_sentiment
	•	Predicts sentiment: Positive / Negative / Neutral
	•	Domain-tuned for stock-market language

⸻

🧪 3. Custom Dataset Curated by Me

📘 Dataset: https://huggingface.co/datasets/Sharpaxis/Stock_news_classification

Includes:
	•	Hand-collected stock/tech/finance articles
	•	Cleaned and labeled (financial vs non-financial)
	•	Suitable for downstream financial NLP tasks

⸻

🗄️ 4. PostgreSQL Storage Layer

Every record includes:
	•	Headline, summary, ticker
	•	Financial/non-financial classification
	•	Sentiment probabilities
	•	Timestamps
	•	Optional summarized insight

Perfect for:
	•	Dashboards
	•	Automated alerts
	•	Trend analysis

⸻

🧠 5. Optional LLM Summarization

Takes multiple articles → produces a clean market summary.

Example:
	•	“Overall market sentiment today is positive, driven by tech earnings…”

⸻

🧱 Project Architecture

Fetch News → Filter News → Classify Sentiment → Store in PostgreSQL → Summarize → Output


⸻

🖼️ Example Outputs

Below are visual examples produced by the notebook.

<img width="826" height="770" alt="SCR-20251128-sdzd" src="https://github.com/user-attachments/assets/be43b9e6-1b60-462b-9c59-0795d980a3db" />


⸻

🟦 Example 2 — Neutral Sentiment Classification

<img width="893" height="821" alt="SCR-20251128-selu" src="https://github.com/user-attachments/assets/d5ab6f40-b6f4-48ef-ae5f-3aba89b9dfc7" />



⚙️ Installation

git clone https://github.com/sharpaxis/Fin-App
cd Fin-App
pip install -r requirements.txt


⸻

▶️ Usage

1. Fetch the News

from fetch_news import fetch_yahoo_finance_news
news = fetch_yahoo_finance_news("AAPL")

2. Classify Financial vs Non-Financial

from classifier import finance_classifier
finance_classifier(news)

3. Predict Sentiment

from sentiment import sentiment_predictor
sentiment_predictor(news)

4. Store Output

from db_utils import save_to_postgres
save_to_postgres(results)


⸻

🛠️ Technologies Used
	•	Transformers (HuggingFace)
	•	DistilBERT, FIN-BERT
	•	Python (3.9+)
	•	PostgreSQL
	•	SQLAlchemy / psycopg2
	•	Pandas, Matplotlib

⸻

🧭 Future Enhancements
	•	📊 Add a real-time Streamlit dashboard
	•	⚡ Incorporate stock price movement correlation
	•	🔔 Set up Telegram/WhatsApp alert system
	•	📡 Expand coverage to global markets

⸻

👤 Author

Aaditya Joshi
ML/NLP Engineer
GitHub: https://github.com/sharpaxis
