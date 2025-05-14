
Overview:
Justin's talk explores the practical challenges and patterns involved in building AI-first applications, which are defined by nondeterministic primary input (e.g., natural language, images). He contrasts this with typical “AI features” bolted onto traditional apps, advocating instead for rethinking entire experiences around AI capabilities.

Part 1: The Problem Space
Current AI narratives are polarized: either “world-ending” or “just a better code autocomplete.” In reality, there are few best practices and even fewer practitioners building serious AI-native products.

StackOverflow 2024 survey: Most developers believe AI won’t replace them, but Justin provocatively suggests: “Yes, it will replace you. Use it anyway.”

AI-first apps invert normal software design — inputs are “fuzzy” (text, images, etc.), not buttons or forms.

Part 2: What Makes AI Development Hard
No standard architecture: No consensus on UI, workflows, or app structure.

No intuition: Devs lack experience in what prompt structures or formats yield good results.

Poor tooling:

Few reliable validators or debuggers.

Chaining LLMs, managing context, multiplexing outputs all require DIY scaffolding.

Models are either “stupid or stupid expensive”:

Cheap models fail accuracy.

Expensive ones (e.g., GPT-4-turbo) cost real money, limiting commercial viability.

Accuracy vs. cost tradeoff is steep and unpredictable.

Part 3: Practical Strategies & Patterns
A. System Architecture
Routing layer: Decides complexity and chooses appropriate model (cheap, medium, expensive).

Tools: Expose deterministic functions to the LLM via structured tool descriptions (e.g., pourBeer).

Agent loop: Output becomes input until task completes. The trick is knowing when to stop the loop.

B. Key Techniques
Streaming: Always use token streaming for UX and faster tool invocation.

Multiplexing: Allows parallel LLM responses over a single user connection.

Lie to the LLM: Inject fake tool calls or responses to correct behavior (e.g., faking a timestamp or emoji preference).

Prompt hygiene:

Keep dynamic data out of system prompts for cacheability.

Don’t inject logic into user prompts — use structured tool calls instead.

Part 4: Case Study – AI Personal Fitness Coach
Justin demoed an AI-powered fitness coach:

Users interact via SMS and a web interface.

LLMs personalize workouts based on user data and preferences.

Implements context persistence, error handling, and model fallback trees (e.g., fall back from Gemini Flash to GPT-4 mini).

Uses Cloudflare stack (Workers, D1, R2, Durable Objects) for scalable infra.

Part 5: Community Wrap-Up
Following the talk:

Discussions ranged from AI use in construction, to organizational AI metrics, and AI music generation.

Several community pitches included:

Building Stable Diffusion from scratch.

AI-generated cybersecurity reenactments.

Book club on AI Engineering.

An exploration of DORA metrics showing AI tools increase perceived productivity, but may reduce production quality.

Core Takeaways:
AI-first apps are feasible today, not a future dream.

You must rethink product design around fuzziness and non-determinism.

Success depends more on architecture and intuition than raw model quality.

There’s enormous opportunity, especially in domains like healthcare, education, legal, and fitness — but execution is everything.
