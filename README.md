# Website-Crawler
# 🌐 Website Crawler with Google Drive Integration (GCP + Python)

## 📘 Overview

This project is a cloud-integrated **Website Crawler** built using **Python**, **Google Drive API**, and **Google Cloud Platform (GCP)**.

### 🎯 Main Features:
- ✅ Reads a starting URL from a `.txt` file stored in **Google Drive**
- 🔁 Crawls internal links recursively from the URL (limited depth to avoid overload)
- 📄 Saves the list of internal links in a `.txt` file
- ☁️ Uploads the result back to Google Drive and shares it with the user
- 🔐 Uses GCP **Service Account** for secure and automated access to Google APIs

---

## 🧱 Architecture & Flow

1. **User uploads `url.txt`** to Google Drive (contains 1 URL)
2. **Python reads file from Drive** using Drive API and Service Account
3. **Crawler scans internal links** (max depth = 2)
4. **Result is uploaded** to Google Drive as `crawled_links.txt`
5. **File is shared with user's email**

---

## 📦 Tech Stack

| Tool/Platform              | Purpose                                     |
|----------------------------|---------------------------------------------|
| Google Cloud Platform (GCP)| Cloud and Service Account Management        |
| Google Drive API           | Read and write files in Google Drive        |
| Python                     | Core logic and scripting                    |
| BeautifulSoup (bs4)        | HTML parsing to extract links               |
| Requests                   | HTTP requests to websites                   |
| Google Colab (optional)    | Development and testing environment         |

---

## 🚀 Setup Guide

### ✅ STEP 1: GCP & Service Account

1. Create a new GCP project  
2. Enable **Google Drive API**  
3. Create a **Service Account**  
4. Grant it access to Drive (Editor or Owner permission)  
5. Download the **JSON key file** (save as `service_account.json`)  

---

### ✅ STEP 2: Google Drive Setup

1. Upload a file named `url.txt` (e.g., contains `https://www.w3schools.com`)  
2. Right-click → Share → Add the **Service Account email**  
3. Copy the **File ID** from the URL (`https://drive.google.com/file/d/FILE_ID/view`)  

---

### ✅ STEP 3: Python Environment

1. Upload the following files to Google Colab or your local machine:
   - `main.py`
   - `service_account.json`

2. Create a `requirements.txt` file:

```txt
google-api-python-client
google-auth
google-auth-httplib2
google-auth-oauthlib
requests
beautifulsoup4
