 <div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:111827,50:312e81,100:0f766e&height=190&section=header&text=StayOnTrack&fontSize=54&fontColor=F8FAFC&fontAlignY=42&desc=spot%20the%20risk.%20support%20the%20student.&descSize=17&descAlignY=68&descColor=A7F3D0" width="100%" alt="StayOnTrack — spot the risk, support the student" />

### an education-focused risk monitoring platform 🎓

A full-stack project exploring how student data can help educators identify academic risk signals and plan timely support.

[Repository](https://github.com/theoudar03/student-risk-predictor) · React + Express + MongoDB + Python ML service

</div>

---

## ✳️ the idea

Warning signs can be spread across attendance, grades, assignments and class participation. **StayOnTrack** brings student information and risk alerts into one application workflow so educators can review signals and consider timely support.

> The goal is to support earlier conversations and interventions — not to treat a model's output as a final judgement about a student.

## ⚡ what’s inside

- **Student data & risk alerts** — API routes for student records and current alerts.
- **Authentication** — a login endpoint for user authentication.
- **Risk recalculation integration** — the backend can call a separately configured ML service.
- **Web client** — React interface built with Vite, with routing, API calls and charting dependencies.
- **Deployment configuration** — Render Blueprint configuration and a Dockerfile are present in the repository.

*The real-world quality of predictions and educational outcomes have not been independently validated here. Check the current implementation and connected services before relying on any risk output.*

## 🧩 under the hood

| Layer | Stack |
|---|---|
| Frontend | React, Vite |
| Styling | Tailwind CSS |
| API / backend | Node.js, Express |
| Database | MongoDB, Mongoose |
| ML integration | Python, scikit-learn (risk recalculation) |
| Client libraries | Axios, React Router, Recharts |
| Deployment config | Docker, Render; Firebase configuration is also present |

```text
Student / Educator
        │
        ▼
 React + Vite client
        │  HTTP API
        ▼
 Node.js + Express API ───────► MongoDB
        │
        ▼
 Configured ML service
 (risk recalculation)
```

## 🛠️ run it locally

### prerequisites

- Node.js and npm
- MongoDB local instance or MongoDB Atlas
- Python, if you are running the ML service locally

### 1. clone the repository

```bash
git clone https://github.com/theoudar03/student-risk-predictor.git
cd student-risk-predictor
```

### 2. configure environment variables

Use the root `.env.example` as a reference. Create the environment files for your local setup.

**`server/.env`**

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=replace_with_a_long_random_secret
ML_SERVICE_URL=http://localhost:8001
```

**`client/.env`**

```env
VITE_API_BASE_URL=http://localhost:5000
```

Set `ML_SERVICE_URL` to the actual URL of your ML service. Never commit real credentials or secret keys.

### 3. install and start the backend

```bash
cd server
npm install
npm run dev
```

The backend's development script uses `nodemon`. Keep this terminal running.

### 4. install and start the frontend

Open a second terminal from the repository root:

```bash
cd client
npm install
npm run dev
```

Open the local URL printed by Vite.

### 5. create a frontend production build

```bash
cd client
npm run build
```

**ML service note:** the backend expects an ML service URL for risk recalculation. Configure and start that service separately before testing the related flow; confirm its current source files for the exact startup command and API contract.

## 🔌 API routes listed in the project docs

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/health` | Health check |
| `POST` | `/api/auth/login` | User authentication |
| `GET` | `/api/students` | Retrieve student records |
| `GET` | `/api/alerts` | Retrieve risk alerts |
| `POST` | `/api/admin/risk-recalculate` | Trigger risk recalculation |

These routes are based on the existing project documentation. Check the backend source for request formats, response schemas and authentication requirements.

## 🧭 responsible-use note

This is an evolving project. Before using it with real student records, validate model performance and limitations, secure endpoints, protect sensitive data, and test the complete frontend–API–database–ML flow. Risk scores should support human review, never replace it.

## 🪄 next up

- [ ] Add current UI screenshots and a short demo walkthrough.
- [ ] Document the ML service setup and input/output schema.
- [ ] Add API examples and error-response documentation.
- [ ] Add automated tests for key API and risk-recalculation flows.
- [ ] Document model evaluation and known limitations.

---

<div align="center">

made to help people notice the signal — and support the student. ✦

</div>
