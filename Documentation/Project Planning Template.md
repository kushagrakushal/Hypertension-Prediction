Project Planning Phase — Product Backlog, Sprint Planning, Stories, Story Points
Date: 08 March 2026
Team ID: Predictive Pulse Team
Project Name: Predictive Pulse: Harnessing ML for Blood Pressure Analysis
Maximum Marks: 8 Marks

Team Members:
- Urnisa Rakshit Rakshit  (dl.ai.u4aim25003@dl.students.amrita.edu)
- Kushagra Kanodia        (dl.ai.u4aid25077@dl.students.amrita.edu)
- Avusali Vivek Chary     (dl.ai.u4aid24010@dl.students.amrita.edu)
- Shreyansh Singh Singh   (dl.ai.u4aid24038@dl.students.amrita.edu)

--- PRODUCT BACKLOG & SPRINT SCHEDULE (4 Marks) ---

Sprint-1 | Project Setup    | USN-1  | As a developer, I can set up Flask environment with all
                                        dependencies (scikit-learn, joblib, numpy) installed.
                                        Story Points: 3 | Priority: High | Assignee: Kushagra K.

Sprint-1 | Project Setup    | USN-2  | As a developer, I can create the project folder structure:
                                        app.py, templates/, static/, logreg_model.pkl.
                                        Story Points: 2 | Priority: High | Assignee: Avusali V.

Sprint-1 | Data Collection  | USN-3  | As a data engineer, I can collect and validate the
                                        1,348-record hypertension clinical dataset.
                                        Story Points: 2 | Priority: High | Assignee: Urnisa R.

Sprint-1 | Data Collection  | USN-4  | As a developer, I can implement categorical encoding for
                                        all 13 input features using label mapping.
                                        Story Points: 2 | Priority: High | Assignee: Kushagra K.

Sprint-2 | Model Building   | USN-5  | As a data scientist, I can split data 80:20 and train
                                        7 ML algorithms, recording accuracy for each.
                                        Story Points: 3 | Priority: High | Assignee: Shreyansh S.

Sprint-2 | Model Selection  | USN-6  | As a data scientist, I can compare all 7 models and
                                        select Logistic Regression as best (95.2% acc).
                                        Story Points: 3 | Priority: High | Assignee: Shreyansh S.

Sprint-2 | Model Deployment | USN-7  | As a developer, I can serialise model + scaler into
                                        logreg_model.pkl bundle using Joblib.
                                        Story Points: 2 | Priority: High | Assignee: Urnisa R.

Sprint-3 | Flask Backend    | USN-8  | As a user, I can submit 13-field health form and receive
                                        a hypertension stage prediction via POST /predict.
                                        Story Points: 3 | Priority: High | Assignee: Kushagra K.

Sprint-3 | Flask Backend    | USN-9  | As a developer, I can implement encode_input() pipeline
                                        with StandardScaler on 5 ordinal features.
                                        Story Points: 2 | Priority: High | Assignee: Kushagra K.

Sprint-4 | Frontend         | USN-10 | As a user, I see result banner with stage name,
                                        confidence ring SVG, and colour-coded priority label.
                                        Story Points: 3 | Priority: High | Assignee: Team

Sprint-4 | Frontend         | USN-11 | As a user, I receive personalised clinical
                                        recommendations with action items for my predicted stage.
                                        Story Points: 2 | Priority: High | Assignee: Team

Sprint-4 | Testing          | USN-12 | As a QA, I can run 5 end-to-end test cases validating
                                        all prediction classes and error handling.
                                        Story Points: 2 | Priority: High | Assignee: Team

--- PROJECT TRACKER, VELOCITY & BURNDOWN CHART (4 Marks) ---

Sprint   | Total Pts | Duration | Start Date  | End Date    | Pts Completed | Release Date
---------|-----------|----------|-------------|-------------|---------------|-------------
Sprint-1 |     9     |  7 Days  | 10 Feb 2026 | 16 Feb 2026 |       9       | 16 Feb 2026
Sprint-2 |     7     |  7 Days  | 17 Feb 2026 | 23 Feb 2026 |       7       | 23 Feb 2026
Sprint-3 |     8     |  7 Days  | 24 Feb 2026 | 02 Mar 2026 |       8       | 02 Mar 2026
Sprint-4 |     7     |  6 Days  | 03 Mar 2026 | 08 Mar 2026 |       7       | 08 Mar 2026

Velocity:
Total Story Points = 31 | Total Sprint Days = 27
Average Velocity (AV) = 31 / 27 = 1.15 story points per day

Burndown Data:
Day 0  (10 Feb 2026) → 31 story points remaining
Day 7  (16 Feb 2026) → 22 remaining  (Sprint-1 complete: -9 pts)
Day 14 (23 Feb 2026) → 15 remaining  (Sprint-2 complete: -7 pts)
Day 21 (02 Mar 2026) →  7 remaining  (Sprint-3 complete: -8 pts)
Day 27 (08 Mar 2026) →  0 remaining  (Sprint-4 complete: -7 pts) ✓ PROJECT COMPLETE