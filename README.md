# GitHub Webhook Integration Project 🚀

This project demonstrates a real-time GitHub Actions to Flask integration using Webhooks, MongoDB, and ngrok.

## 🔧 Tech Stack

- **GitHub Actions:** Sends webhooks on every push/pull request
- **Flask App:** Receives and logs events
- **MongoDB Atlas:** Stores webhook data
- **ngrok:** Exposes localhost to the internet for webhook access

## 📂 Repositories

- **action-repo:** Contains the GitHub Action workflow file
- **webhook-repo:** Contains the Flask app with MongoDB integration

---

## ✅ How It Works

1. You push to `action-repo`.
2. GitHub triggers the `webhook_trigger.yml` action.
3. That action sends a POST request (webhook) to your Flask app.
4. Flask receives it and stores the data in MongoDB.
5. Your web dashboard displays all incoming events live!

---

## ▶️ How to Run

1. **Clone** both repos:
   ```bash
   git clone https://github.com/yourusername/action-repo
   git clone https://github.com/yourusername/webhook-repo
