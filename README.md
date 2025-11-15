# Machine Learning for Global Mission Assessment (Master's Thesis)

**[View Full Thesis PDF (130 pages)](TFM_Airbus_Final.pdf)**

### Project Summary
A 6-month Master's Thesis project in collaboration with Airbus, developing a Machine Learning system (Python, Scikit-learn) to automate the debriefing of complex military missions, classifying the success or failure of flight actions.

---

### 1. The Problem (Business Understanding)
The manual *debriefing* process for military missions is "tedious and complex," time-consuming, and difficult to scale with the increasing amount of data from flight recorders[cite: 18, 25, 49]. [cite_start]The objective was to design and prove the feasibility of an automated tool using Machine Learning to assess missions, reducing time and cost.

### 2. The Solution (My Methodology)
I designed a hierarchical ML model that breaks the complex problem ("Was the mission successful?") into a chain of simpler, manageable classification problems.

1.  **Signals ➡️ Flight Facets:** First, I grouped thousands of raw flight signals into expert-defined **"Flight Facets"** (e.g., "Propulsion System", "Flight Condition", "Pilot Workload")].
2.  **Facets ➡️ Actions:** I trained a classifier to evaluate the success (1 or 0) of an **"Action"** (e.g., "Reach 240 Knots") based on the status of its related facets.
3.  **Actions ➡️ Tasks/Procedures:** A second layer of models learned to assess a **"Procedure"** (e.g., "Take-Off Maneuver") based on the success of its component actions.
4.  **Procedures/Tasks ➡️ Mission:** A final meta-model classified the **"Global Mission"** success based on the aggregated results of all its tasks and procedures.



### 3. The Process (Modeling & Evaluation)
* **Problem Type:** Binary Classification (Success=1, Fail=0).
* **Model Benchmarking:** I tested 7 different classification algorithms, including `Logistic Regression`, `SVC`, `K-Nearest Neighbors`, **`Random Forest Classifier`**, and **`Gradient Boosting Classifier`**.
* **Evaluation Metrics:** As this was a classification problem, I evaluated models using the **Confusion Matrix**, **Accuracy**, **Precision**, **Recall**, and **F1-Score**.
* **Optimization:** The champion models (RFC and GBC) were optimized using **`GridSearchCV`** to find the best combination of hyperparameters (e.g., `n_estimators`, `max_depth`, `learning_rate`).

### 4. The Results (Conclusion)

* **Important Disclaimer on Data:** Due to the sensitive nature of the data (**NATO Restricted**), the dataset had to be anonymized and simplified before delivery. This resulted in highly clean data patterns, which the models learned to perfection (0.99-1.0 scores).
* **Proof of Concept:** The project's true success was not the score itself, but the **proof of concept**: demonstrating that a complex, hierarchical aerospace engineering problem *can* be successfully modeled and automated with a standard Machine Learning pipeline.

### 5. Technologies Used
* **Core:** `Python`, `Scikit-learn`, `Pandas`, `Numpy`, `Matplotlib`.
* **Models:** `RandomForestClassifier`, `GradientBoostingClassifier`, `LogisticRegression`, `SVC`, `KNN`, etc.
* **Techniques:** `GridSearchCV`, `Cross-Validation`, `Feature Engineering`, `Hyperparameter Tuning`.
