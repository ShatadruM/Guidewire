# 🚀 ParaGuard – AI Parametric Insurance for Gig Workers

ParaGuard is an automated, zero-touch insurance platform designed to safeguard the livelihoods of India's delivery partners from income loss caused by external disruptions. By leveraging real-time weather data and AI-driven fraud detection, it provides instant payouts during periods when factors like extreme weather or curfews prevent riders from working.

---

## 📋 Table of Contents

- [Persona & Workflow](#-persona--workflow)
- [Financial Model](#-financial-model)
- [Technical Architecture](#-technical-architecture)
- [Microservice File Structures](#-microservice-file-structures)
- [AI/ML Integration](#-aiml-integration)
- [Tech Stack](#-tech-stack)

---

## 👤 Persona & Workflow

### Target Persona
The **Q-Commerce Rider** (for example: Zepto, Blinkit delivery partners).

### The Problem
High-frequency, short-distance deliveries are often halted during heavy waterlogging or extreme heat conditions such as **45°C+**, resulting in a **20–30% drop in weekly earnings**.

### The Safety Net
ParaGuard automatically triggers coverage when local weather sensors exceed predefined safety thresholds.

### Application Workflow

#### 1. Onboarding
The rider connects their delivery platform ID, and the AI calculates their **Average Weekly Wage**.

#### 2. Weekly Subscription
The user pays a **dynamic premium every Sunday** for coverage during the upcoming week.

#### 3. Real-time Monitoring
The system continuously polls **weather APIs** and **social/disruption APIs** for issues within the user’s specific geo-fenced area.

#### 4. Auto-Claim
If a disruption is detected, the platform automatically initiates a claim.  
No manual filing is required.

#### 5. AI Verification
Fraud detection models verify that the rider was genuinely in the affected zone and was unable to work.

#### 6. Instant Payout
Funds are disbursed directly to the user’s wallet through a simulated payment gateway.

---

## 💰 Financial Model

### Weekly Pricing
All premiums and payouts are structured on a **weekly basis** to align with gig worker payout cycles.

### Dynamic Premium Engine
Premium amounts are adjusted using the **7-day weather forecast**.  
For example, if the forecast predicts a **70% chance of heavy rain**, the premium increases slightly to reflect the higher risk.

### Coverage Scope
ParaGuard covers **loss of income only**.

It does **not** provide coverage for:
- Health
- Life
- Accidents
- Vehicle repairs

---

## 🏗️ Technical Architecture

ParaGuard follows a **Microservices Architecture** to ensure:
- Scalability
- Independent deployment
- Better fault isolation
- Separate handling of AI/ML workloads

---

## 🛠️ Tech Stack

### Backend
- Node.js (Express)
- Java (Spring Boot)

### AI/ML
- Python
- FastAPI
- Scikit-learn

### Databases
- PostgreSQL (Transactional data)
- MongoDB (Persona data and logs)
- Redis (Real-time triggers and caching)

### Messaging
- RabbitMQ / AWS SQS (Asynchronous communication)

### Frontend
- React (Web Dashboard)

---

## 📂 Microservice File Structures

### 1. User & Persona Service (Node.js / MongoDB)
Responsible for onboarding users and storing delivery partner profiles.

```plaintext
user-service/
├── src/
│   ├── controllers/      # Onboarding logic
│   ├── models/           # MongoDB Schema (Persona/Earnings)
│   ├── routes/           # API Endpoints
│   └── services/         # Integration with Platform APIs (Mocks)
├── tests/
└── server.js
```
### 2. Policy & Premium Service (Java / PostgreSQL)
Manages weekly policies, contracts, and premium calculations.

```plaintext
policy-service/
├── src/main/java/com/paraguard/
│   ├── controller/       # Premium & Policy API
│   ├── entity/           # JPA Entities (WeeklyPolicy)
│   ├── repository/       # PostgreSQL Repositories
│   └── service/          # Dynamic Pricing Logic
└── src/main/resources/
    └── application.properties
```
### 3. Monitoring Service (Node.js / Redis)
Acts as the parametric trigger engine by polling external APIs.

```plaitext
monitor-service/
├── src/
│   ├── cron/             # API Polling Jobs (Weather/Traffic)
│   ├── triggers/         # Threshold Logic (e.g., Rain > 30mm)
│   └── utils/            # Redis Client
├── mock-apis/            # Mocked Weather/Social data
└── app.js
```
### 4. Claims & Fraud Service (Python / FastAPI)
The AI engine responsible for anomaly detection and claim validation.

```plaintext
claims-ai-service/
├── models/               # Saved ML Models (.pkl or .h5)
├── src/
│   ├── api/              # Claim Validation Endpoints
│   ├── core/             # Fraud Logic (GPS Spoofing Check)
│   └── ml_engine/        # Risk Profiling Scripts
├── main.py
└── requirements.txt
```


## 🤖 AI/ML Integration

ParaGuard uses AI and machine learning to make the platform smarter, faster, and more reliable. These models help assess risk, prevent fraud, and support dynamic pricing decisions in real time.

### Risk Profiling
Historical delivery and earnings data are analyzed to understand how vulnerable a rider is to specific types of disruptions, such as heavy rainfall, waterlogging, or extreme heat. This helps the system personalize risk evaluation for each user.

### Fraud Detection
Anomaly detection models are used to flag suspicious claim behavior before payout. The system checks multiple signals together to validate whether a claim is genuine.

Examples of fraud indicators include:
- GPS spoofing
- False disruption claims
- Unusual rider activity patterns
- Location and event mismatches

By cross-verifying weather conditions, geo-fenced rider presence, and platform activity, ParaGuard reduces the risk of false payouts.

### Dynamic Pricing
Predictive models adjust weekly premiums based on hyper-local risk factors. These may include short-term weather forecasts, past disruption frequency, and area-specific delivery vulnerability. This allows premiums to remain fair while still reflecting actual exposure to risk.

## ✅ Summary

ParaGuard brings together parametric insurance, AI-driven validation, and a microservices-based architecture to build a zero-touch protection layer for gig workers. The platform is designed to automatically detect disruption events, validate claims intelligently, and deliver fast payouts with minimal manual intervention. By focusing on measurable external triggers and loss-of-income coverage, ParaGuard offers a practical and scalable safety net for delivery riders.
