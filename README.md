# GitHub Webhook Integration Project 🚀

This project demonstrates a **real-time webhook system** using GitHub Actions, Flask, MongoDB Atlas, and ngrok.

---

## 🔧 Project Structure

| Repo | Description |
|------|-------------|
| [`action-repo`](https://github.com/Zainaafreen/action-repo) | Contains the GitHub Action that triggers a webhook. |
| `webhook-repo` | Flask app that receives webhook data and displays it on a dashboard. |

---

## 🎯 Features

✅ GitHub Actions workflow triggers on push / pull request  
✅ Sends webhook to Flask app via `ngrok`  
✅ Flask app receives & stores data in **MongoDB Atlas**  
✅ Frontend dashboard shows recent GitHub activity  
✅ Auto-refreshes every 15 seconds  

---

## 🚀 Setup Instructions

### 1️⃣ Clone both repos:

```bash
git clone https://github.com/Zainaafreen/action-repo.git
git clone https://github.com/Zainaafreen/webhook-repo.git
