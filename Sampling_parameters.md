# LLM Sampling Parameters: Temperature, Top-p, Top-k

> Ek hi README mein **sab kuch detail se**, Roman Urdu + English mix mein. GitHub pe push karne ke liye ready!

---

## 🌟 Introduction

Yeh parameters **Large Language Model (LLM)** ke output ko control karte hain. Inka use karke hum decide karte hain ke jawab **kitna safe**, **kitna creative**, ya **kitna random** hoga.  

- **Temperature** → Creativity ka thermostat  
- **Top-p** → Smart word filter (nucleus)  
- **Top-k** → Fixed top words only  

---

## 1. Temperature

### Kya hai?
Ek **scaling factor** jo LLM ke **next word probability** ko softmax ke through badalta hai.  

### Range: `0.0` se `2.0` tak  
*(Common: 0.1 – 1.2)*

### Kaise kaam karta hai?
- **Low Temp (0.1 – 0.5)** → Sirf **high confidence** words → **boring, predictable, accurate**  
- **High Temp (1.0 – 1.5)** → **Low probability** words ko bhi chance → **creative, funny, lekin risky**

### Example:
```text
Prompt: "Ek robot ghar gaya aur..."

Temp = 0.2 → "...wahan baitha TV dekhta raha."
Temp = 1.2 → "...wahan disco kiya aur chand pe selfie li!"
Best Practice:


Use CaseRecommended TempCode, Facts, Q&A0.1 – 0.5Normal Chat0.7 (default)Story, Poetry0.9 – 1.2

Temp = 0 → Greedy decoding (hamesha #1 word)
Temp > 1.5 → Bakwas shuru ho sakti hai
```
## 2. Top-p (Nucleus Sampling)
### Kya hai?
Sirf *cumulative probability* mein top p % words hi consider karta hai. Baqi ignore.
**Range: 0.0 se 1.0**
(Common: 0.9)
### Kaise kaam karta hai?
Har step pe LLM dekhta hai:
"In words ka total probability p tak pohanch gaya? Rakho. Baqi hatao."
### Example:
```
textNext word probabilities:
  "hai"   → 60%
  "tha"   → 20%
  "hoga"  → 10%
  "ne"    → 5%
  ...
top_p = 0.95 → "hai", "tha", "hoga", "ne" rakhega (95% tak)
top_p = 0.5 → Sirf "hai" aur "tha" (50% tak)
```
### Best Practice:



TaskTop-pSafe answers0.7Balanced0.9Max creativity1.0

Top-p = 1.0 → Koi filtering nahi
Top-p = 0.0 → Sirf #1 word


## 3. Top-k
### Kya hai?
Sirf top K *most likely* words hi consider karta hai. Fixed number

**Range: 1 se ∞**
(Common: 40 – 100)
### Kaise kaam karta hai?
Har baar sirf K sabse zyada possible words mein se choose karta hai.
### Example:
texttop_k = 5  → Sirf top 5 words allowed
top_k = 50 → 50 words allowed → zyada variety
Best Practice:

TaskTop-kStrict control10–20Normal use40–50Creative100+

Top-k = 1 → Greedy (hamesha #1 word)


## 🎯 Kaunsa Kab Use Karein? (Cheat Sheet)


```TaskTemperatureTop-pTop-kReasonCode generation0.20.9540AccurateCustomer support bot0.70.950Natural + safeStory / Poem1.00.95100CreativeFact-based Q&A0.11.01Max accuracyBrainstorming ideas1.20.98150Wild ideas```

### ⚙️ Code Example (Python)
```
pythonimport openai

response = openai.ChatCompletion.create(
    model="grok-beta",
    messages=[{"role": "user", "content": "Ek mazedaar kahani likho robot ki"}],
    temperature=1.0,
    top_p=0.95,
    # top_k=50,  # OpenAI support nahi karta, Hugging Face mein use karo
    max_tokens=200
)

print(response.choices[0].message.content)
```
### Note:

##### OpenAI: temperature + top_p
##### Hugging Face / Grok API: top_k bhi support
##### Top-k aur Top-p dono mat use karo → conflict



### 🔥 Pro Tips

*Temperature + Top-p saath best kaam karte hain*

*Temp = 0 + Seed → 100% same output har baar*

*Top-p > Top-k zyada flexible hota hai*

*Experiment karo → Har model alag behave karta hai*


## ❌ Common Mistakes

| Galti                        | Result         |
|------------------------------|----------------|
| Temp=2.0                     | Random bakwas  |
| Top-p=0.1 + Temp=0           | Stuck in loop  |
| Top-k=1                      | Repetition     |
| Temp=0 + Top-p=1.0           | No effect      |
## 🛠️ Experiment Karne Ke Tools

##### Grok Playground
##### Hugging Face Text Generation
##### OpenAI Playground

