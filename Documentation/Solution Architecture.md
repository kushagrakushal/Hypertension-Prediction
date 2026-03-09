Project Design Phase-I — Solution Architecture
Date: 08 March 2026
Team ID: Predictive Pulse Team
Project Name: Predictive Pulse: Harnessing ML for Blood Pressure Analysis
Maximum Marks: 4 Marks

Solution Architecture — Predictive Pulse: Harnessing ML for Blood Pressure Analysis
Figure: Data and request flow of the Predictive Pulse hypertension risk detection system

Architecture Layers:

Layer 1 — User / Browser
  Patient opens web app, fills 5-section health form (13 fields: demographics,
  history, symptoms, vitals, lifestyle) and submits for prediction.

Layer 2 — Flask Frontend
  Jinja2 HTML template renders form (index.html). CSS design system
  (Navy/Teal/Ivory, DM Serif + DM Sans + JetBrains Mono) handles responsive layout.

Layer 3 — Flask Backend
  app.py: GET / serves the assessment form. POST /predict validates all 13
  required inputs, calls encode_input(), runs ML pipeline, returns rendered result.

Layer 4 — Preprocessing
  encode_input() maps 13 string values to numeric codes using 7 label dicts.
  StandardScaler scales 5 ordinal features (Age, Severity, Diagnosis Time,
  Systolic BP, Diastolic BP). Binary features passed through unchanged.

Layer 5 — ML Engine
  LogisticRegression.predict() → class 0–3.
  predict_proba() → confidence %. Loaded from logreg_model.pkl via Joblib.

Layer 6 — Model Artefact
  logreg_model.pkl: Joblib bundle {model: LogisticRegression, scaler: StandardScaler}.
  Loaded once at app startup; shared across all requests.

Layer 7 — Output Rendering
  stage_map, color_map, recommendations dict map class to display content.
  SVG confidence ring and colour-coded result banner rendered via Jinja2.

Input Features (13):
  Gender | Age | Family History | Currently a Patient | Taking BP Medication |
  Symptom Severity | Breath Shortness | Visual Changes | Nose Bleeding |
  Time Since Diagnosis | Systolic BP | Diastolic BP | Controlled Diet

Output Classes:
  Class 0: NORMAL            — colour: #22c55e (green)
  Class 1: HYPERTENSION Stage-1 — colour: #f59e0b (amber)
  Class 2: HYPERTENSION Stage-2 — colour: #f97316 (orange)
  Class 3: HYPERTENSIVE CRISIS  — colour: #ef4444 (red)

