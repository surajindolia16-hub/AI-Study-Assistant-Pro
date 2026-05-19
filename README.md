# Mobile AI Study Engine Assistant (v1.0.4)
### A Simple Python Semantic Search Engine Built From Scratch Without Any Heavy Libraries

---

## 📌 Project Concept
Hi! I am a 12th-grade student from India. I built this project because I wanted to learn how search engines and AI assistants actually find matching text under the hood. 

Usually, people just import heavy libraries like Scikit-Learn or FAISS to do this. But since I code on my mobile phone (using Termux), I wanted to see if I could build a working **Semantic Search Engine** using only pure Python math. 

This project proves that you don't need an expensive laptop or massive software frameworks to write smart algorithms—you can do it with core math right on a mobile screen!

---

## 🛠️ The Architecture (How it Works)

The assistant works by converting text into numbers (vectors) and measuring the angle between them. Here is the step-by-step logic I wrote in the code:

### Step 1: Word Weighting (TF-IDF)
When you save a note, the engine breaks the text into words and calculates two metrics:
* **TF (Term Frequency):** How many times a word appears in that specific note.
* **IDF (Inverse Document Frequency):** How unique or rare that word is across all your saved notes. 

$$\text{Formula used for IDF:} \quad IDF(t) = \ln\left(\frac{1 + N}{1 + DF(t)}\right) + 1$$

### Step 2: Vector Matching (Cosine Similarity)
When you type a search phrase, the engine projects the query and the saved notes into a mathematical vector space. It then runs the **Cosine Similarity Formula** to calculate the exact closeness between them:

$$\text{Similarity}(Q, D) = \frac{Q \cdot D}{\|Q\| \|D\|}$$

### Step 3: Heuristic Fallback
If the math score drops below `0.05` (meaning no direct vector match was found), a backup parser takes over. It scans for core keywords like "Python" or "AI" to ensure the assistant still returns a relevant fallback response.

---

## ⚙️ Core Features
* **Persistent Storage:** Automatically serializes and saves your database into a local `mobile_knowledge_matrix.json` file.
* **Dynamic Vocabulary:** The vector space dynamically expands its dimensions whenever you type in a new word, without needing a system restart.

---

## 🚀 How to Run

1. Open your terminal app (like Termux on mobile or Command Prompt on PC).
2. Execute the python thread:

```bash
python MobileAIStudyEngine.py


