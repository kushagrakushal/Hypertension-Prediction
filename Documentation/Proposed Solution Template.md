Project Design Phase-I — Proposed Solution Template
Date: 08 March 2026
Team ID: Predictive Pulse Team
Project Name: Predictive Pulse: Harnessing ML for Blood Pressure Analysis
Maximum Marks: 2 Marks

S.No. | Parameter                        | Description
------|----------------------------------|-------------------------------------------------------
1.    | Problem Statement                | Hypertension (high blood pressure) is a silent killer.
      | (Problem to be solved)           | Most individuals are unaware of their risk until a
      |                                  | crisis occurs. There is no accessible, AI-driven tool
      |                                  | that integrates clinical symptoms, vitals, and personal
      |                                  | history to give instant stage-wise risk prediction.

2.    | Idea / Solution description      | Predictive Pulse: Flask web app powered by Logistic
      |                                  | Regression trained on 1,348 clinical records. Users
      |                                  | input 13 health parameters (demographics, vitals,
      |                                  | symptoms, lifestyle). Model predicts one of 4 stages
      |                                  | (Normal/Stage-1/Stage-2/Crisis) with confidence score
      |                                  | and personalised clinical recommendations.

3.    | Novelty / Uniqueness             | Combines 13 multi-domain features (not just BP readings).
      |                                  | 4-class output covering full hypertension spectrum
      |                                  | including Crisis stage. 95.2% accuracy; 100% Crisis
      |                                  | Recall. Confidence ring SVG visualisation for
      |                                  | transparency. Clinically-aligned recommendations per
      |                                  | stage. Professional medical-grade Navy+Teal UI.

4.    | Social Impact /                  | Enables early detection before irreversible damage.
      | Customer Satisfaction            | Bridges gap for rural/semi-urban users without clinic
      |                                  | access. Empowers individuals to take proactive health
      |                                  | decisions. Reduces burden on emergency care through
      |                                  | early intervention. Applicable for personal use,
      |                                  | community workers, clinics, and telemedicine platforms.

5.    | Business Model                   | Freemium web app (basic free; premium for history
      | (Revenue Model)                  | tracking). B2B SaaS license to hospitals and
      |                                  | telemedicine platforms. Health insurance risk scoring
      |                                  | API. Government / NGO contracts for community
      |                                  | screening programmes.

6.    | Scalability of the Solution      | Modular Flask architecture; cloud deployment (AWS/GCP)
      |                                  | for horizontal scaling. Retrainable with larger datasets.
      |                                  | Mobile app via React Native using same API. IoT
      |                                  | integration with BP monitors and wearables in future.