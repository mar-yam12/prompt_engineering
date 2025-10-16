# Context Engineering Tutorial: Full Notes (Topics 1 to 11) – Expanded Edition
##  Simple English, More Details and Real Examples
**Date:** October 17, 2025  
**Compiled By:** **Maryam Shahid**  


---

## Topic 1: What is Context Engineering?
### Simple Definition (Expanded)
Hey, straight up: Context Engineering is the way we give a Large Language Model (LLM) – like me (Grok) or ChatGPT – the right information, in the right format, at the right time so it does a specific task really well. It's not just writing a prompt, but smartly packing the "context window" (the LLM's input area where we put all info, like up to 128k tokens). Like packing a suitcase for travel – everything in place, no waste, and key things on top so you grab them fast at the airport.

In easy words: It's making a "perfect guidebook" for AI, with only the pages that help, so AI doesn't get confused and gives quick, accurate answers. From the quote: "Strategically packing the context window to maximize effectiveness."

**Key Point from André Karpathy:** LLM is the CPU (brain that thinks), context window is RAM (short-term memory that holds stuff temporarily). Context Engineering optimizes that RAM, so more work happens without crashing or slowing down.

### Working in Easy Steps (More Details)
1. **Identify Context:** First, decide what's needed for the task. Like for medical advice, symptoms + history + WHO guidelines.
2. **Build Structure:** Break info into chunks – headings, bullet points, JSON format. Makes it easy for AI to parse (understand).
3. **Filter Relevance:** Don't add everything, only what's useful. Use vector search tools (like FAISS) to pull similar data.
4. **Inject into Prompt:** Put context at the start of the prompt: "Based on this [context], answer..."
5. **Iterate & Test:** Check output, tweak it. Boost token efficiency.

Technically: LLMs use attention, focused context gives better weights.

### Full Components and Benefits (Expanded)
- **Static vs Dynamic Context:** Static is fixed (company policy), dynamic updates in real-time (user query).
- **Compression:** Summarize long docs.
- **Multi-Modal:** Text + images (add captions).
- **CoT Integration:** Add step-by-step reasoning.
- **Guardrails:** "No illegal advice."
- **Memory:** Summarize previous stuff.

**Benefits:** Less hallucinations, 10x better output, saves cost.  
**Challenges:** Token limits, bias – solution: A/B test.

### Real-World Examples (Expanded)
1. **Kitchen Recipe App:** Without: Generic curry. With context: Allergies (skip nuts), fridge (no garlic), time (15 min). Result: "Chicken + tomato quick." Real: Zomato personalized, try at home.
2. **Office Email Reply:** Boss "Report?" Without: Boring. Context: Past emails, deadlines, style. Result: "Q3 up 15%, graph attach." Real: Gmail, saves time for freelancers.
3. **Online Shopping:** "Shoes." Context: History (running), budget (2000), weather (waterproof). Result: 3 options. Real: Amazon, daily buys.
4. **Student Homework:** "Math solve." Context: Chapter, past mistakes, steps. Result: Graph + explain. Real: Khan Academy tutor.
5. **Doctor App:** "Headache." Context: Age, records, meds. Result: "Rest + paracetamol." Real: Practo, like COVID telehealth.
6. **Funny Extra:** Dating app – profile + likes, "Cricket fan? Watch a match!" Like Tinder.

**Tips:** Start with small projects, test with Promptfoo.

---

## Topic 2: Context Engineering vs Prompt Engineering
### Basic Difference (Expanded)
**Prompt Engineering:** For direct talks, like chatting with ChatGPT – ask a question, get answer, refine it. Casual, back-and-forth, step-by-step improvement.  
**Context Engineering:** For building AI apps/agents, like a customer bot – full instructions, standalone (runs on its own), plan all scenarios ahead. Advanced, feels like code.

From quote: Prompt is conversational, Context is evolution for complex – no real-time tweaks, predict everything.

### Comparison Table (Expanded)
| Aspect              | Prompt Engineering                          | Context Engineering                          |
|---------------------|---------------------------------------------|---------------------------------------------|
| **Use Case**        | Direct talks (discuss shoes: cushion, price) | Apps (customer agent: order, refund) |
| **Nature**          | Back-and-forth, step-by-step                | Standalone, full coverage                   |
| **Complexity**      | Simple, short prompts                       | Complex, XML tags/markdown, code-like       |
| **When to Use**     | Quick personal answers                      | Production apps, for speed/accuracy         |
| **Pros**            | Fast to learn, fun                          | Scalable, runs alone                        |
| **Cons**            | Doesn't scale, more errors in long tasks    | Takes time to set up, lots of testing       |

**Why the Difference Matters?** In apps, customers won't wait for tweaks, so plan ahead. Use hybrid: Get ideas from prompts, turn into context.

### Working Mechanism (More Steps)
**Prompt:** 1. Write prompt. 2. Get answer. 3. Refine if needed. Easy, human helps.  
**Context:** 1. Build full data/rules. 2. Add to prompt. 3. Runs alone. Use XML like <user>budget</user>.

### Pros/Cons and Integration
Prompt: Pros fast, cons not for big scale. Context: Pros accurate, cons hard start. Integrate: Mix in LangChain.

### Real-World Examples (Expanded)
1. **Shopping:** Prompt: WhatsApp chat about shoes, tweak price. Context: Flipkart app uses history for list, no chat. Real: Instagram vs Amazon.
2. **Health App:** Prompt: Google "Headache," add fever. Context: Practo uses symptoms + records for diagnosis. COVID apps.
3. **Coding Help:** Prompt: ChatGPT function, fix error in chat. Context: VS Code Copilot uses codebase + rules for full code. Freelance work.
4. **Customer Service:** Prompt: Emails back-and-forth. Context: Zendesk bot uses details + policy for instant fix. Jio support.
5. **Gym Trainer:** Prompt: "Give plan," tweak it. Context: App uses weight + goals + equipment for full plan. Cult.fit.
6. **Extra:** Office meeting – prompt discusses agenda, context auto-books calendar.

**Tips:** Practice with prompts first, then shift to context for apps.

---

## Topic 3: When to Use Context Engineering
### Basic Idea (Expanded)
Use it when AI needs to work alone – handle many situations on its own, connect to outside systems, keep things consistent, and process tricky step-by-step jobs. Key for apps, not simple chats.

### Main Areas Table (Expanded)
| Main Area                  | What It Is (Easy Words) | Why Use Context? | Example Scenarios |
|----------------------------|-------------------------|------------------|-------------------|
| **Handle Multiple Scenarios Autonomously** | AI makes decisions alone, no human | Quick handling, plan ahead | Billing, refunds, login, escalation, rare cases |
| **Integrate with External Systems** | Connect to outside (API, database) | Get real-time data | Calls, queries, payments |
| **Maintain Consistency** | Same style and rules always | Keeps brand safe, no bias | Voice/tone, policies, laws |
| **Process Complex Workflows** | Multi-steps, if-then choices | Logical flow, no mix-up | Orders, decision trees |

### Details (More Break Down)
1. **Multiple Scenarios:** Add rules to context ("Refund over 500? Manager OK"). Examples of past cases. How: AI checks then acts.
   **Challenges:** Thinking of all cases; fix with flowcharts.
2. **External Systems:** Add keys/formats to context. How: "Query database [SQL code]." Use LangChain tools.
   **Challenges:** Slow delays; fix with cache.
3. **Consistency:** Pin at start: "Always be polite." How: Check every output.
   **Challenges:** Rules change; fix with version control.
4. **Workflows:** JSON tree in context: {"step1": "Check stock", "if low": "Suggest other"}. Use Chain of Thought.
   **Challenges:** Loops; fix with testing.

**Benefits:** Makes things scalable, 80% better accuracy. In 2025, must for big company apps.

### Real-World Examples (Expanded)
1. **Scenarios:** Uber ride cancel – auto refund for traffic. Swiggy late order gives coupon. Daily food orders.
2. **Integrate:** Myntra checks stock API + payment. Paytm pulls balance + pays bill. Smooth on phone.
3. **Consistency:** Zomato emails always "Hungry? Order now!" Starbucks "Your favorite latte." Coffee alerts.
4. **Workflows:** Naukri job apply – upload resume > match jobs > suggest course if no fit. LinkedIn schedules interview. Job search.
5. **Funny:** Gym app – easy for beginners, pulls heart from wearable, always "You got this!", flow from warmup to cool down.
6. **Extra:** HR new hire – step tree, connects to HR database, professional tone.

**Tips:** Test with Zapier for workflows.

---

## Topic 4: The Six Essential Components of AI Agents
### Basic Idea (Expanded)
Every AI agent (smart robot that does tasks alone) needs 6 basic building blocks – like Lego pieces. Without them, it's incomplete. From quote: Model is core, tools connect out, knowledge stores info, audio makes natural talk, guardrails keep safe, orchestration runs and fixes.

**Burger Analogy Expanded:** Bun (model holds it all), Patty (main power), Veggies/Condiments (tools, knowledge, audio, guardrails add flavor), Assembly (context prompt) – without instructions, it's a mess.

### Components Table (Expanded)
| Component          | What It Is (Easy) | Why Necessary? | Choose/Tips |
|--------------------|-------------------|----------------|-------------|
| **Model**         | AI engine (GPT, Claude) | Core thinking/processing | Large for tough jobs, small for quick; open or paid |
| **Tools**         | Outside hands (calendar, email) | Real actions | Keep few, secure APIs |
| **Knowledge/Memory** | Fixed database + changing history | Smart recall | Use vector DB like Pinecone |
| **Audio/Speech**  | Voice in/out | Human-like, easy access | STT/TTS tools, handle accents |
| **Guardrails**    | Safety nets (filters) | No bad actions | Moderation API, follow laws |
| **Orchestration** | Back-end run (deploy, watch) | No crashes, get better | Kubernetes, check logs |

### Details (More)
1. **Model:** Large like elephant brain (high accuracy), small like ant (fast). How: Takes input, processes, gives output. Challenge: High cost.
2. **Tools:** Like calendar to book, database to pull. How: Call tool > mix result. Challenge: Errors.
3. **Knowledge:** Legal files, therapy notes. How: RAG to fetch. Challenge: Old info.
4. **Audio:** Mic listens, speaker talks. How: Turn text to voice. Challenge: Noisy places.
5. **Guardrails:** Block rude words, keep pro tone. How: Add to prompt + check. Challenge: Too strict.
6. **Orchestration:** Put on cloud, track stats. How: A/B test versions. Challenge: Handle big users.

### Real-World Examples (Expanded)
1. **Model:** Siri uses small for commands, large for translate. "Hey Siri call mom" daily.
2. **Tools:** Google Assistant books calendar invite. Office meetings.
3. **Knowledge:** Netflix movie database + your history. Makes binge personal.
4. **Audio:** Alexa "Turn lights on." Smart home no hands.
5. **Guardrails:** ChatGPT says no to illegal. PhonePe blocks fraud.
6. **Orchestration:** Uber back-end tracks rides, improves paths. Cab rides smooth.
7. **Full:** Groww money app – GPT for tips, bank tools, history memory, voice ask, safe advice, auto updates.
8. **Fitness:** Fitbit checks data, GPS tools, old workouts, voice reminders, no crazy diets, watches battery.

**Tips:** Start like Lego – small builds.

---

## Topic 5: Building AI Agents with Context Engineering
### Role of Context Engineer (Expanded)
You are the "instruction manual" builder – how parts work together, when to use tools, how to get memory, when speech, how guardrails, when to call human. Makes agent ready to plug in and go.

### Prompt Complexity (Expanded)
Prompts turn into big docs: 1000+ words, XML <tool>call calendar</tool>, markdown bullets, code-like if-then, cover all cases (normal/error/rare).

**Challenges:** Hits token limit; fix by compressing. LangChain for multi-agents.

### Manual Parts Table (Expanded)
| Part of Manual                  | What It Is? | How? | Why? |
|---------------------------------|-------------|------|------|
| **Components Together** | Glue the pieces | Flow: Model thinks > Tool acts > Memory checks | Runs smooth |
| **Tools Use** | When/how to connect | <tool>API with details</tool> | Power without waste |
| **Memory Access** | Pull past info | Get [history] | Makes personal |
| **Speech/Audio** | When to use voice | If no hands, use TTS | Feels natural |
| **Guardrails** | Follow safety | Add "Be polite only" | Builds trust |
| **Escalation** | Send to human | If sure <70% | Knows limits |

### Details (More)
1. **Together:** Put flowchart in prompt.
2. **Tools:** "If about time, call calendar."
3. **Memory:** "Suggest from user orders."
4. **Speech:** "Voice in? Voice out."
5. **Guardrails:** Auto check for bad.
6. **Escalation:** Log it + send ticket.

### Real-World Examples (Expanded)
1. **Smart Home:** Google Home – voice query, model thinks, light tool, memory likes dark, guard privacy, escalate hard stuff. Set up at home.
2. **Shopping Agent:** Flipkart – payment tool call, memory history, voice "Order done?", guard no scams, escalate no stock.
3. **Fitness Coach:** MyFitnessPal – access past weak spots, voice in gym, guard safe food, escalate to doctor.
4. **Support Bot:** HDFC bank – <step>check login</step>, FAQ knowledge, polite tone, escalate fraud.
5. **Funny:** Bumble dating – memory likes, swipe tool, voice icebreaker, guard respect, escalate weird.
6. **Extra:** Travel agent – parts team up for flight book, memory budget.

**Tips:** Make simple manual in Notion AI.

---

## Topic 6: Real-World Example: AI Research Assistant
### Basic Idea (Expanded)
This is a real prompt example – AI takes query, makes subtasks, finds trends from sources, JSON output, 300-word summary. Simple single-agent, but in real life split multi (one searches, one sums up).

**Why Useful?** Does research alone, fresh 10-day data, uses web tool.

### Structure Details (More)
1. **Role Definition:** "You are assistant, find and sum trends from many sources, break into subtasks, pick best insights by likes/experts."
2. **Task Breakdown:** Step1: Up to 10 different subtasks (angles/sources). Step2: Rank by likes/cites. Step3: JSON for each. Step4: Dates in UTC ISO (now -10 days). Step5: Short summary.
3. **Input:** <user_query>AI trends</user_query> – keeps it neat.
4. **Output:** JSON like {"id":"1", "query":"sub", "source":"news", "time":"1-10", "focus":"tech", "priority":"1", "start":"2025-10-07T00:00:00Z", "end":"2025-10-17T23:59:59Z"}.
5. **Final:** Bullets, only new big stuff, no extra words.
6. **Constraints:** Keep short, no grammar stress, skip old talk.
7. **Capabilities:** Web search okay, know today's date, only 10 days old.

**Implementation Notes:** Split for big scale – Agent1 gathers, Agent2 puts together.

### Live Example (Expanded – Recent AI Trends, Oct 7-17 2025)
Query: Recent AI trends. Sample 3 subtasks in JSON:  
{"id":"1", "query":"Agentic AI news", "source":"news", "priority":"1", ...}  
Summary (150 words):  
- **Agentic Surge:** 78% companies trying, OpenAI builder 80% AI-written code.  
- **Generative Exponential:** More compute, AI builds better AI.  
- **Specialized Models:** Custom beats general, 10x cheaper run.  
- **Reasoning Advances:** Extra training helps think, edge and multi-sense rising.  
- **Challenges:** Power use, bias, fake info walls.

### Real-World Examples (Expanded)
1. **Student Research:** "Climate change." Subtasks news/academic, sum UN policy on floods. Mix Google Scholar, exam help.
2. **Job Hunter:** "AI jobs." LinkedIn for experts, sum pay up 15%. Update Naukri.
3. **Business Update:** "Social AI tools." X for likes, sum voice ads 78%. Instagram posts.
4. **Funny:** "Dating AI." Reddit sources, sum new app buzz, safe rules.
5. **Extra:** Marketing – newsletter focus, high-view rank.

**Tips:** Try similar prompt in Grok.

---

## Topic 7: Advanced Context Engineering Strategies
### Basic Idea (Expanded)
Beyond basics: Smart handle context – let AI write notes, pick right info, shrink overload, keep separate for safe + share smart in multi-agents. Boosts efficiency, cuts fake answers.

### Strategies Table (Expanded)
| Strategy              | What It Is? | How? | Benefits | Challenges |
|-----------------------|-------------|------|----------|------------|
| **Writing Context** | Let AI write notes (tasks, results) | Prompt "Write notes [section]" | Tracks steps | Notes get long |
| **Selecting** | Pull only right outside info | RAG query/fetch | Fresh and aimed | Slow outside calls |
| **Compressing** | Shrink (sum up, pull keys) | AI sum, embeddings | Saves tokens | Might miss key bits |
| **Isolating** | Keep in separate spots | Different databases | Privacy and focus | Hard to share when needed |

### Details (More)
1. **Writing:** Break tasks, explain choices. Save in vector stores. 2025 coding agents use it.
2. **Selecting:** Database on task, user likes. Dynamic RAG.
3. **Compressing:** Folder-like levels, short JSON. LlamaIndex tools.
4. **Isolating:** For task/user/time, lock with code.

**Multi-Agent Sharing:** Share common always, watch hidden choices in actions. Use central spot or pass messages.

### Real-World Examples (Expanded)
1. **Writing:** Cursor AI "Why this function: Loop for speed." VS Code fix bugs.
2. **Selecting:** Netflix pulls your watch history for matches. Streaming feels yours.
3. **Compressing:** ChatGPT sums old chats to keys. Office email quick.
4. **Isolating:** PhonePe keeps your money moves separate. Galileo stops bad mix.
5. **Multi:** Manus checks resume – gather agent sends short sum to checker. LinkedIn teams.
6. **Extra Funny:** News app A47 – 47 AI hosts share info for 24/7 news. Phone reads.

**Tips:** Try compressing in LangChain.

---

## Topic 8: Best Practices and Resources
### Essential Guidelines (Expanded Table)
| Guideline                  | What It Is? | How to Apply? | Why? | Challenge/Fix |
|----------------------------|-------------|---------------|------|---------------|
| **Structure is Key** | Use XML/markdown clear | <tag> for parts, bullets | Easy for AI to read | Wastes tokens / Use just enough |
| **Be Comprehensive** | Plan all situations | If-then rules, trees | Handles surprises | Takes time / Brainstorm first |
| **Test Extensively** | Check edge cases that break | Promptfoo fake tests, A/B | Makes strong | Slow / Auto tools |
| **Iterate on Usage** | Watch real use, fix | Stats, logs, feedback | Gets better over time | Keep data private / Hide names |
| **Keep Security in Mind** | Add good guardrails | Put rules in, use check APIs | Safe and legal | Too tight / Test balance |

### Resources (Expanded with 2025 Updates)
1. **Cognition Blog:** Multi-agent rules – share info, watch choices. Key: Don't make too many agents. 2025 June post "Don't Build Multi-Agents" big hit, single with good context wins. Link: cognition.ai/blog. Use: Devin code agent.
2. **LangChain Guide:** How to do strategies. 2025 July "Context for Agents" – art of filling window. Link: blog.langchain.com. Use: Build dynamic bots.

### Implementation Tools (Expanded)
- **No-Code:** NAT/Zapier – drag and drop, auto handle. Example: Email to Slack flows.
- **Code-Based:** OpenAI SDK/LangChain – code in Python for control. n8n shrinks in 2025.
- **Any Platform:** Prompts work on all models. Example: Same research on Grok or GPT.

### Real-World Examples (Expanded)
1. **Structure:** Gmail bullet replies always neat.
2. **Comprehensive:** Uber cancel has all paths ready.
3. **Test:** Netflix tests for users with no history.
4. **Iterate:** Spotify changes songs on skips.
5. **Security:** SBI blocks bad money questions.
6. **Extra:** UiPath 2025 workflows reliable, GitHub Copilot cuts bugs 50% with edges.

**Tips:** Pick a project, start with structure.

---

## Topic 9: Assessment Questions
### Quiz 1: Basic Understanding (Expanded)
**Q:** Main difference between prompt and context engineering?  
**A:** Prompt is for chats where you tweak step-by-step; Context is for apps with full standalone plans that handle everything alone.  
**Explanation:** Prompt reacts, context plans ahead. Example: Chat vs app.

### Quiz 2: AI Agent Components (Expanded)
**Q:** Name 6 components and why each?  
**A:**  
- Model: Processing power – to think.  
- Tools: Outside connect – for actions.  
- Knowledge/Memory: Store/pull – to remember.  
- Audio/Speech: Natural skills – for voice.  
- Guardrails: Safety/rules – to stay right.  
- Orchestration: Run/watch – to keep going and fix.  
**Explanation:** Like burger parts. Example: Siri uses all.

### Quiz 3: Practical Application (Expanded)
**Q:** For customer service AI, what scenarios in context?  
**A:** Money issues, refunds, login help, rules questions, off-topic, rude talk, send to human, pull info base, keep good tone.  
**Explanation:** Add rules for each. Example: Amazon covers all.

### Examples (Expanded)
1. **Quiz 1:** WhatsApp tweak vs Netflix alone.
2. **Quiz 2:** Siri brain/tools etc.
3. **Quiz 3:** Amazon from money to tone.
4. **Extra:** Test yourself, tell score.

**Tips:** Use for quick review.

---

## Topic 10: Conclusion
### Key Ideas (Expanded)
**Evolution:** From prompt to context – upgrade for tough apps, alone steps. 2025: Less human help, smarter models.  
**Build Systems:** Full instructions – parts + safe real use. Dynamic handle info.  
**Key for Real World:** Good safe work, multi-agents leading. Connect protocols like MCP.  
**Fast Changing Field:** Learn new tools, context top job. 2025 AI report: Boosts work speed.  
**Tips:** Start easy, test full, fix on real results. Train on watch + human-AI mix.

### 2025 Trends Table (Expanded)
| Point | Trend | Example |
|-------|-------|---------|
| Evolution | Less human, smart models | Gemini auto trip |
| Build | Right time/format info | Alexa changes live |
| Real World | Multi-agent teams | Uber path fix |
| Learn New | Context as main skill | Netflix connect |
| Tips | Human-AI team work | Spotify user fix |

### Real-World Examples (Expanded)
1. **Evolution:** Google Gemini full plan vs old helper.
2. **Systems:** Alexa shop with history + safe.
3. **Real World:** Uber multi for safe rides.
4. **Learn New:** Netflix trends with protocols.
5. **Tips:** Instagram bot fixes on sales.
6. **Funny:** Peloton coach – smart voice, full plan, safe work, new trends, user fixes.
7. **Extra:** Travel app plans hours with shrink.

**Motivation:** Become builder, make stuff!

---

## Topic 11: Must Read - Effective Context Engineering for AI Agents
### Main Idea (Expanded)
Context beats prompt – set up all tokens for right actions. Question: "What setup gives best output?" Agents do many steps, refine data cycles. Anthropic 2025: Smallest top tokens.

**Views:** Full details + short checklist. Context limited, gets worse with more (rot).

### Key Concepts (Expanded)
1. **From Prompt to Context:** Prompt just guides, context full setup (tools/data/history). Refine in loops. How: Each step trim/add.
   **Example:** Netflix long watch curates history.
2. **Main Challenge:** Attention limit, grows slow (square math), trained short. Rot: Forgets in long. Treat like rare stuff.
   **Example:** Maps shows only zoom details.

### Best Practices (Expanded)
1. **System Prompt:** Goldilocks – clear sections, tips not hard rules. Test tough spots.
   **Example:** ChatGPT polite steps.
2. **Tools:** Break pages/filter, clear names/docs. Set defaults, no repeats.
   **Example:** Zapier takes only needed fields.
3. **Curation:** Pick top small tokens, load little first, get more as needed (RAG mix). Show step-by-step.
   **Example:** Amazon list then full info.

### Long-Horizon Tactics (Expanded)
- **Compaction:** Sum path now and then, restart clean (remember first, cut after). Clear old tool results.
- **Note-Taking:** Save TODO/choices outside, add back later.
- **Sub-Agents:** Special ones dig deep, main gets short sum.
- **Rule:** Easy thing that works, treat context like gold.

**Example:** Copilot code long – sums code, saves notes, separate debug helper.

### Checklist (Expanded with How)
1. **Minimal Prompt:** Sections, test and add aimed. (Role in bullets.)
2. **Trim Tools:** Clear details, low use. (Few and simple.)
3. **3-7 Examples:** Top few-shot, cut mess. (Good cases only.)
4. **Small Start + Get Later:** Guide + quick refs first, tools for more. (Mix way.)
5. **Long Jobs:** Plan sums, NOTES save, sub-helpers for deep. (Run tactics.)

### Real-World Examples (Expanded)
1. **Concepts:** Netflix long binge curates.
2. **Practices:** Bank prompt just right.
3. **Tools:** Flow picks inbox parts.
4. **Curation:** Shop gets details later.
5. **Tactics:** GitHub hours code with sum.
6. **Funny:** Dating chat sums history, notes likes, sub for open lines.
7. **Extra:** Money long plan – checklist for Groww money sum.

**Tips:** Use checklist on project, try Anthropic Claude.

---

**End of Expanded Notes!** 