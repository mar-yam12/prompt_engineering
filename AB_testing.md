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
