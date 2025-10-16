# Context Engineering Tutorial: Full Notes (Topics 1 to 11) – Expanded Edition
## Easy Words, Zyada Details Aur Real Examples Ke Saath
**Date:** October 17, 2025  
**Compiled By:** **Maryam Shahid**  

---

## Topic 1: What is Context Engineering?
### Simple Definition (Expanded)
In Simple Words: Context Engineering woh tareeqa hai jismein hum Large Language Model (LLM) – jaise Grok ya ChatGPT – ko sahi information, sahi format mein, aur sahi time pe dete hain taake woh koi specific task ache se kare. Yeh sirf prompt likhna nahi, balki "context window" (LLM ka input area, jahan saari info daalte hain, jaise 128k tokens tak) ko smartly pack karna hai. Jaise tum suitcase pack karte hai travel ke liye – har cheez jagah pe, waste na ho, aur zaruri cheezen top pe, taake airport pe fast nikaal sake.

Easy words mein: Yeh AI ko "perfect guidebook" banana hai, jismein sirf woh pages hon jo kaam aayen, taake AI confuse na ho aur fast, accurate jawab de. Quote se: "Strategically packing the context window to maximize effectiveness."

**Key Point from André Karpathy:** LLM CPU hai (brain jo sochta hai), context window RAM hai (short-term memory jo temporary store karta hai). Context Engineering RAM ko optimize karna hai, taake zyada kaam ho sake bina crash ke ya slow hone ke.

### Working in Easy Steps (Zyada Details)
1. **Context Identify Karo:** Pehle decide karo ke task ke liye kya zaruri hai. Jaise, agar medical advice, toh symptoms + history + WHO guidelines.
2. **Structure Banao:** Info ko chunks mein baanto – headings, bullet points, JSON format. Yeh AI ko parse (samajhna) mein asaan.
3. **Relevance Filter:** Sab kuch mat daalo, sirf relevant. Vector search tools (FAISS) se similar data retrieve.
4. **Inject in Prompt:** Context ko prompt ke start mein daalo: "Based on this [context], answer..."
5. **Iterate & Test:** Output dekho, tweak karo. Token efficiency badhao.

Technically: LLMs attention use karte, focused context se better weights.

### Full Components Aur Benefits (Expanded)
- **Static vs Dynamic Context:** Static fixed (company policy), dynamic real-time (user query).
- **Compression:** Summarize lambi docs.
- **Multi-Modal:** Text + images (captions add).
- **CoT Integration:** Step-by-step reasoning add.
- **Guardrails:** "No illegal advice."
- **Memory:** Previous summarize.

**Benefits:** Hallucinations kam, 10x better output, cost save.  
**Challenges:** Token limits, bias – solution: Test A/B.

### Real-World Examples (Expanded)
1. **Kitchen Recipe App:** Bina: Generic curry. Context: Allergies (nuts avoid), fridge (no garlic), time (15 min). Result: "Chicken + tomato quick." Real: Zomato personalized, try ghar pe.
2. **Office Email Reply:** Boss "Report?" Bina: Boring. Context: Past emails, deadlines, style. Result: "Q3 up 15%, graph attach." Real: Gmail, freelancer time save.
3. **Online Shopping:** "Shoes." Context: History (running), budget (2000), weather (waterproof). Result: 3 options. Real: Amazon, daily use.
4. **Student Homework:** "Math solve." Context: Chapter, mistakes, steps. Result: Graph + explain. Real: Khan Academy tutor.
5. **Doctor App:** "Headache." Context: Age, records, meds. Result: "Rest + paracetamol." Real: Practo, COVID telehealth.
6. **Funny Extra:** Dating app – profile + likes, "Cricket fan? Match dekhen!" Tinder jaise.

**Tips:** Chhote projects se shuru, Promptfoo test.

---

## Topic 2: Context Engineering vs Prompt Engineering
### Basic Difference (Expanded)
**Prompt Engineering:** Yeh direct conversations ke liye, jaise ChatGPT se baat – sawal pooch, jawab, refine. Casual, back-and-forth, iterative (dheere improve).  
**Context Engineering:** Building AI apps/agents ke liye, jaise customer bot – comprehensive instructions, standalone (khud chal jaye), upfront saare scenarios socho. Advanced, code jaise complex.

Quote se: Prompt conversational, Context evolution for complex – real-time refine nahi, anticipate all.

### Comparison Table (Expanded)
| Aspect              | Prompt Engineering                          | Context Engineering                          |
|---------------------|---------------------------------------------|---------------------------------------------|
| **Use Case**        | Direct baatein (shoes discuss: cushion, price) | Apps (customer agent: order, refund) |
| **Nature**          | Back-and-forth, iterative                   | Standalone, comprehensive                   |
| **Complexity**      | Simple, short prompts                       | Complex, XML tags/markdown, code-like       |
| **When to Use**     | Quick personal answers                      | Production apps, speed/accuracy             |
| **Pros**            | Fast learning, fun                          | Scalable, autonomous                        |
| **Cons**            | Limited scale, errors long tasks mein       | Setup time, testing zyada                   |

**Why Distinction Matters?** Apps mein customer wait nahi karega, upfront ready. Hybrid use: Prompt ideas, Context convert.

### Working Mechanism (Zyada Steps)
**Prompt:** 1. Prompt likh. 2. Jawab. 3. Refine. Easy, human involved.  
**Context:** 1. Full data/rules banao. 2. Inject. 3. Standalone run. XML <user>budget</user> use.

### Pros/Cons Aur Integration
Prompt: Pros fast, cons not for scale. Context: Pros accurate, cons hard setup. Integrate: LangChain mein mix.

### Real-World Examples (Expanded)
1. **Shopping:** Prompt: WhatsApp discuss shoes, refine price. Context: Flipkart app history se list, no chat. Real: Instagram vs Amazon.
2. **Health App:** Prompt: Google "Headache," refine fever. Context: Practo symptoms + records, diagnosis. COVID apps.
3. **Coding Help:** Prompt: ChatGPT function, error fix chat. Context: VS Code Copilot codebase + rules, full code. Freelance.
4. **Customer Service:** Prompt: Email back-forth. Context: Zendesk bot details + policy, instant. Jio support.
5. **Gym Trainer:** Prompt: "Plan bata," refine. Context: App weight + goals + equipment, full plan. Cult.fit.
6. **Extra:** Office meeting – prompt discuss agenda, context auto-schedule calendar.

**Tips:** Prompt se practice, apps ke liye context.

---

## Topic 3: When to Use Context Engineering
### Basic Idea (Expanded)
Jab AI "khud-mukhtaar" bane – multiple scenarios autonomously, external systems integrate, consistency maintain, complex workflows process. Essential for apps, na ki simple chats ke liye.

### Main Areas Table (Expanded)
| Main Area                  | Kya Hai? (Easy Words) | Kyun Use Context? | Example Scenarios |
|----------------------------|-----------------------|-------------------|-------------------|
| **Handle Multiple Scenarios Autonomously** | AI khud decisions, bina human | Fast handle, upfront cover | Billing, refunds, login, escalation, edges |
| **Integrate with External Systems** | Bahar connect (API, DB) | Real-time data | Calls, queries, payments |
| **Maintain Consistency** | Same style/rules | Brand safe, no bias | Voice, policies, compliance |
| **Process Complex Workflows** | Multi-step, if-then | Logical, no confusion | Orders, decisions, trees |

### Details (Zyada Break Down)
1. **Multiple Scenarios:** Context mein rules ( "Refund >500 manager"), examples past cases. Working: AI check > action.
   **Challenges:** Sab cases sochna; solution flowcharts.
2. **External Systems:** Context mein keys/formats. Working: "Query DB [SQL here]." Tools LangChain.
   **Challenges:** Delays; solution cache.
3. **Consistency:** Start mein pin: "Polite bolo." Working: Har output check.
   **Challenges:** Updates; solution version control.
4. **Workflows:** JSON tree: {"step1": "Check", "if low": "Alternative"}. CoT use.
   **Challenges:** Loops; solution testing.

**Benefits:** Scalable, 80% accuracy up. 2025 mein enterprise apps mein must.

### Real-World Examples (Expanded)
1. **Scenarios:** Uber cancel – traffic refund auto. Swiggy late order coupon. Roz order.
2. **Integrate:** Myntra stock API + payment. Paytm bill + balance. Phone pe seamless.
3. **Consistency:** Zomato "Hungry? Order!" emails. Starbucks "Favorite latte." Coffee notifications.
4. **Workflows:** Naukri apply – resume > match > course suggest. LinkedIn interview schedule. Job hunt.
5. **Funny:** Gym app – beginner easy, integrate wearable heart, consistent "You got this!", workflow warmup-main.
6. **Extra:** HR onboarding – steps tree, API HR DB, tone professional.

**Tips:** Zapier workflows se test.

---

## Topic 4: The Six Essential Components of AI Agents
### Basic Idea (Expanded)
Har AI agent (smart robot jo tasks khud kare) ko 6 fundamental building blocks – jaise Lego bricks. Bina inke adhoora. Quote se: Model core, tools interact, knowledge store, audio natural, guardrails safe, orchestration manage.

**Burger Analogy Expanded:** Bun (model holds), Patty (core function), Veggies/Condiments (tools, knowledge, audio, guardrails flavor), Assembly (context prompt) – bina instructions mess.

### Components Table (Expanded)
| Component          | Kya Hai? (Easy) | Why Necessary? | Choose/Tips |
|--------------------|-----------------|----------------|-------------|
| **Model**         | AI engine (GPT, Claude) | Core thinking/processing | Large complex, small quick; open vs paid |
| **Tools**         | External haath (calendar, email) | Real actions | Few, secure APIs |
| **Knowledge/Memory** | Static DB + dynamic history | Smart recall | Vector DB like Pinecone |
| **Audio/Speech**  | Voice in/out | Human-like, accessible | STT/TTS tools, accent handle |
| **Guardrails**    | Safety nets (filters) | No bad behavior | Moderation API, compliance |
| **Orchestration** | Backend run (deploy, monitor) | No crash, improve | Kubernetes, logs |

### Details (Zyada)
1. **Model:** Large elephant brain (accuracy), small ant (speed). Working: Input process output. Challenge: Cost.
2. **Tools:** Examples calendar book, DB pull. Working: Call > result integrate. Challenge: Errors.
3. **Knowledge:** Legal DB, therapy notes. Working: RAG fetch. Challenge: Outdated.
4. **Audio:** Mic suno, speaker bolo. Working: Convert text-voice. Challenge: Noise.
5. **Guardrails:** Block abuse, tone pro. Working: Prompt embed + check. Challenge: Over-filter.
6. **Orchestration:** Cloud deploy, analytics. Working: A/B test. Challenge: Scale.

### Real-World Examples (Expanded)
1. **Model:** Siri small for commands, large translation. "Hey Siri call" roz.
2. **Tools:** Google Assistant calendar invite. Office meetings.
3. **Knowledge:** Netflix movies DB + history. Binge-watch personal.
4. **Audio:** Alexa "Lights on." Smart home hands-free.
5. **Guardrails:** ChatGPT "No hack." PhonePe fraud block.
6. **Orchestration:** Uber backend track/improve. Cab smooth.
7. **Full:** Groww finance – GPT advice, bank tools, history memory, voice query, safe tips, updates.
8. **Fitness:** Fitbit data analyze, GPS tools, past workouts, voice reminder, no extreme, battery monitor.

**Tips:** Lego jaise start small.

---

## Topic 5: Building AI Agents with Context Engineering
### Role of Context Engineer (Expanded)
Tu "instruction manual" ka architect – components kaise saath, tools kab, memory kaise, speech when, guardrails how, escalation kab. Yeh agent ko plug-and-play banata.

### Prompt Complexity (Expanded)
Prompts large docs ban jaate: 1000+ words, XML <tool>call</tool>, markdown bullets, code-like if-then, saare scenarios (normal/error/rare).

**Challenges:** Token cross; solution compress. Tools LangChain multi-agent.

### Manual Parts Table (Expanded)
| Part of Manual                  | Kya Hai? | Kaise? | Why? |
|---------------------------------|----------|--------|------|
| **Components Together** | Glue bricks | Flow: Model > Tool > Memory | Smooth chal |
| **Tools Use** | Kab/kaise connect | <tool>API with params</tool> | Power without waste |
| **Memory Access** | Past pull | Retrieve [history] | Personal |
| **Speech/Audio** | Voice switch | If hands-free, TTS | Natural |
| **Guardrails** | Rules follow | Embed "Polite only" | Trust |
| **Escalation** | Human bhej | Confidence <70% | Limits jaano |

### Details (Zyada)
1. **Together:** Flowchart prompt mein.
2. **Tools:** Conditional "If schedule, call."
3. **Memory:** "User orders se suggest."
4. **Speech:** "Voice input? Output audio."
5. **Guardrails:** Auto-moderate.
6. **Escalation:** Log + ticket.

### Real-World Examples (Expanded)
1. **Smart Home:** Google Home – audio query, model soch, light tool, memory prefs, guard privacy, escalate complex. Setup ghar pe.
2. **Shopping Agent:** Flipkart – buy tool payment, memory history, speech "Order place?", guard no fraud, escalate stock out.
3. **Fitness Coach:** MyFitnessPal – history access past weak, voice gym mein, guard safe diet, escalate doctor.
4. **Support Bot:** HDFC bank – <step>login check</step>, knowledge FAQ, tone polite, escalate fraud.
5. **Funny:** Bumble dating – memory likes, tool swipe API, speech icebreaker, guard respect, escalate creepy.
6. **Extra:** Travel agent – components coordinate flight book, memory budget.

**Tips:** Notion AI se simple manual bana.

---

## Topic 6: Real-World Example: AI Research Assistant
### Basic Idea (Expanded)
Yeh ek practical prompt example – AI query pe subtasks bana, sources se trends dhund, JSON output, 300 words summary. Single-agent simple, real mein multi (search agent + summarize).

**Why Useful?** Autonomous research, fresh 10 days data, web tool access.

### Structure Details (Zyada)
1. **Role Definition:** "Tu assistant, trends identify multiple sources se, subtasks bana, insights engagement/authority pe."
2. **Task Breakdown:** Step1: 10 diverse subtasks (angles/sources). Step2: Prioritize likes/citations. Step3: JSON each. Step4: Dates UTC ISO (current -10 days). Step5: Concise summary.
3. **Input:** <user_query>AI trends</user_query> – structured.
4. **Output:** JSON {"id":"1", "query":"sub", "source":"news", "time":"1-10", "focus":"tech", "priority":"1", "start":"2025-10-07T00:00:00Z", "end":"2025-10-17T23:59:59Z"}.
5. **Final:** Bullets, new developments only, no fluff.
6. **Constraints:** Succinct, no grammar worry, ignore background.
7. **Capabilities:** Web search, current date aware, 10 days filter.

**Implementation Notes:** Split agents for scale – Agent1 gather, Agent2 synthesize.

### Live Example (Expanded – Recent AI Trends, Oct 7-17 2025)
Query: Recent AI trends. Subtasks JSON (sample 3):  
{"id":"1", "query":"Agentic AI news", "source":"news", "priority":"1", ...}  
Summary (150 words):  
- **Agentic Surge:** 78% companies experimenting, OpenAI builder 80% AI-coded.  
- **Generative Exponential:** Compute scaling, AI designs AI.  
- **Specialized Models:** Custom over general, 10x cheaper inference.  
- **Reasoning Advances:** Post-training boosts, edge multimodal.  
- **Challenges:** Energy, bias, hallucinations.

### Real-World Examples (Expanded)
1. **Student Research:** "Climate change." Subtasks news/academic, summary UN policy floods. Google Scholar mix, exam prep.
2. **Job Hunter:** "AI jobs." LinkedIn authority, summary salaries up 15%. Naukri update.
3. **Business Update:** "Social AI tools." X engagement, summary voice ads 78%. Instagram content.
4. **Funny:** "Dating AI." Reddit sources, summary new apps buzz, safe guardrails.
5. **Extra:** Marketing trends – newsletter focus, priority high-views.

**Tips:** Grok mein try similar prompt.

---

## Topic 7: Advanced Context Engineering Strategies
### Basic Idea (Expanded)
Basic se aage: Context ko smart manage – write notes, select relevant, compress overload, isolate secure + multi-agent share. Yeh efficiency badhata, hallucinations kam.

### Strategies Table (Expanded)
| Strategy              | Kya Hai? | How? | Benefits | Challenges |
|-----------------------|----------|------|----------|------------|
| **Writing Context** | AI notes likhe (tasks, results) | Prompt "Notes likh [section]" | Track progress | Notes long |
| **Selecting** | External relevant pull | RAG query/fetch | Fresh targeted | Slow APIs |
| **Compressing** | Shrink (summarize, extract) | LLM summarize, embeddings | Token save | Miss important |
| **Isolating** | Alag compartments | Separate DBs | Privacy focus | Sync sharing |

### Details (Zyada)
1. **Writing:** Decomposition notes, rationales. Save vector stores. 2025 coding agents mein use.
2. **Selecting:** DB task-based, user prefs. Dynamic RAG.
3. **Compressing:** Hierarchical folders, token-efficient JSON. LlamaIndex tools.
4. **Isolating:** Task/user/temporal, encryption.

**Multi-Agent Sharing:** Always share common, actions implicit decisions careful. Central hub message pass.

### Real-World Examples (Expanded)
1. **Writing:** Cursor AI "Function rationale: Loop efficiency." VS Code debug.
2. **Selecting:** Netflix API history select matching shows. Streaming personal.
3. **Compressing:** ChatGPT history summarize key points. Office emails.
4. **Isolating:** PhonePe transactions user-alag. Galileo avoid poisoning.
5. **Multi:** Manus resume – gather agent pass digest to analyze. LinkedIn team.
6. **Extra Funny:** News app A47 – 47 anchors shared context 24/7 news. Phone news.

**Tips:** LangChain compressing try.

---

## Topic 8: Best Practices and Resources
### Essential Guidelines (Expanded Table)
| Guideline                  | Kya Hai? | How Apply? | Why? | Challenge/Solution |
|----------------------------|----------|------------|------|--------------------|
| **Structure Key** | XML/markdown clear | <tag> sections, bullets | Easy parse | Token waste / Minimal use |
| **Comprehensive** | All scenarios anticipate | If-then rules, trees | Handle unexpected | Time / Brainstorm sessions |
| **Test Extensively** | Edge cases break | Promptfoo simulate A/B | Strong system | Time-consuming / Automate |
| **Iterate Usage** | Monitor real, improve | Analytics logs feedback | Evolve | Privacy / Anonymize data |
| **Security Mind** | Guardrails proper | Embed rules, APIs | Safe legal | Over-strict / Balance test |

### Resources (Expanded with 2025 Updates)
1. **Cognition Blog:** Multi-agent – sharing, decisions. Key: Don't over-multi. 2025 June post "Don't Build Multi-Agents" hit, single with context better. Link: cognition.ai/blog. Apply: Devin coding.
2. **LangChain Guide:** Strategies implement. 2025 July "Context for Agents" – window art. Link: blog.langchain.com. Apply: Dynamic bots.

### Implementation Tools (Expanded)
- **No-Code:** NAT/Zapier – drag-drop, auto-manage. Example: Email-Slack.
- **Code-Based:** OpenAI SDK/LangChain – Python control. n8n compress 2025.
- **Agnostic:** Prompts cross models. Example: Research same Grok/GPT.

### Real-World Examples (Expanded)
1. **Structure:** Gmail bullet replies consistent.
2. **Comprehensive:** Uber cancel paths.
3. **Test:** Netflix no-history fallback.
4. **Iterate:** Spotify skip-based better songs.
5. **Security:** SBI fraud block.
6. **Extra:** UiPath workflows 2025 reliable, GitHub Copilot edges 50% less bugs.

**Tips:** Project le structure shuru.

---

## Topic 9: Assessment Questions
### Quiz 1: Basic Understanding (Expanded)
**Q:** Prompt vs Context main difference?  
**A:** Prompt conversational iterative refine; Context apps ke liye comprehensive standalone autonomous scenarios.  
**Explanation:** Prompt react, context predict. Example: Chat vs app.

### Quiz 2: AI Agent Components (Expanded)
**Q:** 6 components name + why?  
**A:**  
- Model: Processing power – sochne ke liye.  
- Tools: Integrate external – actions.  
- Knowledge/Memory: Store/retrieve – yaad.  
- Audio/Speech: Natural capabilities – voice.  
- Guardrails: Safety/compliance – proper.  
- Orchestration: Deploy/monitor – run/improve.  
**Explanation:** Burger parts jaise. Example: Siri full.

### Quiz 3: Practical Application (Expanded)
**Q:** Customer service agent scenarios?  
**A:** Billing/refund issues, login, terms queries, irrelevant, abusive, escalation, knowledge access, tone maintenance.  
**Explanation:** Rules daalo. Example: Amazon all cover.

### Examples (Expanded)
1. **Quiz 1:** WhatsApp refine vs Netflix standalone.
2. **Quiz 2:** Siri model/tools etc.
3. **Quiz 3:** Amazon billing to tone.
4. **Extra:** Test khud le, score bata.

**Tips:** Revision ke liye use.

---

## Topic 10: Conclusion
### Key Ideas (Expanded)
**Evolution:** Prompt se context – complex apps ke liye upgrade, multi-step autonomous. 2025 less human, intelligent models.  
**Architect Systems:** Comprehensive instructions – components + safe real-world. Dynamic management.  
**Crucial Real-World:** Effective safe operation, multi-agents frontier. Interoperability MCP.  
**Evolving Field:** Stay updated frameworks, context #1 job. AI Index 2025 productivity.  
**Tips:** Start simple, test thorough, iterate performance. Train oversight.

### 2025 Trends Table (Expanded)
| Point | Trend | Example |
|-------|-------|---------|
| Evolution | Less human intervention | Gemini trip auto |
| Architect | Right time/format info | Alexa dynamic |
| Real-World | Multi-agent teams | Uber route optimize |
| Updated | Context discipline | Netflix MCP |
| Tips | Human-AI workflows | Spotify feedback |

### Real-World Examples (Expanded)
1. **Evolution:** Google Gemini full plan vs old assistant.
2. **Systems:** Alexa shopping history + safe.
3. **Operation:** Uber multi safe drive.
4. **Updated:** Netflix trends protocols.
5. **Tips:** Instagram bot sales iterate.
6. **Funny:** Peloton coach – evolution voice, systems plan, operation safe, updated trends, tips user feedback.
7. **Extra:** Travel app hours plan compaction.

**Motivation:** Architect ban, build kar!

---

## Topic 11: Must Read - Effective Context Engineering for AI Agents
### Main Idea (Expanded)
Context evolution prompt se – optimize full tokens for behavior. Sawal: "Best config konsa?" Agents turns mein data refine curate. Anthropic 2025: Smallest high-signal tokens.

**Viewpoints:** Detailed + brief checklist. Finite context, rot se degrade.

### Key Concepts (Expanded)
1. **From Prompt to Context:** Prompt instructions, context full state (tools/data/history). Cycles refine. Working: Turn pe trim/add.
   **Example:** Netflix session history curate.
2. **Core Challenge:** Attention budget, quadratic scaling, short training. Rot: Recall drop long mein. Manage scarce.
   **Example:** Maps zoom details only.

### Best Practices (Expanded)
1. **System Prompt:** Goldilocks – sectioned heuristics, no brittle/vague. Test hard cases.
   **Example:** ChatGPT polite steps.
2. **Tools:** Paginate/filter, unambiguous names/docs. Defaults, no overlap.
   **Example:** Zapier relevant fields.
3. **Curation:** High-signal small set, upfront minimal, just-in-time RAG hybrid. Progressive disclosure.
   **Example:** Amazon list then details.

### Long-Horizon Tactics (Expanded)
- **Compaction:** Summarize trace, restart distilled (recall > prune). Clear old outputs.
- **Note-Taking:** Persist TODO/decisions outside, re-inject.
- **Sub-Agents:** Specialized deep, coordinator digest.
- **Principle:** Simple works, context precious.

**Example:** Copilot code session summarize notes sub-debug.

### Checklist (Expanded with How)
1. **Minimal Prompt:** Sectioned, test add targeted. (Role bullets.)
2. **Trim Tools:** Obvious params efficient. (Few clear.)
3. **3-7 Examples:** Canonical few-shot, no edges. (Best cases.)
4. **Tiny + Fetch:** Instructions refs shuru, tools runtime. (Hybrid.)
5. **Long:** Schedule compaction, NOTES memory, sub-agents dives. (Marathon tactics.)

### Real-World Examples (Expanded)
1. **Concepts:** Netflix long binge curate.
2. **Practices:** Banking prompt Goldilocks.
3. **Tools:** Workflow filter inbox.
4. **Curation:** Shopping just-in-time.
5. **Tactics:** GitHub hours code compaction.
6. **Funny:** Dating chat summarize history, notes likes, sub icebreaker.
7. **Extra:** Finance long plan – checklist Groww portfolio.

**Tips:**  Checklist project apply, Anthropic Claude try.

---

**End of Expanded Notes!** 