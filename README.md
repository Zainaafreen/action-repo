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

   
# GitHub Action Webhook Trigger

This repository contains a GitHub Action that sends webhook events (on push, pull request, or manual trigger) to a Flask backend server.

## 📦 What It Does

- On every push, pull request, or workflow dispatch, this GitHub Action triggers a webhook.
- The webhook sends:
  - Action type (push, PR, etc.)
  - Username of the actor
  - Branches involved
  - Timestamp
- It sends this info to your Flask app via an ngrok public URL.

## 🧠 How It Works

The Action is defined in:
.github/workflows/webhook_trigger.yml


It looks like this:

```yaml
name: Send Webhook to Flask

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  send-event:
    runs-on: ubuntu-latest
    steps:
    - name: Send webhook to Flask app
      run: |
        curl -X POST https://<your-ngrok-link>.ngrok-free.app/webhook \
        -H "Content-Type: application/json" \
        -d '{
          "action": "${{ github.event_name }}",
          "author": "${{ github.actor }}",
          "from_branch": "${{ github.head_ref || github.ref_name }}",
          "to_branch": "${{ github.base_ref || github.ref_name }}",
          "timestamp": "${{ github.event.head_commit.timestamp || github.event.pull_request.updated_at }}"
        }'
Trigger test from Zaina 
