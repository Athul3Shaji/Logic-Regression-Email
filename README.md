# Logic-Regression-Email
Using Logic regression model find the email Safe or Phishing


📧 Email Phishing Detection API
A high-performance Email Safety Detection API built with FastAPI, Logic Regression, and Redis!
Quickly analyze email content and determine if it’s Safe or Phishing in real-time.

🚀 Features
🔥 FastAPI: Ultra-fast and lightweight web API framework.

🧠 Logic Regression Model: Lightweight and interpretable Machine Learning model for classification.

⚡ Redis Integration: Boost performance with fast in-memory storage for:

Caching predictions

Reducing redundant model computations

Improving API response times

📈 Easy Extensibility: Train and update the model with new email samples effortlessly.

🛠️ Tech Stack
Python 3.11+

FastAPI

Scikit-learn (for Logistic Regression Model)

Redis (as caching backend)

Uvicorn (ASGI server)

🧩 How It Works
User submits the email text to the API.

The API first checks if a prediction already exists for the same email text in Redis Cache.

If found → Return the cached result (Safe or Phishing) instantly.

If not found → Use Logic Regression Model to predict and store the result in Redis for future use.

✅ Safe
❌ Phishing

🛠️ Setup Instructions
1. Clone the repository

git clone https://github.com/your-username/email-phishing-detection-api.git
cd email-phishing-detection-api


2. Create a Virtual Environment

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

3. Install Dependencies

pip install -r requirements.txt
4. Start Redis Server
Make sure Redis is installed and running locally:
redis-server
(or use Docker if preferred)
docker run -p 6379:6379 redis


5. Run the FastAPI server
uvicorn main:app --reload


📨 API Endpoint

Method	URL	Description
POST	/predict	Predict if an email is Safe or Phishing


Example Request

POST /predict_email
Content-Type: application/json

{
  "email_text": "Dear user, click here to claim your prize!"
}

Example Response

{
  "prediction": "Phishing",
  "confidence": 0.92
}


💡 Why Redis?
Ultra-Fast Lookups: Redis stores previously seen emails and their predictions, making repeated predictions instantaneous.

Reduced Load: Avoids redundant model computations.

Scalable Caching Layer: Ideal for high-traffic scenarios.

Persistence: Optional disk persistence ensures cache survives server restarts.

🔥 Future Enhancements
Add authentication for API users.

Build a dashboard to monitor phishing detection stats.

Introduce advanced models (like transformers) for better accuracy.

Integrate rate limiting with Redis to prevent abuse.

📢 Contributing
Pull requests are welcome!
For major changes, please open an issue first to discuss what you would like to change.

📄 License
MIT License

🙌 Acknowledgements
FastAPI Documentation

Redis Documentation

Scikit-learn Documentation

“An ounce of prevention is worth a pound of cure — Protect your inbox today!”