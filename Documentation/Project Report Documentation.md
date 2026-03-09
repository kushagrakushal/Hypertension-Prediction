Project Report — Predictive Pulse: Harnessing ML for Blood Pressure Analysis
Team: Urnisa Rakshit Rakshit, Kushagra Kanodia, Avusali Vivek Chary, Shreyansh Singh Singh
Completion Date: 08 March 2026

1. PROJECT TITLE
Predictive Pulse — AI-Powered Hypertension Risk Detection & Clinical Recommendation System

2. PROJECT DESCRIPTION
System Overview  : Flask web app + Logistic Regression ML model for 4-class hypertension risk prediction
Problem Domain   : Cardiovascular health — early hypertension detection before clinical crisis occurs
Core Technology  : Python 3.x, Flask, Scikit-learn, Joblib, NumPy, HTML5/CSS3
Key Capabilities : 13-feature input, 4-stage prediction (Normal/Stage-1/Stage-2/Crisis),
                   confidence score, personalised clinical recommendations
Target Users     : Adults aged 35-65 at risk, rural health workers, clinics, telemedicine platforms
Real-world Relevance: Hypertension affects 1.28 billion adults globally; 46% are unaware (WHO 2023)

3. APPLICATION SCENARIOS / USE CASES
- Personal Use    : Individual submits BP readings + symptoms at home to check risk before doctor visit
- Rural Healthcare: Community health worker screens patients at camp using tablet — no specialist needed
- Telemedicine    : Integrated as pre-consultation screener; doctors receive patient risk stage before call
- Insurance       : Provider uses prediction API for cardiovascular risk scoring during policy onboarding

4. TECHNICAL ARCHITECTURE OVERVIEW
- Frontend  : HTML5 + CSS3 (DM Serif/Sans/JetBrains Mono via Google Fonts CDN) + Jinja2 templates
- Backend   : Flask (Python) — GET / renders form; POST /predict runs ML pipeline and returns result
- ML Engine : Scikit-learn LogisticRegression loaded from logreg_model.pkl via Joblib at app startup
- Preprocess: Label encoding (13 features) + StandardScaler on 5 ordinal features only
- Artefact  : logreg_model.pkl — Joblib dict bundle containing {model, scaler}
- Database  : None — stateless prediction; no persistent storage in current version
- External  : Google Fonts CDN for typography; no other external API dependencies
- Deployment: python app.py (port 5000); production via Gunicorn + Nginx

5. PREREQUISITES
5.1 Software: Python 3.8+, pip, VS Code / PyCharm, Web Browser (Chrome/Firefox), Git
5.2 Libraries: Flask 2.x, scikit-learn 1.x, joblib 1.x, numpy 1.x, Jinja2 3.x
5.3 Hardware : Any PC/laptop with 4GB RAM, 2GHz CPU; internet only for Google Fonts CDN

6. PRIOR KNOWLEDGE REQUIRED
- Python (OOP, functions, dicts, numpy arrays)
- Flask routing & Jinja2 templating
- Scikit-learn API: fit(), predict(), predict_proba(), StandardScaler, LogisticRegression
- HTML5 form handling, CSS3 grid/flexbox, SVG for confidence ring visualisation
- ML fundamentals: classification, feature encoding, cross-validation, overfitting analysis

7. PROJECT OBJECTIVES
- Technical    : Build 4-class ML pipeline achieving >95% accuracy on 1,348-record dataset
- Performance  : Achieve 100% Recall on Hypertensive Crisis — zero false negatives for emergencies
- Deployment   : Deliver fully functional Flask web app accessible via browser with live demo link
- Clinical     : Provide evidence-based, stage-specific recommendations aligned with medical guidelines
- Learning     : Demonstrate end-to-end ML pipeline from preprocessing to production web deployment

8. SYSTEM WORKFLOW
1. User opens app and fills 5-section form (Demographics, History, Symptoms, Vitals, Lifestyle)
2. Browser sends HTTP POST to /predict with 13 form field values
3. Flask validates all required fields; flashes error message if any field is empty
4. encode_input() maps all string values to numeric codes using 7 predefined mapping dicts
5. StandardScaler scales 5 ordinal features (Age, Severity, Diagnosis Time, Systolic, Diastolic)
6. model.predict() returns class 0-3; predict_proba() returns confidence percentage
7. stage_map, color_map, recommendations dict map prediction to display content
8. Jinja2 renders index.html with result banner: stage title, confidence ring SVG, recommendations

9. MILESTONE 1: REQUIREMENT ANALYSIS & SYSTEM DESIGN
9.1 Problem    : Hypertension is silent; no accessible AI tool integrates symptoms+vitals+history
9.2 Functional : Form input (13 fields), ML prediction, confidence score, stage recommendations
9.3 Non-Functional: <2s response time, mobile-responsive UI, graceful error handling
9.4 Design     : Stateless Flask app; all state in single POST request; no database required
9.5 Stack      : Flask for simplicity; Scikit-learn for ML; Joblib for serialisation; Jinja2 for UI

10. MILESTONE 2: ENVIRONMENT SETUP & INITIAL CONFIGURATION
  pip install flask scikit-learn joblib numpy
  Folder: app.py | logreg_model.pkl | templates/index.html | static/style.css | README.md

11. MILESTONE 3: CORE SYSTEM DEVELOPMENT
Feature 1 — encode_input(): Maps 13 form fields to numeric array using 7 label maps (gender,
  age, history, severity, diagnosis time, systolic, diastolic). Returns list of 13 numeric values.
Feature 2 — /predict route: Validates inputs, calls encode_input(), scales ordinal features with
  StandardScaler, runs model.predict() + predict_proba(), returns rendered template with results.
Feature 3 — Result Banner UI: SVG confidence ring (stroke-dasharray = confidence/100 * 163.4),
  colour-coded stage (green/amber/orange/red), recommendations list with action items per stage.

12. MILESTONE 4: INTEGRATION & OPTIMIZATION
12.1 Integration  : encode_input() feeds into scaler.transform() then model.predict()
12.2 Optimisation : Only 5 ordinal features scaled; 8 binary features pass through unchanged
12.3 Security     : secret_key set; inputs validated server-side; no SQL / no injection surface
12.4 Error Handling: try/except on model load; field validation with flash(); fallback demo mode

13. MILESTONE 5: TESTING & VALIDATION
Test Cases:
TC-01 | Gender=M, Age=35-50, Systolic=130+, Diastolic=100+, Severity=Severe | HYPERTENSIVE CRISIS  | Pass
TC-02 | Gender=F, Age=18-34, Systolic=111-120, Diastolic=70-80, Severity=Mild, all No | NORMAL    | Pass
TC-03 | Missing required field (Gender empty)                                | Flash error message  | Pass
TC-04 | Age=65+, History=Yes, Medication=Yes, Systolic=130+, Diastolic=91-100 | HTN Stage-2        | Pass
TC-05 | All lowest-risk values                                               | NORMAL + high conf%  | Pass

Performance Metrics (AI/ML):
- Accuracy       : 95.2%
- Macro F1 Score : 0.95
- Crisis Recall  : 100%  (zero false negatives for emergency class)
- Avg Precision  : ~95%
- Dataset        : 1,348 validated clinical records
- Algorithms Compared: 7 (LR, SVM, RF, DT, KNN, NB, GBM) — LR selected as best

14. DEPLOYMENT
14.1 Architecture: Single-server Flask app; static files via Flask or Nginx
14.2 Platform    : Local Python server; production via Gunicorn + Nginx on Linux VPS or cloud VM
14.3 Steps       : git clone → pip install -r requirements.txt → python app.py → open localhost:5000
14.4 Production  : Set debug=False, use env variable for secret_key, serve static files via Nginx

15. PROJECT STRUCTURE
Hypertension-Prediction/
├── app.py                ← Flask app, routes, ML pipeline, encode_input()
├── logreg_model.pkl      ← Joblib bundle: {model: LogReg, scaler: StandardScaler}
├── templates/
│   └── index.html        ← Jinja2 template (form + result banner)
├── static/
│   └── style.css         ← Navy/Teal/Ivory design system, responsive layout
└── README.md             ← Project overview and setup instructions

16. RESULTS
- Output     : 4-class prediction (Normal/Stage-1/Stage-2/Crisis) + confidence % + recommendations
- Performance: 95.2% accuracy, Macro F1=0.95, 100% Crisis Recall on 1,348-record dataset
- Demo Link  : https://drive.google.com/file/d/136irYzxj-gSAsv3l9mBbbCpoUEMI5kR0/view?usp=drive_link

17. ADVANTAGES & LIMITATIONS
Advantages:
- 95.2% accuracy with 100% Crisis Recall — no emergency missed; clinically safe
- Covers full hypertension spectrum (Normal → Crisis) in one accessible tool
- No installation required — browser-based; works on any device
- Explainable model (Logistic Regression) — coefficients interpretable by clinicians
- Instant results with personalised stage-specific clinical action items

Limitations:
- Limited to 1,348-record dataset — needs larger diverse data for generalisation
- BP inputs are range-based categories, not exact mmHg values
- No persistent user history or longitudinal BP trend tracking
- No integration with wearable devices or EHR systems yet

18. FUTURE ENHANCEMENTS
- Retrain on larger datasets (NHANES, WHO HEARTS programme data)
- Add BP trend dashboard with visualisation charts (Chart.js / D3.js)
- Deploy on AWS/GCP with CI/CD pipeline for production scalability
- Build React Native mobile app using same Flask prediction API
- Integrate with IoT BP monitors and smartwatch sensor APIs
- Add multi-language support for Indian regional languages

19. CONCLUSION
Predictive Pulse successfully demonstrates an end-to-end ML pipeline for hypertension risk
detection. The system achieves 95.2% accuracy with 100% Crisis Recall using Logistic
Regression on 1,348 clinical records. The Flask web app provides a professional clinical UI
with personalised recommendations, making early hypertension detection accessible to
individuals and healthcare workers alike. The project bridges the gap between patients
and clinical care, offering a scalable, evidence-based digital health solution.

20. APPENDIX
GitHub    : https://github.com/kushagrakushal/Hypertension-Prediction
Demo      : https://drive.google.com/file/d/136irYzxj-gSAsv3l9mBbbCpoUEMI5kR0/view?usp=drive_link
Dataset   : 1,348 clinical records | 13 features | 4 target classes
Model     : logreg_model.pkl — Joblib bundle {model: LogisticRegression, scaler: StandardScaler}
Team      : Urnisa Rakshit Rakshit | Kushagra Kanodia | Avusali Vivek Chary | Shreyansh Singh Singh