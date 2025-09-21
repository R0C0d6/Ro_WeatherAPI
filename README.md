
# Weather Dashboard with AWS S3

This project is a simple **Weather API Dashboard** built with **Python**, **OpenWeather API**, and **AWS S3**.

It fetches live weather data for multiple cities and automatically saves the results as JSON files in an **Amazon S3 bucket**.

---

## Features

* Fetch current weather data from [OpenWeather API](https://openweathermap.org/api).
* Supports multiple cities (default: Philadelphia, Seattle, New York).
* Automatically creates an S3 bucket (if it doesn’t exist).
* Saves weather data into S3 in timestamped JSON files.
* Uses environment variables for API keys and AWS credentials (secure setup).

---

## Tech Stack

* **Python 3.8+**
* **Boto3** (AWS SDK for Python)
* **Requests** (for API calls)
* **OpenWeather API**
* **AWS S3**

---

## 📂 Project Structure

```
weather-dashboard-demo/
│── src/
│   └── weather_dashboard.py   # Main application code
│── .env                       # Environment variables (not committed)
│── requirements.txt           # Dependencies
│── README.md                  # Project documentation
```

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/weather-dashboard-demo.git
cd weather-dashboard-demo
```

### 2. Create a virtual environment (optional but recommended)

```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

If you don’t have `requirements.txt` yet, generate it with:

```bash
pip freeze > requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the project root with the following content:

```
OPENWEATHER_API_KEY=your_openweather_api_key_here
AWS_BUCKET_NAME=your-unique-s3-bucket-name
```

**Important:** Never commit your `.env` file to GitHub.

### 5. Configure AWS CLI

Make sure your AWS credentials are set up:

```bash
aws configure
```

Enter:

* AWS Access Key ID
* AWS Secret Access Key
* Default region (e.g., `us-east-1`)

### 6. Run the project

```bash
python src/weather_dashboard.py
```

---

## Example Output

```
Creating bucket my-weather-dashboard-bucket
Successfully created bucket my-weather-dashboard-bucket

Fetching weather for Philadelphia...
Temperature: 63.36°F
Feels like: 63.19°F
Humidity: 81%
Conditions: overcast clouds
Successfully saved data for Philadelphia to S3
```

---

## Security Notes

* Do **not** hardcode AWS keys or API keys in your Python files.
* Always use `.env` for secrets and add `.env` to `.gitignore`.
* Rotate AWS credentials if they were exposed accidentally.

---

## Future Improvements

* A simple frontend dashboard (React or Streamlit).
* Store historical weather trends in DynamoDB.
* Add error logging and retries for failed API calls.
* Support more cities or dynamic city input.

---

## License

This project is open-source and available under the **MIT License**.

---
