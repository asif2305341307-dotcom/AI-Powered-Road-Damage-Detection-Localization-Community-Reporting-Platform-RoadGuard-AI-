# 🛣️ RoadGuard AI
### 🤖 Intelligent Road Damage Detection, Localization, Severity Assessment & Community Reporting Platform

<p align="center">
  🚧 Detect • 📍 Locate • 📸 Report • 🗺️ Monitor
</p>

**🎓 Course:** SE331 — Software Engineering Capstone Project  
**🏛️ Department:** Department of Software Engineering  
**🏫 Institution:** Daffodil International University  
**🚀 Project Status:** In Development

---

## 🌟 1. Project Overview

RoadGuard AI is a proposed web-based prototype that combines **Artificial Intelligence (AI), computer vision, and community-based road damage reporting**.

The platform aims to help community members submit road damage images and location information, receive AI-assisted damage predictions, and track submitted reports. Administrators can review reports, correct predictions, update report statuses, and monitor reported road damage through map-based visualization and analytics.

🎯 **Our mission:** Make road damage reporting more organized, accessible, and data-driven while keeping human verification at the center of the process.

> ⚠️ RoadGuard AI is designed to support reporting and review. It does not replace professional road engineers or make official road repair decisions.

## 🚧 2. Problem Statement

Road damage, including potholes, cracks, and surface deterioration, can affect road users and make travel difficult. Traditional reporting processes may result in incomplete information, inconsistent categorization, duplicate reports, and limited visibility into report progress.

💡 RoadGuard AI proposes a centralized workflow that combines image-based damage classification, location information, report management, and administrator verification to make road damage reports easier to organize and review.

## 🎯 3. Project Objectives

- 📸 Develop a web-based prototype for community road damage reporting.
- 🤖 Train or fine-tune a computer-vision model to classify road images into supported damage categories.
- 📊 Display the predicted damage class and confidence score.
- 🔍 Support damage localization if suitable object-detection annotations and resources are available.
- 🗺️ Provide map and list views of submitted reports.
- 🛡️ Allow administrators to verify, reject, reclassify, and update report statuses.
- 🔄 Flag potential duplicate reports using geographic proximity and image similarity.
- 📈 Provide basic analytics by damage category, location, and status.
- 🧪 Evaluate model performance and document errors, dataset limitations, and responsible AI considerations.

## ✨ 4. Core Features

### 👥 Community Reporting
- 📤 Submit a road image with GPS coordinates or a map-selected location.
- 📝 Add an optional description.
- ✅ Validate uploaded images and required information.
- 🆔 Receive a unique report ID and view report status.

### 🧠 AI-Powered Road Damage Classification
- 🖼️ Analyze a valid uploaded image using a trained computer-vision model.
- 🏷️ Predict a damage category supported by the selected dataset.
- 📊 Display the confidence score when available.
- ⚠️ Present predictions as estimates requiring human review.

### 🔍 Damage Localization — Conditional
Display a bounding box or marked region around visible damage if a suitable object-detection model and bounding-box annotations are available.

### 📏 Severity Assessment — Conditional
Include AI-based severity classification only if reliable severity-labelled data and a validated model are available. Otherwise, severity will be assessed manually or omitted.

### 🗺️ Map and Report Management
- 📍 Display reports in a list and on a map when valid coordinates are available.
- 💾 Store report metadata, image references, predictions, timestamps, and statuses.
- 🛡️ Allow authorized administrators to verify, reject, reclassify, and update reports.
- 📜 Maintain report-status history.

### 🔄 Potential Duplicate Detection
- 📌 Flag candidate duplicates using configured geographic-distance and image-similarity rules.
- 👨‍💻 Present possible duplicates for administrator review.
- 🚫 Never automatically delete or reject a report solely because it is flagged.

### 📊 Analytics Dashboard
- 📈 Display report counts by status and supported damage category.
- 🔎 Provide filters and map-based visualization where feasible.

## 🤖 5. AI and Computer-Vision Approach

The core AI task is **automated analysis of uploaded road images to suggest a supported damage category**.

### 🔬 Planned AI Workflow

1. 📚 Inspect a public road-damage dataset and verify its source, licence, categories, and annotation format.
2. 🧹 Prepare image data and separate training, validation, and test sets before model selection.
3. 🧠 Train or fine-tune a baseline image classifier using transfer learning with a pretrained convolutional neural network (CNN).
4. 🧪 Evaluate the model on held-out test data.
5. 🔗 Integrate the model into the reporting workflow.
6. 📝 Document model performance, misclassifications, and known limitations.

A suitable YOLO object-detection implementation may be considered for localization if annotations, licensing, and computing resources permit.

Potential duplicate detection may combine visual image embeddings or perceptual similarity with geographic-distance rules.

### 📊 AI Evaluation Metrics

The team plans to report:

- 🎯 Precision
- 🔍 Recall
- ⚖️ F1-score
- 🧩 Confusion matrix
- 📈 Accuracy where appropriate
- 📦 Suitable object-detection metrics if localization is implemented
- ⏱️ Model inference time in the available development environment

Class imbalance and data leakage will be considered. Actual evaluation results will be documented after testing; **no model accuracy or performance result is claimed in advance**.

## 🔄 6. Proposed System Workflow

1. 👤 A community user submits a road image and location.
2. ✅ The application validates the image and required information.
3. 🤖 The computer-vision model predicts a supported damage category and confidence score.
4. 🆔 The application creates a report with a unique ID and an initial status of **Pending Review**.
5. 💾 The report is stored and displayed in the list or map.
6. 🔄 The duplicate-check module may flag similar reports for review.
7. 🛡️ An authorized administrator verifies or corrects the report and updates its status.
8. 📬 The user can track the report's current status.

## 🧰 7. Tools and Technologies

| 🛠️ Area | 💻 Proposed Technology | 🎯 Purpose |
|---|---|---|
| Programming Language | Python | Application development and AI experiments |
| Web Interface | Streamlit | Reporting interface, admin pages, and dashboard |
| Deep Learning | PyTorch or TensorFlow/Keras | Image classification; the team will choose one |
| Image Processing | OpenCV and Pillow | Image validation, preprocessing, and visualization |
| Data Analysis | pandas, NumPy, scikit-learn | Dataset analysis and evaluation metrics |
| Object Detection | Suitable YOLO implementation (optional) | Damage localization |
| Database | SQLite | Report metadata, predictions, and status history |
| Mapping | Folium/Leaflet or equivalent | Map-based report visualization |
| Charts | Plotly or Matplotlib | Analytics and evaluation charts |
| Version Control | Git and GitHub | Collaboration and source control |

📌 The team will confirm the dataset, model, and framework licences before implementation. The core prototype is not intended to depend on a paid AI API.

## 🏗️ 8. System Architecture

The proposed system consists of five main components:

- 🖥️ **Presentation Layer:** Community report form, report list/map, and administrator dashboard.
- ⚙️ **Application Layer:** Input validation, report creation, inference requests, duplicate-candidate checking, and status workflow.
- 🧠 **AI Layer:** Trained image classifier and optional object detector.
- 🗄️ **Data Layer:** Report metadata, image references, predictions, and status history.
- 🧪 **Evaluation Layer:** Held-out test data, AI metrics, error analysis, and functional test cases.

## 📋 9. Functional Requirements

The system is planned to support the following requirements:

- 🔐 **FR-01:** User registration, login, and role-based administrator access.
- 📤 **FR-02:** Submit a road damage report with an image, location, and optional description.
- ✅ **FR-03:** Validate image file types and configured file-size limits.
- 🤖 **FR-04:** Generate an AI damage prediction and display its confidence score when available.
- 🔍 **FR-05:** Localize visible damage if a suitable detection model is implemented.
- 🆔 **FR-06:** Create and store a report record with a unique ID.
- 🗺️ **FR-07:** Display reports in a list and map when location coordinates are available.
- 🛡️ **FR-08:** Allow authorized administrators to verify, reject, reclassify, and update reports.
- 🔄 **FR-09:** Flag potential duplicate reports for human review.
- 📏 **FR-10:** Support conditional severity classification if reliable labels and a validated model are available.
- 📍 **FR-11:** Allow users to track report status.
- 📊 **FR-12:** Display basic report analytics.
- 📜 **FR-13:** Maintain report-status history and the responsible administrator account.
- ⚠️ **FR-14:** Show a disclaimer explaining that AI predictions are estimates.

## 🛡️ 10. AI and Non-Functional Requirements

The project will address the following requirements:

- 🧪 Evaluate at least one baseline image classifier on held-out data.
- 📊 Report appropriate evaluation metrics and consider class imbalance.
- 🔒 Prevent data leakage by separating training, validation, and test data before model selection.
- 💬 Display predictions as model estimates rather than engineering conclusions.
- 📚 Document the dataset source, licence, supported classes, splitting approach, and known limitations.
- ⚠️ Provide understandable validation and inference-error messages.
- 🔐 Require authentication for administrator-only actions.
- 🕵️ Minimize personal data exposure and provide permission-based or manual location selection.
- 🧩 Separate interface, report handling, AI inference, and data storage into maintainable modules where practical.
- ⏱️ Measure inference time and test the main reporting workflow.
- 🧯 Handle failed predictions without silently discarding reports, preserving them for manual review where feasible.
- 🔁 Record relevant package versions, model configuration, and evaluation procedures for reproducibility.

## 👥 11. Project Team

| 👤 Team Member | 🆔 Student ID | 🎯 Primary Responsibilities |
|---|---|---|
| Md Asif Hossen | 232-35-307 | AI/ML, dataset preparation, image preprocessing, model training, evaluation metrics, and AI limitation analysis |
| Tahsin Jubayer | 232-35-370 | Web interface, report workflow, database, map/list view, administrator pages, and AI integration support |
| Tasfia Tasnim Nidi | 232-35-474 | Requirements review, UI/UX feedback, functional test cases, testing coordination, documentation review, and presentation preparation |

🤝 All members will contribute to integration, debugging, ethical review, final documentation, and demonstration.

## 🗓️ 12. Project Timeline and Work Plan

The proposal defines a **12-week sample plan**.

| 🏁 Milestone | 📅 Schedule | 📦 Planned Deliverable |
|---|---|---|
| M1 — Requirements | Week 1 | Approved scope and requirement checklist |
| M2 — Dataset Preparation | Weeks 2–3 | Dataset documentation, data splits, and preprocessing notes |
| M3 — AI Baseline | Weeks 4–5 | Baseline model and experiment log |
| M4 — Model Evaluation | Week 6 | Evaluation table, confusion matrix, and final AI scope |
| M5 — Core Application | Weeks 7–8 | Working report submission and retrieval workflow |
| M6 — Map and Admin | Week 9 | Map/list view and administrator status management |
| M7 — AI Integration | Week 10 | AI result stored with a report and duplicate checking where feasible |
| M8 — Testing | Week 11 | Test report, bug list, and evidence screenshots |
| M9 — Final Demonstration | Week 12 | Working prototype, final documentation, and demonstration slides |

📌 The schedule will be adjusted to the actual course calendar, and progress will be updated during development.

## ⚖️ 13. Ethical, Legal, and Social Considerations

- 📜 Follow dataset licence and attribution requirements.
- 🔏 Collect only necessary personal information.
- 📍 Request permission before accessing device location and provide manual location selection.
- 👤 Avoid publicly displaying unnecessary reporter contact details.
- 🧑‍⚖️ Keep AI predictions separate from administrator-verified results.
- 🌦️ Consider bias related to road types, lighting, weather, and geographic regions.
- 🚧 Do not present AI outputs as proof of legal responsibility, road safety, or official repair priority.

## ⚠️ 14. Risks and Limitations

- 🌍 A public dataset may not represent local road conditions accurately.
- 📷 Poor image quality can reduce prediction reliability.
- 📦 Localization depends on suitable bounding-box annotations.
- 📏 AI severity classification requires reliable severity labels.
- 🔄 Duplicate-candidate detection may produce false positives or miss genuine duplicates.
- ⏳ Limited time or computing resources may restrict optional features.

🚫 RoadGuard AI will not automatically repair roads, dispatch contractors, guarantee detection of every defect, accurately measure pothole depth from a single ordinary image, predict accidents, or make official repair-priority decisions.

## 🔮 15. Future Work

- 🛣️ Build a permission-based local road-image dataset.
- 🎯 Improve localization and severity assessment using consistently labelled data.
- 📱 Develop a mobile-friendly or offline-capable reporting workflow.
- 🔥 Explore road-damage hotspot analysis when sufficient verified reports are available.
- 🏛️ Explore authorized integration with road-maintenance organizations if formal access becomes available.

## 🚀 16. Project Status

**🟡 RoadGuard AI is an academic project in development.**

The features described in this README reflect the proposed scope and requirements. Implementation status, screenshots, setup instructions, and AI evaluation results will be updated as development progresses and features are tested.

## 📚 17. References

The final documentation will include the actual sources consulted by the team, including:

1. 📖 The selected road-damage dataset: official title, authors or organization, URL, licence, and access date.
2. 🧠 The selected computer-vision model or architecture.
3. 📘 Official documentation for the chosen deep-learning framework.
4. 🖼️ OpenCV and Pillow documentation.
5. 🗺️ Documentation for the selected mapping library.

Only verified sources actually used by the team should be included.

---

<p align="center">
  🛣️ <strong>RoadGuard AI</strong><br/>
  🎓 SE331 Software Engineering Capstone Project<br/>
  🏫 Daffodil International University
</p>
