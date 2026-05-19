# Mobile AI Study Engine Assistant (v1.0.4)
### A Simple Python Semantic Search Engine Built From Scratch Without Any Heavy Libraries

---

## 📌 What is this Project?
Hi! I am a 12th-grade student and I built this project to understand how search engines and AI assistants actually find matching text under the hood. 

Usually, people use big pre-made libraries like Scikit-Learn, NumPy, or FAISS to do this. But since I code on my mobile phone (using Termux), I wanted to see if I could build a working **Semantic Search Engine** using only pure Python math (`math`, `json`, and `collections`). 

This project proves that you don't need a heavy laptop or massive software frameworks to write smart algorithms—you can do it with core math right on a mobile screen!

---

## 🛠️ How It Works (The Logic)

### 1. Counting and Weighting Words (TF-IDF)
When you save a note or a document in this assistant, the code breaks the text into words and calculates two things:
* **TF (Term Frequency):** How many times a word appears in a specific note.
* **IDF (Inverse Document Frequency):** How rare or important that word is across all your saved notes. It uses a clean log formula:

$$IDF(t) = \ln\left(\frac{1 + N}{1 + DF(t)}\right) + 1$$

### 2. Matching the Query (Cosine Similarity Math)
When you type a search phrase, the code turns your query and your notes into mathematical vectors. Then, it uses the **Cosine Similarity Formula** to find the angle between those vectors and spots the best match:

$$\text{Similarity}(Q, D) = \frac{Q \cdot D}{\|Q\| \|D\|}$$

### 3. Smart Backup Layer (Fallback)
If the math doesn't find a good match (score drops below 0.05), the assistant doesn't just crash. It has a backup loop that looks for important keywords like "Python" or "AI" to give you a helpful response anyway.

---

## ⚙️ Features
* **Save to Phone Memory:** It automatically saves your notes into a local file called `mobile_knowledge_matrix.json`.
* **Dynamic Vocabulary:** The code automatically learns new words whenever you add a new note, without needing to restart the program.

---

## 🚀 How to Run the Code

Open your terminal or mobile terminal app and run:

```bash
python MobileAIStudyEngine.py

