# FinSight

**FinSight** is a prototype AI system designed to analyze **earnings call Q&A interactions** and detect potentially **evasive executive responses**.

Earnings calls contain critical communication between **financial analysts and company management**. Executives sometimes respond to difficult questions indirectly or with vague statements. FinSight aims to identify such communication patterns automatically.

The system combines **semantic similarity analysis and LLM reasoning** to classify responses as:

* **Direct Answer**
* **Partial Answer**
* **Evasive Answer**

This helps analysts quickly identify important signals in earnings call discussions.

---

# Project Overview

FinSight analyzes the interaction between **analyst questions and executive answers** rather than simply summarizing the entire transcript.

The workflow includes:

1. Extracting **question–answer pairs** from earnings call transcripts
2. Measuring **semantic similarity** between the question and the response
3. Sending the Q&A pair to an **LLM for reasoning-based classification**
4. Generating explanations for why a response may be evasive or incomplete

The goal is to help analysts focus on the **most meaningful communication signals** instead of manually reviewing long transcripts.

---

# Example

**Analyst Question**

> What caused the decline in margins this quarter?

**Executive Response**

> We remain focused on long-term shareholder value and strategic investments.

**FinSight Output**

Classification: **Evasive Answer**

Reason: The response does not address the analyst’s question about margin decline and instead shifts focus toward broader strategic goals.

---

# Current Status

FinSight is currently a **proof-of-concept prototype**.

For the initial prototype:

* Analyst **question–answer pairs were manually extracted**
* Semantic similarity and LLM reasoning were used to test whether meaningful insights could be generated
* The system demonstrates that **NLP can detect communication signals in earnings call discussions**

---

# Technologies Used

* Python
* Sentence Transformers (semantic similarity)
* Scikit-learn
* Groq LLM API
* HuggingFace models

---

# Setup Instructions

## 1 Install dependencies

Install the required Python packages:

```
pip install pandas sentence-transformers scikit-learn openai groq
```

---

## 2 Create API Keys

FinSight requires two API keys.

### HuggingFace Token

Create a token at:

[https://huggingface.co/settings/tokens](https://huggingface.co/settings/tokens)

---

### Groq API Key

Create an API key at:

[https://console.groq.com/keys](https://console.groq.com/keys)

---

## 3 Add API Keys

Inside the notebook, replace the placeholder values with your keys:

```python
import os

os.environ["HF_TOKEN"] = "your-huggingface-token-here"
os.environ["GROQ_API_KEY"] = "your-groq-api-key-here"
```

Do **not upload real keys to GitHub**.

---

## 4 Run the notebook

Open the notebook:

```
finsight_analysis.ipynb
```

Run all cells to execute the analysis pipeline.

---

# Future Extensions

Possible extensions discussed during the JPMorgan Innovation Forum include:

* **Audio-to-text integration** for analyzing earnings call recordings
* **Voice tone and hesitation detection**
* **Speaker identification for analyst vs executive dialogue**
* **Multimodal analysis combining text, audio, and video signals**

