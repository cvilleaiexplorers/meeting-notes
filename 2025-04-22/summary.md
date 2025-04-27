## **Summary:**
**1. Speaker Background (John Berryman):**
- Started in aerospace engineering; moved into search technology.
- Worked at OpenSource Connections, EventBrite, GitHub (on search), and was an early production engineer for GitHub Copilot.
- Wrote books about his experiences; now runs an independent consultancy (Arur Labs).
**2. Format of the Talk:**
- Compressed a multi-day course into a 45-minute session by audience vote.
- Covered prompt engineering, RAG (Retrieval-Augmented Generation), agentic AI, evaluation, and fine-tuning.
---
## **Key Insights:**
### **Prompt Engineering:**
- **Early LLMs** worked only with completion prompts (no chat, no tools).
- **Few-shot prompting:** Showing multiple examples helps models find and continue a pattern.
- **Pattern alignment:** Models follow the most statistically salient pattern—prompt engineering often means making the right pattern obvious and constraining the prompt.
- Many prompt engineering best practices have been “baked into” newer models via instruction tuning.
- **“Give the LLM room to think”**: Adding space for step-by-step reasoning (“Let’s think step by step”) helps models generate more accurate responses.
### **LLM Evolution & Capabilities:**
- Progressed from simple completion engines to instruction-following models and now to tool-using, agentic systems.
- LLMs don’t “think” like humans; they predict one token at a time based on prior context, without internal simulation or world models.
### **RAG (Retrieval-Augmented Generation):**
- **Two main parts:** Retrieval (search engine, lexical/semantic) and generation (LLM).
- **Lexical search:** Matches on exact words; good for jargon, specific lookups (product IDs, phrases).
- **Semantic search:** Embedding-based; good for matching meaning, synonyms, related concepts.
- **Neither alone is perfect:** They complement each other, but current data structures don’t integrate both perfectly.
- **Debugging RAG:** Treat retrieval and generation as separate, debuggable components (not one black box).
### **Agentic AI:**
- **Conversational agents:** Loop between user prompt, LLM response, and tool use.
- **Workflow agents:** Predefined task chains (developer-imposed structure).
- **Tools/functions:** Modern LLMs can call external functions via JSON schema; descriptive, intuitive function names and parameters help the LLM choose correctly.
- **Agent design:** System messages define agent role; tool descriptions are critical; loop structure is simple but powerful.
### **Practical Prompt Engineering Tips:**
- Treat LLMs as “dumb mechanical friends” that have read the internet but need familiar patterns (e.g., markdown, HTML, legal/finance formats).
- Don’t overwhelm with excessive context—models have limited attention.
- If a prompt is confusing to a human, it will confuse the LLM.
- Give the model room to “think,” i.e., allow for intermediate reasoning before the final answer.
### **Evaluation & Testing:**
- **Automated (algorithmic) evaluation:** Possible when outputs are clear-cut (e.g., data extraction).
- **Subjective/human evaluation:** Needed for response quality, hallucinations, and “better/worse” judgments.
- **Meta-evaluation:** Using LLMs to evaluate other LLMs (“LLM-as-judge”) is becoming common, but is itself a complex challenge.
- **Testing like software:** Use test sets, aggregate pass rates, and monitor performance over time.
### **Fine-Tuning:**
- **Use rarely:** Powerful, but costly and complex—mainly for output structure, smaller models, or cost savings.
- **Risks:** Catastrophic forgetting, significant work required for each base model change.
- **Best for:** Cases where prompt engineering and RAG are insufficient.
### **Trends & Predictions:**
- **Rapid progress:** LLMs' ability to perform unguided work is increasing exponentially.
- **Workflows:** Break complex tasks into small, pluggable, testable steps; easier to isolate and fix issues.
### **UX/UI for AI:**
- **Transparency helps users:** Show users what the model “sees” and “thinks” to align mental models and improve experience.
---
## **Discussion/Community Section:**
- **Breakout tracks:** Book clubs, collaborative projects, and hackathons (e.g., on Model Content Protocol, schemas in AI).
- **Open forum:** Questions on topics like reproducibility in LLMs, incremental/iterative training, machine learning on iOS, and topic modeling.
- **Reproducibility:** LLM outputs can be noisy and not perfectly deterministic even with fixed seeds/temperature zero, due to hardware/GPU nondeterminism and stochasticity in embeddings.
- **Academic use:** Quantify uncertainty, embrace noise as a feature, not a bug; reproducibility is nuanced.
---
## **Selected Practical Takeaways:**
- **Prompt engineering is evolving:** Many tricks are now built into models, but knowing how and why to use them is still valuable.
- **RAG is not a monolith:** Treat retrieval and generation as distinct for debugging and improvement.
- **Agentic design:** Well-described tools/functions make for better agent behavior.
- **Evaluation remains a major challenge:** Meta-evaluation with LLMs is promising but imperfect.
- **Be pragmatic:** Don’t overuse fine-tuning; prefer prompt engineering and RAG when possible.
- **Community matters:** Sharing, collaboration, and continuous learning are emphasized.
---
## **Closing Note:**
The session was highly interactive, blending technical depth with practical wisdom, and encouraged ongoing community engagement and knowledge sharing.
