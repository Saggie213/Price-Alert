<div align="center">
  <br />
    <img src="public/images/banner.png" alt="Project Banner">
  <br />

  <div>
    <img src="https://img.shields.io/badge/-Web_Scraping-black?style=for-the-badge&logoColor=white&color=FF0000" />
    <img src="https://img.shields.io/badge/-Next_JS-black?style=for-the-badge&logoColor=white&logo=nextdotjs&color=000000" />
    <img src="https://img.shields.io/badge/-Tailwind_CSS-black?style=for-the-badge&logoColor=white&logo=tailwindcss&color=06B6D4" />
    <img src="https://img.shields.io/badge/-MongoDB-black?style=for-the-badge&logoColor=white&logo=mongodb&color=47A248" />
    <img src="https://img.shields.io/badge/-Nodemailer-black?style=for-the-badge&logoColor=white&color=EA4335" />
    <img src="https://img.shields.io/badge/-Bright_Data-black?style=for-the-badge&logoColor=white&color=F57C00" />
  </div>

  <h3 align="center">Price Alert – E-commerce Price Tracking & Notification System</h3>

  <div align="center">
    Track product prices automatically and receive real-time email alerts when prices drop or items go back in stock.
  </div>
</div>

---

## 📋 Table of Contents

1. 🤖 Introduction  
2. ⚙️ Tech Stack  
3. 🔋 Features  
4. 🏗️ System Architecture  
5. 🧠 Core Logic  
6. 🤸 Quick Start  
7. 📂 Project Structure  
8. 🚀 Future Improvements  

---

## 🤖 Introduction

Price Alert is a full-stack e-commerce tracking application built using Next.js 14, MongoDB, and automated scraping with Bright Data.

Users can paste Amazon product URLs and:

- Track price fluctuations
- Monitor stock availability
- Receive email alerts for major price drops
- Automatically track historical price trends

The system runs background cron jobs to continuously monitor products without manual checking.

---

## ⚙️ Tech Stack

### Frontend
- Next.js 14
- React
- Tailwind CSS
- Headless UI

### Backend
- Next.js Server Actions
- TypeScript
- MongoDB + Mongoose

### Automation & Services
- Bright Data Proxy (Web Unlocker)
- Axios + Cheerio (Web Scraping)
- Nodemailer (Email Notifications)
- Cron Jobs (Automated Monitoring)

---

## 🔋 Features

👉 Product scraping from Amazon URLs  
👉 Historical price tracking  
👉 Lowest, highest & average price calculation  
👉 Discount percentage detection  
👉 Email alerts for:
   - Lowest price ever  
   - Back in stock  
   - Discount threshold met (≥ 40%)  
👉 Automated background cron job execution  
👉 Responsive and clean UI  
👉 Modular & scalable architecture  

---

## 🏗️ System Architecture

1. User submits product URL.
2. Product data is scraped and stored in MongoDB.
3. Users subscribe using their email.
4. Cron job runs periodically.
5. Latest product data is scraped.
6. System compares:
   - Current price vs lowest historical price  
   - Stock status change  
   - Discount threshold  
7. If conditions match → Email is triggered.

---

## 🧠 Core Logic

### Price History Tracking

Each product maintains:

- `priceHistory[]`
- `lowestPrice`
- `highestPrice`
- `averagePrice`

Prices are recalculated dynamically after each scrape.

---

### Notification Trigger Conditions

| Condition | Notification Type |
|------------|------------------|
| New price < historical lowest | LOWEST_PRICE |
| Previously out of stock → now available | CHANGE_OF_STOCK |
| Discount ≥ 40% | THRESHOLD_MET |

---

### Email System

- HTML-based dynamic email templates
- Multi-user email support
- Automated delivery via Nodemailer

---

## 🤸 Quick Start

### Prerequisites

- Node.js
- npm
- MongoDB Atlas account
- Bright Data account

---

### Clone Repository

```bash
git clone YOUR_REPOSITORY_LINK
cd YOUR_PROJECT_FOLDER
