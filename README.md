# Machine Learning for Global Mission Assessment (Master's Thesis)

**[View Full Thesis PDF (130 pages)](TFM_Airbus_Final.pdf)**

### Project Summary
[cite_start]A 6-month Master's Thesis project in collaboration with Airbus, developing a Machine Learning system (Python, Scikit-learn) to automate the debriefing of complex military missions, classifying the success or failure of flight actions[cite: 8, 53].

---

### 1. The Problem (Business Understanding)
[cite_start]The manual *debriefing* process for military missions is "tedious and complex," time-consuming, and difficult to scale with the increasing amount of data from flight recorders[cite: 18, 25, 49]. [cite_start]The objective was to design and prove the feasibility of an automated tool using Machine Learning to assess missions, reducing time and cost[cite: 50, 118, 2212].

### 2. The Solution (My Methodology)
[cite_start]I designed a hierarchical ML model that breaks the complex problem ("Was the mission successful?") into a chain of simpler, manageable classification problems [cite: 2203-2205].

1.  [cite_start]**Signals ➡️ Flight Facets:** First, I grouped thousands of raw flight signals into expert-defined **"Flight Facets"** (e.g., "Propulsion System", "Flight Condition", "Pilot Workload") [cite: 140-141, 222, 237].
2.  [cite_start]**Facets ➡️ Actions:** I trained a classifier to evaluate the success (1 or 0) of an **"Action"** (e.g., "Reach 240 Knots") based on the status of its related facets [cite: 265-269, 566-568].
3.  [cite_start]**Actions ➡️ Tasks/Procedures:** A second layer of models learned to assess a **"Procedure"** (e.g., "Take-Off Maneuver") based on the success of its component actions[cite: 278, 599, 625].
4.  [cite_start]**Procedures/Tasks ➡️ Mission:** A final meta-model classified the **"Global Mission"** success based on the aggregated results of all its tasks and procedures [cite: 278-280, 651].



### 3. The Process (Modeling & Evaluation)
* [cite_start]**Problem Type:** Binary Classification (Success=1, Fail=0)[cite: 511, 758].
* [cite_start]**Model Benchmarking:** I tested 7 different classification algorithms, including `Logistic Regression`, `SVC`, `K-Nearest Neighbors`, **`Random Forest Classifier`**, and **`Gradient Boosting Classifier`**[cite: 1480, 1537].
* [cite_start]**Evaluation Metrics:** As this was a classification problem, I evaluated models using the **Confusion Matrix**, **Accuracy**, **Precision**, **Recall**, and **F1-Score** [cite: 1341-1390].
* [cite_start]**Optimization:** The champion models (RFC and GBC) were optimized using **`GridSearchCV`** to find the best combination of hyperparameters (e.g., `n_estimators`, `max_depth`, `learning_rate`) [cite: 1539, 1566-1578, 1605-1618].

### 4. The Results (Conclusion)

* **Important Disclaimer on Data:** Due to the sensitive nature of the data (**NATO Restricted**), the dataset had to be anonymized and simplified before delivery. This resulted in highly clean data patterns, which the models learned to perfection (0.99-1.0 scores).
* [cite_start]**Proof of Concept:** The project's true success was not the score itself, but the **proof of concept**: demonstrating that a complex, hierarchical aerospace engineering problem *can* be successfully modeled and automated with a standard Machine Learning pipeline [cite: 2206-2213].

### 5. Technologies Used
* [cite_start]**Core:** `Python`, `Scikit-learn`[cite: 1318], `Pandas`, `Numpy`, `Matplotlib`.
* [cite_start]**Models:** `RandomForestClassifier` [cite: 814][cite_start], `GradientBoostingClassifier` [cite: 817][cite_start], `LogisticRegression` [cite: 813][cite_start], `SVC` [cite: 805][cite_start], `KNN`[cite: 808], etc.
* [cite_start]**Techniques:** `GridSearchCV` [cite: 1543][cite_start], `Cross-Validation`[cite: 391], `Feature Engineering`, `Hyperparameter Tuning`.
