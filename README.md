# TraceNet

### Trace before you Trust.

**TraceNet** is a multi-modal misinformation detection and verification platform that analyzes **text, URLs, images, and videos** to help identify potentially misleading, manipulated, or AI-generated content.

The system combines **machine learning, visual analysis, external verification, explainable AI, and information tracking** to provide users with a prediction, confidence score, supporting evidence, and relationships between relevant sources.

---

## Overview

The rapid spread of information through social media, news platforms, messaging applications, and digital media makes it increasingly difficult to determine whether content can be trusted.

TraceNet provides a single platform where users can submit different types of content and analyze them through specialized detection pipelines.

### Supported Inputs

* **Text** — Fake/real news and misinformation detection
* **URL** — News/content analysis and source verification
* **Image** — Real vs AI-generated image detection
* **Video** — Real vs deepfake video detection

Instead of relying only on a prediction, TraceNet combines model results with supporting information and explanations to help users understand the result.

---

# Key Features

### Multi-Modal Detection

TraceNet supports multiple forms of digital content:

* Text
* URLs
* Images
* Videos

Each input is processed using an appropriate analysis pipeline.

### Text & News Detection

Analyzes text and news content to identify potentially misleading or fake information.

### URL Analysis

Analyzes submitted URLs and checks related information and sources where applicable.

### AI-Generated Image Detection

Analyzes images to identify characteristics associated with AI-generated or manipulated visual content.

### Deepfake Video Detection

Processes videos using frame-level and visual analysis techniques to identify potential deepfake content.

### Confidence Score

Displays a confidence score along with the model prediction to provide additional context about the result.

### External Verification

Cross-checks information with external sources and fact-checking services where applicable.

### Explainable AI

TraceNet provides supporting information about why content may have been flagged.

### Information Tracking

Related sources and content can be represented through interactive relationships and network graphs.

<img width="1402" height="667" alt="T1" src="https://github.com/user-attachments/assets/12c95d87-6559-4bd4-a9a0-22011fab0380" />
<img width="1300" height="602" alt="T2" src="https://github.com/user-attachments/assets/b118c55a-5caa-4777-936c-4a540b229f8d" />
<img width="1257" height="617" alt="T6" src="https://github.com/user-attachments/assets/fc625446-56f7-40a4-9bb7-893a52d041d1" />
<img width="1410" height="676" alt="T5" src="https://github.com/user-attachments/assets/23de2a39-885a-48be-b276-a9b04df23bf9" />
<img width="1421" height="687" alt="T4" src="https://github.com/user-attachments/assets/604c59ab-b1b1-408a-8e8c-81ef917eca19" />
<img width="1282" height="637" alt="T3" src="https://github.com/user-attachments/assets/a587090e-a226-4edc-888e-25fc3df3c1e8" />

---

# System Architecture

TraceNet follows a multi-stage pipeline:

```text
                         USER
                           │
                           ▼
                 ┌───────────────────┐
                 │    INPUT LAYER    │
                 │                   │
                 │ Text │ URL │ Image│
                 │       │ Video     │
                 └─────────┬─────────┘
                           │
                           ▼
                 ┌───────────────────┐
                 │   PREPROCESSING   │
                 │                   │
                 │ Text Processing   │
                 │ URL Processing    │
                 │ Image Processing  │
                 │ Video Processing  │
                 └─────────┬─────────┘
                           │
                           ▼
                 ┌───────────────────┐
                 │ FEATURE EXTRACTION│
                 └─────────┬─────────┘
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
        ┌──────────┐  ┌──────────┐  ┌──────────┐
        │   TEXT   │  │  IMAGE   │  │  VIDEO   │
        │   MODEL  │  │   MODEL  │  │   MODEL  │
        └────┬─────┘  └────┬─────┘  └────┬─────┘
             │             │             │
             └─────────────┼─────────────┘
                           ▼
                 ┌───────────────────┐
                 │ PREDICTION ENGINE │
                 │                   │
                 │ Classification    │
                 │ Confidence Score  │
                 └─────────┬─────────┘
                           │
              ┌────────────┼────────────┐
              ▼            ▼            ▼
        ┌──────────┐ ┌──────────┐ ┌──────────┐
        │ External │ │Explain-  │ │Information│
        │Verification│ │ability  │ │ Tracking │
        └─────┬────┘ └────┬─────┘ └────┬─────┘
              └────────────┼────────────┘
                           ▼
                 ┌───────────────────┐
                 │   FINAL RESULT    │
                 │                   │
                 │ Prediction        │
                 │ Confidence       │
                 │ Evidence         │
                 │ Sources          │
                 │ Explanation      │
                 └───────────────────┘
```

---

# Machine Learning Models

TraceNet uses different machine learning approaches for different content types.

| Input | Model             | Task                          |
| ----- | ----------------- | ----------------------------- |
| Text  | Random Forest     | Fake / Real news detection    |
| Image | Gradient Boosting | Real / AI-generated detection |
| Video | XGBoost           | Real / Deepfake detection     |

Each model is applied according to the characteristics of the submitted content.

---

# How TraceNet Works

The complete workflow consists of the following stages:

### 1. Input Collection

The user provides one of the supported inputs:

```text
Text
URL
Image
Video
```

### 2. Preprocessing

The submitted content is processed according to its type.

For example:

* Text is cleaned and prepared for feature extraction.
* URLs are processed for source/content analysis.
* Images are prepared for visual analysis.
* Videos are processed into frames and analyzed for relevant visual characteristics.

### 3. Feature Extraction

Relevant features are extracted from the processed input.

### 4. Model Prediction

The appropriate machine learning model analyzes the extracted features.

### 5. External Verification

Where applicable, the system cross-checks information against external sources and fact-checking services.

### 6. Explainability

TraceNet provides supporting information that helps users understand why content may have been flagged.

### 7. Final Result

The system presents:

* Prediction
* Confidence score
* Supporting evidence
* Relevant sources
* Explanations
* Source relationships where available

---

# Explainability

TraceNet does not limit the output to a simple **Fake / Real** result.

The system provides additional information to help users interpret the prediction.

### Text

**LIME** is used for text-based explanations.

### Images

Image analysis uses:

* Error Level Analysis (ELA)
* Visual features

### Videos

Video analysis considers:

* Individual frames
* Motion-related characteristics
* Visual patterns

### Supporting Evidence

The system can also display:

* Supporting sources
* Related information
* Evidence used during verification

---

# Information Tracking

A major component of TraceNet is the ability to track relationships between information sources.

The system can display:

* Relevant sources
* Related content
* Source relationships
* Information propagation through network graphs
* Source credibility signals

This allows users to look beyond a single prediction and examine how information is connected across sources.

---

# Dataset

## Text Dataset

TraceNet uses multiple datasets for text-based misinformation detection:

* **ISOT Fake News Dataset**
* **LIAR Dataset**
* **WWFND Dataset**
* **20,000+ combined samples**

---

## Image Dataset

The image detection pipeline uses:

* **AI Generated Images vs Real Images Dataset**
* **975 images**

The dataset is used for distinguishing real images from AI-generated images.

---

## Video Dataset

The video detection pipeline uses:

* **Deepfake Videos Dataset**
* **Real vs AI Video Dataset**
* **FaceForensics++**
* **76 videos used for training and evaluation**

---

# Model Performance

The following results are based on the current evaluation reported for the project.

## Text Model

| Metric    |     Result |
| --------- | ---------: |
| Accuracy  | **82.53%** |
| Precision |    **83%** |
| Recall    |    **83%** |
| F1-Score  |    **83%** |
| AUC-ROC   | **0.9245** |

---

## Image Model

| Metric    |   Result |
| --------- | -------: |
| Accuracy  |  **71%** |
| Precision |  **71%** |
| Recall    |  **71%** |
| F1-Score  |  **71%** |
| AUC-ROC   | **0.78** |

---

## Video Model

| Metric         |     Result |
| -------------- | ---------: |
| Accuracy       | **68.75%** |
| AUC-ROC        |   **0.75** |
| Macro F1-Score | **0.6761** |

---

# Performance Summary

| Modality | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
| -------- | -------: | --------: | -----: | -------: | ------: |
| Text     |   82.53% |       83% |    83% |      83% |  0.9245 |
| Image    |      71% |       71% |    71% |      71% |    0.78 |
| Video    |   68.75% |         — |      — |   0.6761 |    0.75 |

> Performance values are dependent on the datasets, preprocessing methods, training configuration, and evaluation setup used for each modality.

---

# Technology Stack

| Category             | Technologies          |
| -------------------- | --------------------- |
| Programming Language | Python                |
| Machine Learning     | Scikit-learn          |
| Gradient Boosting    | XGBoost               |
| Computer Vision      | OpenCV                |
| Data Processing      | Pandas, NumPy         |
| Explainable AI       | LIME                  |
| Backend              | Flask                 |
| Frontend             | HTML, CSS, JavaScript |
| AI Services          | Gemini API            |
| Verification         | Fact-Check APIs       |

---


---

# Installation

## 1. Clone the Repository

```bash
git clone https://github.com/bhoooomi05/TraceNet.git
```

```bash
cd TraceNet
```

## 2. Create a Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
```

```bash
source venv/bin/activate
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## 4. Configure APIs

If required by the current implementation, configure the required API credentials for:

* Gemini API
* Fact-checking services
* Other external verification services

Store API credentials using environment variables rather than committing them to the repository.

Example:

```text
GEMINI_API_KEY=your_api_key
FACT_CHECK_API_KEY=your_api_key
```

## 5. Run the Application

Start the Flask backend using the project's configured entry point.

Then open the frontend through the configured local development server or application URL.

---

# Usage

### Text

Enter or paste the content that you want to analyze.

```text
User → Text → Preprocessing → ML Model → Prediction
```

### URL

Submit a news or content URL.

```text
User → URL → Source Analysis → Verification → Result
```

### Image

Upload an image for analysis.

```text
User → Image → Visual Analysis → Model → Result
```

### Video

Upload a video for deepfake analysis.

```text
User → Video → Frame Analysis → Model → Result
```

---

# Example Output

A TraceNet result can contain:

```text
Content Type:
Text / URL / Image / Video

Prediction:
Fake / Real
or
AI Generated / Real
or
Deepfake / Real

Confidence:
XX%

Supporting Evidence:
Relevant sources and information

Explanation:
Important features or visual characteristics

Related Sources:
Connected information and source relationships
```

---

# Why TraceNet?

TraceNet combines several analysis capabilities into a single platform.

Instead of analyzing only one type of content, the system provides a common workflow for:

```text
TEXT
  │
URL
  │
IMAGE
  │
VIDEO
  │
  ▼
TRACE
  │
  ▼
VERIFY
  │
  ▼
EXPLAIN
  │
  ▼
UNDERSTAND
```

The objective is to help users **trace information before trusting it**.

---

# Future Scope

Potential extensions for TraceNet include:

* Transformer-based misinformation detection
* Larger and continuously updated datasets
* Improved deepfake detection
* Multilingual misinformation detection
* Real-time social media monitoring
* Browser extension for instant content analysis
* Improved source credibility analysis
* Advanced knowledge graphs
* More detailed explainable AI
* Cross-platform content verification
* Real-time misinformation alerts

---

# Limitations

TraceNet is a machine-learning-based detection system and its predictions should not be treated as absolute proof that a piece of content is true or false.

Model performance can vary depending on:

* Dataset quality
* Input quality
* Unseen content
* Image/video compression
* Language and writing style
* Model limitations
* Availability and reliability of external sources

The system is intended to provide **automated analysis and supporting evidence**, while final verification may require human judgment.

---

# Project Philosophy

> **Trace before you Trust.**

TraceNet is built around a simple idea:

**Don't just ask whether information is true — trace where it came from, how it is connected, and what evidence supports it.**

---

# Achievement

Won **1st Place in the Software Category at Colloquium '26**.

---

# Contributors

This project was collaboratively developed by our team of five members.

- Althia Ferreira 
- Bhoomi Koli
- Bliss Gonsalves
- Jibi Johny
- Shravani Joshi

---

# License

This project is intended for educational, research, and demonstration purposes.



