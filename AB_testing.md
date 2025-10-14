# 🧠 Prompt Engineering Temperature, Top-P and Top-k Examples

| **Parameter** | **Prompt** | **Low Setting Example** | **High Setting Example** |
|----------------|-------------|--------------------------|---------------------------|
| **Temperature** | Write one line about the moon. | Temp = 0.2 → The moon is a natural satellite of Earth. | Temp = 1.0 → The moon dances in the dark sky like a glowing pearl. |
| **Top-p (Nucleus Sampling)** | Describe the ocean. | Top-p = 0.3 → The ocean is deep and blue. | Top-p = 0.9 → The ocean roars with waves, mystery, and endless life. |
| **Top-k** | Describe a cat. | Top-k = 5 → A cat is a small, furry animal. | Top-k = 50 → A cat is a playful creature with sparkling eyes and a curious soul. |
| **Max Output Tokens** | Explain the water cycle. | Max Tokens = 20 → Water evaporates, forms clouds, and falls as rain. | Max Tokens = 100 → The water cycle involves evaporation from oceans, condensation into clouds, precipitation as rain or snow, and collection in rivers and lakes. |



# 🧠Zero, One and Few Short Prompting Examples

| **Prompting Type** | **Example Prompt** | **Example Output** |
|-------------------|------------------|------------------|
| **Zero-shot Prompting** | “Translate 'Hello' to French.” | “Bonjour” |
| **One-shot Prompting** | “Translate 'Hello' to French. Example: 'Good morning' → 'Bonjour'” | “Hello' → 'Bonjour'” |
| **Few-shot Prompting** | “Translate these English words to French: 'Good morning' → 'Bonjour', 'Thank you' → 'Merci'. Now translate 'Hello'.” | “Hello → Bonjour” |
| **System Prompting** | System: “You are a polite assistant. Answer politely.” User: “How are you?” | “I’m doing well, thank you! How about you?” |
| **Role Prompting** | “You are a teacher. Explain photosynthesis to a student in simple words.” | “Photosynthesis is how plants make food using sunlight, water, and air.” |
| **Contextual Prompting** | “Previously we discussed planets. Now, explain why Mars is red.” | “Mars is red because its surface has iron oxide, which gives it a reddish color.” |


# 🧠 Advanced Prompting Examples

| **Strategy** | **Example Prompt** | **Example Output** |
|--------------|------------------|------------------|
| **CoT (Chain of Thought)** | “Solve 23 + 47 step by step.” | “Step 1: Add tens → 20 + 40 = 60. Step 2: Add units → 3 + 7 = 10. Step 3: Combine → 60 + 10 = 70. Answer: 70” |
| **Self-Consistency** | “Solve 23 + 47 three times independently and pick the most frequent answer.” | “Attempt 1: 70, Attempt 2: 70, Attempt 3: 70. Most common answer: 70” |
| **Step-Back** | “Solve 23 + 47 and then verify by subtracting 23 from your answer.” | “23 + 47 = 70. Verification: 70 − 23 = 47 ✅ Correct, so answer is confirmed.” |
| **ReAct (Reason + Action)** | “You are an agent. Determine if 23 + 47 is even or odd. Show reasoning and action.” | “Reasoning: 23 + 47 = 70. 70 is divisible by 2, so it is even. Action: Confirmed 70 is even.” |
| **ToT (Tree of Thoughts)** | “Plan a multi-step approach to find 23 + 47 considering different strategies.” | “Thought 1: Add tens first → 20 + 40 = 60, then units → 3 + 7 = 10, sum = 70. Thought 2: Break differently → 23 + 7 = 30, 30 + 40 = 70. Final Answer: 70” |


# 📝 Best Practices for Effective Prompts

| **Practice** | **Example Prompt** | **Improved Prompt / Explanation** |
|--------------|------------------|----------------------------------|
| **Be Specific and Clear** | "Explain the impact of climate change on agriculture." | "Provide a detailed analysis of how climate change affects crop yields, water availability, and farming practices in South Asia over the past two decades." |
| **Use Action Verbs** | "Information about the French Revolution." | "Summarize the key events of the French Revolution, highlighting the causes, major battles, and outcomes." |
| **Provide Examples When Possible** | "Translate the following sentences into French." | "Translate the following sentences into French. Example: 'Good morning' → 'Bonjour'. Now, translate: 'How are you?'" |
| **Structure Your Prompts** | "Tell me about the water cycle." | "Explain the water cycle in the following structure:\n1. Evaporation: Describe the process.\n2. Condensation: Explain how clouds form.\n3. Precipitation: Discuss how rain occurs.\n4. Collection: Explain how water returns to bodies of water." |
| **Use Instruction Over Constraints** | "Write a poem about nature. Don't make it too long." | "Write a 4-line poem about the beauty of nature, focusing on the changing seasons." |
| **Control Output Format** | "List the capitals of European countries." | "Provide a table listing European countries and their capitals. Format:\n| Country | Capital |\n|---------|---------|\n| France | Paris |\n| Germany | Berlin |\n| Italy | Rome |" |
| **Use Variables for Reusability** | "Generate a report on the economic impact of tourism in Paris." | "Generate a report on the economic impact of tourism in {City}. Replace {City} with 'Paris', 'Rome', or 'Tokyo' as needed." |
| **Iterate and Document** | "Explain photosynthesis." | "Explain photosynthesis in simple terms for a 10-year-old. Include the role of sunlight, water, and carbon dioxide." |


# ⚠️ Common Pitfalls and How to Avoid Them

### 1. Vague or ambiguous prompts  
- **Pitfall:** “Tell me about climate change.”  
- **Avoid by:** Being specific: “Explain how climate change affects monsoon patterns in South Asia from 2000 to 2025.”

### 2. Overly long or complex prompts  
- **Pitfall:** Giving a single prompt with many sub-questions intertwined.  
- **Avoid by:** Breaking into smaller prompts, or clearly numbering the parts.

### 3. Too many constraints  
- **Pitfall:** “Write a poem about nature, in Urdu, exactly 7 lines, no rhymes, include words ‘tree’ and ‘river’.”  
- **Avoid by:** Using instructions rather than rigid constraints: “Write a poem (4–7 lines) about nature, including ‘tree’ and ‘river’.”

### 4. Not specifying output format  
- **Pitfall:** “List world capitals.” → you get a paragraph.  
- **Avoid by:** Specifying format, e.g. “List world capitals in a table format: `Country | Capital`.”

### 5. Ignoring domain or context  
- **Pitfall:** Asking “Explain photosynthesis” without saying audience or scope.  
- **Avoid by:** Providing context: “Explain photosynthesis to a 12-year-old in an urban school.”

### 6. Inconsistent or missing examples  
- **Pitfall:** Giving no example, so AI doesn’t know style.  
- **Avoid by:** Including a small example: e.g. “Example: ‘Hello’ → ‘Bonjour’. Now translate: ‘Good night’.”

### 7. Not iterating or refining  
- **Pitfall:** You use a prompt once and never tweak it.  
- **Avoid by:** Testing, refining, documenting which prompt works best, and improving over time.

### 8. Hardcoding everything (no reuse)  
- **Pitfall:** Writing prompts specific to one input every time.  
- **Avoid by:** Using placeholders/variables, e.g. `{Topic}`, so you can reuse: “Explain {Topic} in 5 sentences.”

---

*(These pitfalls and avoidance strategies are adapted from the “Common Pitfalls and How to Avoid Them” section of the Panaversity prompt engineering guide.)*  



# 🛠 Hands-on Examples

### Example 1: Translation  
**Prompt:**  
Translate the following English sentences into Urdu:  
1. “Good morning.”  
2. “How are you?”  
3. “I like to learn AI.”  

**Expected Output:**  
1. “صبح بخیر۔”  
2. “آپ کیسے ہیں؟”  
3. “مجھے AI سیکھنا پسند ہے۔”

---

### Example 2: Summarization  
**Prompt:**  
Summarize this paragraph in 2–3 sentences:  

"Artificial intelligence (AI) enables machines to perform tasks that normally require human intelligence. It includes areas like language understanding, image recognition, and decision-making. AI systems learn from data and improve over time."  

**Expected Output:**  
AI lets machines do tasks that usually need human intelligence, like understanding language and recognizing images. These systems learn from data and get better as they receive more information.

---

### Example 3: QA with Context  
**Prompt:**  
Here is a short passage:  

"Marie Curie discovered radium and polonium and was the first woman to win a Nobel Prize. Her work laid the foundation for modern radiological science."  

**Question:**  
What did Marie Curie discover, and why is she important?  

**Expected Output:**  
Marie Curie discovered radium and polonium. She is important because she was the first woman to win a Nobel Prize and her discoveries advanced the field of radiological science.

---

### Example 4: Role + Instruction  
**Prompt:**  
You are a high school science teacher. Explain the greenhouse effect to students in simple terms, with one real-world example.  

**Expected Output:**  
The greenhouse effect happens when certain gases in Earth’s atmosphere trap heat from the sun, keeping the planet warm.  
For example, just like a car’s windows let sunlight in but don’t let heat escape, greenhouse gases let sunlight through but trap the warmth, which raises Earth’s temperature.

---

> 💡 These are hands-on examples — meaning learners can try writing, modifying, and testing the prompts themselves to understand how prompt design improves the AI’s responses.
