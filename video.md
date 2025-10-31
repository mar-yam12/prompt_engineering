

## 1. What is  LLM?

**LLM = Large Language Model**  
A super-smart AI that predicts the next word in a sentence.  

- Trained on **billions of words** (books, websites, chats).  
- Doesn't "think" — it finds **patterns**.  
- Example:  
  > You: "Pakistan's capital is..."  
  > LLM: "Islamabad" (because it saw this 1M+ times).

---

## 2. Prompt & Context Engineering

**Prompt** = Your question/instruction.  
**Context** = Background info you give.

**Bad Prompt:**  
> "Tell me about AI."

**Good Prompt (Engineered):**  
> "Explain AI to a 10-year-old in 3 simple sentences."

**Context Example:**  
> "You are a funny science teacher. Explain gravity to kids."

**Result:** Better, clearer, funnier answers!

---

## 3. Temperature, Top-p, Top-k (Output Controls)

| Parameter   | What It Does                  | Low = ?         | High = ?          |
|-------------|-------------------------------|-----------------|-------------------|
| **Temperature** | Controls randomness          | Safe, boring    | Creative, wild    |
| **Top-p**       | Keeps top % of likely words  | Focused         | More variety      |
| **Top-k**       | Keeps top K words only       | Very limited    | More options      |

**Examples:**  
- `Temp=0.2` → "The cat sat on the..." → "mat." (safe)  
- `Temp=1.2` → "The cat sat on the..." → "flying pizza!" (fun)  

**Defaults:** `Temp=0.7`, `Top-p=0.9`, `Top-k=50`

---
