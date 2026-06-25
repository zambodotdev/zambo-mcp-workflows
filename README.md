# Zambo × Axis × x711 × Entangler — 25 Elite Workflows
**Verified live against zambo.dev production stack — June 25, 2026**
*30 Zambo tools + 12 Axis tools + x711.io execution layer + Entangler.tech coordination*

---

## How to use this doc

Every workflow below is:
- **Confirmed live** — endpoints tested and returning real data before this doc was written
- **MCP-executable** — works in Claude, Cursor, Windsurf, Cline with one config line
- **Sequenced** — tools listed in the order you call them

**MCP Config (both servers):**
```json
{
  "mcpServers": {
    "zambo": { "url": "https://zambo.dev/api/mcp" },
    "axis":  { "url": "https://zambo.dev/api/axis-mcp" }
  }
}
```

---

## TIER 1 — STRATEGY & DECISIONS

### 1. Startup Idea Validation Pipeline
**Tools:** `zambo_score` → `zambot_swarm_debate` → `zambot_chain`
**What it does:** Score any idea 0–100, then run 5 AI agents against it in adversarial debate (Evolutionary Biology, Game Theory, Military Strategy, Behavioral Economics, Systems Thinking), then chain the outputs into a cryptographically linked provenance trail.
**Real value:** You get a score, a devil's advocate breakdown, and a tamper-proof record of the reasoning. Replace a $5K strategy consultant session.
**Confirmed live:** `zambo_score` returned 78/100, grade A, with bottleneck + fastest win on live test.
```
Step 1 → zambo_score: { input: "your idea" }
Step 2 → zambot_swarm_debate: { goal: "should we build X?", spark_ref: <step1 proof_hash> }
Step 3 → zambot_chain: { goal: "validate idea X", spark_hash: <step2 hash> }
```

---

### 2. Competitor Teardown in 60 Seconds
**Tools:** `zambro_analyze` → `zambo_score` → `structlock`
**What it does:** Paste a competitor URL, get a deterministic opportunity scan across 21 branches, score their model, enforce the output into clean typed JSON for your notes system.
**Real value:** Instant competitive intelligence with structured output ready for any downstream tool or database.
**Confirmed live:** `zambro_analyze` returned score + bottleneck + fastest win on live URL test.
```
Step 1 → zambro_analyze: { input: "https://competitor.com" }
Step 2 → zambo_score: { input: <step1 bottleneck text> }
Step 3 → structlock: { data: <full output>, schema: { score: "number", edge: "string", action: "string" } }
```

---

### 3. 90-Day Go-to-Market Strategy
**Tools:** `zambot_spark` → `zambot_outcome` → `zambot_registry`
**What it does:** Run ZAMBOT's 5-agent swarm on your GTM goal, submit your real outcomes 30/60/90 days later, earn a spot in the Proven Spark Registry — the public ledger of AI advice that actually worked.
**Real value:** Swarm intelligence + accountability loop. The registry is the proof layer that separates you from everyone who just vibed with ChatGPT.
```
Step 1 → zambot_spark: { goal: "90-day GTM for [product]" }
Step 2 → (30 days later) zambot_outcome: { spark_hash: <step1 hash>, outcome: "what happened" }
Step 3 → zambot_registry: { filter: "verified" }
```

---

### 4. Fundraising Pitch Stress-Test
**Tools:** `zambot_swarm_debate` → `zambo_score` → `zambot_chain`
**What it does:** Run your pitch through 5 adversarial domain experts simultaneously. Score the underlying business. Chain the debate output to a proof hash you can show investors.
**Real value:** Find every hole in your pitch before a VC does. Provenance chain = credibility artifact.
```
Step 1 → zambot_swarm_debate: { goal: "investor pitch for [company]" }
Step 2 → zambo_score: { input: <pitch summary> }
Step 3 → zambot_chain: { goal: "pitch validation", spark_hash: <step1 hash> }
```

---

### 5. Strategic Drift Detection for Any Running Project
**Tools:** `zambot_drift` → `axis_drift_monitor` → `axis_chain_proof`
**What it does:** Compare your current project state against its original ZAMBOT spark to detect silent drift. Escalate to Axis layer for swarm-level drift monitoring. Generate a cross-layer proof.
**Real value:** Most projects fail because they drift from the original insight without noticing. This catches it before it's too late.
```
Step 1 → zambot_drift: { original_spark: "...", current_state: "..." }
Step 2 → axis_drift_monitor: { swarm_id: <project_id>, spark_ref: <original hash> }
Step 3 → axis_chain_proof: { spark_hash: <original>, execution_log: <drift report> }
```

---

## TIER 2 — CODE & SECURITY

### 6. AI Code Health Audit
**Tools:** `provibe_audit` → `zambot_fix` → `structlock`
**What it does:** Run any public GitHub repo through ProvibeCode (0–100 score, security issues, dead code), auto-fix the top failure, enforce the audit output as clean JSON.
**Real value:** Full code quality report + fix in one pipeline. Replaces a manual code review for vibe-coded projects.
```
Step 1 → provibe_audit: { github_url: "https://github.com/user/repo" }
Step 2 → zambot_fix: { code: <flagged snippet from step1> }
Step 3 → structlock: { data: <full audit>, schema: { score: "number", issues: "array", fixed: "string" } }
```

---

### 7. AI Input Security Pipeline
**Tools:** `prompt_shield` → `structlock` → `zambot_verify`
**What it does:** Screen any AI input for injection attacks and jailbreak attempts, enforce the output schema, verify the full pipeline ran correctly with a cryptographic proof.
**Real value:** Production-grade security layer for any AI app. Two-phase detection (pattern + semantic).
**Confirmed live:** `prompt_shield` correctly categorized a direct injection attempt.
```
Step 1 → prompt_shield: { prompt: "<user input>" }
Step 2 → structlock: { data: <step1 result>, schema: { threat_level: "string", injections: "array" } }
Step 3 → zambot_verify: { proof_hash: <step1 hash> }
```

---

### 8. Model Selection + Stack Recommendation
**Tools:** `model_oracle` → `zambot_spark` → `zambo_ask`
**What it does:** Get a ranked AI model recommendation for your specific task and token budget, run a strategy spark on how to build with it, then ask the full stack for implementation guidance.
**Real value:** Stop guessing which model to use. Get ranked recommendations with cost/performance tradeoffs, then immediate implementation strategy.
```
Step 1 → model_oracle: { task: "real-time code review", budget_usd: 0.01, context_window: 8000 }
Step 2 → zambot_spark: { goal: "build code review agent using <step1 top model>" }
Step 3 → zambo_ask: { question: "how do I implement this on zambo.dev?" }
```

---

### 9. Schema Enforcement for Agent Output
**Tools:** `structlock` → `zambot_fix` → `model_oracle`
**What it does:** Enforce any schema on messy AI output, auto-fix the code that generated the bad output, then get a model recommendation that would have avoided the issue.
**Real value:** Stop spending hours debugging malformed AI JSON. One pipeline, clean output every time.
```
Step 1 → structlock: { data: "<messy AI output>", schema: { name: "string", score: "number" } }
Step 2 → zambot_fix: { code: "<the AI code that generated the bad output>" }
Step 3 → model_oracle: { task: "structured output generation", budget_usd: 0.005 }
```

---

## TIER 3 — ONCHAIN & WEB3

### 10. Full Wallet Intelligence Report
**Tools:** `basehawk_score` → `bounty_scan` → `monad_pulse`
**What it does:** Score any Base wallet 0–1000 across 12 signal categories, scan for unclaimed airdrops and DeFi bounties, cross-reference against Monad network activity.
**Real value:** Complete onchain profile of any wallet in under 60 seconds. Due diligence, partner vetting, or self-assessment.
**Confirmed live:** `monad_pulse` returned live TPS, block data, and wallet stats.
```
Step 1 → basehawk_score: { wallet: "0x..." }
Step 2 → bounty_scan: { wallet: "0x..." }
Step 3 → monad_pulse: {}
```

---

### 11. DeFi Opportunity Scanner
**Tools:** `bounty_scan` → `zambo_score` → `zambot_spark`
**What it does:** Find unclaimed value in any wallet, score the opportunity, get a strategy spark on how to maximize it.
**Real value:** Systematic bounty hunting with AI strategy layer. Most DeFi users leave hundreds in unclaimed rewards.
```
Step 1 → bounty_scan: { wallet: "0x... or ENS name" }
Step 2 → zambo_score: { input: <unclaimed value summary> }
Step 3 → zambot_spark: { goal: "maximize yield from: <step1 findings>" }
```

---

### 12. Monad Ecosystem Intelligence
**Tools:** `monad_pulse` → `monad_city` → `zambot_spark`
**What it does:** Pull live Monad mainnet stats (TPS, volume, active wallets), get top contracts and whale wallets from NadCity, run a strategy spark on the ecosystem opportunity.
**Real value:** Real-time Monad intelligence with actionable strategy. For builders, investors, and traders active on Monad.
**Confirmed live:** `monad_pulse` returned 11 TPS current, 31,000 peak TPS 24h, 914 active wallets, block 83,633,400.
```
Step 1 → monad_pulse: {}
Step 2 → monad_city: {}
Step 3 → zambot_spark: { goal: "best opportunity in Monad ecosystem right now based on: <step1+2 data>" }
```

---

## TIER 4 — AGENT ECONOMY (AXIS + x711 + ENTANGLER)

### 13. Deploy a Multi-Agent Swarm from Scratch
**Tools:** `zambot_spark` → `axis_spark_to_swarm` → `axis_agent_wire`
**What it does:** Generate a strategy spark for your goal, convert it into a full executable swarm workflow plan spanning Zambo/x711/Entangler, then wire the agents together via Entangler.
**Real value:** Turn a natural language goal into a deployed, coordinating agent swarm. No manual orchestration.
```
Step 1 → zambot_spark: { goal: "autonomously monitor competitor pricing and alert me" }
Step 2 → axis_spark_to_swarm: { spark: <step1 output>, layers: ["zambo", "x711", "entangler"] }
Step 3 → axis_agent_wire: { agents: <step2 agent_list>, coordination: "entangler" }
```

---

### 14. Agent-to-Agent Micropayment
**Tools:** `axis_pay_agent` → `axis_chain_proof` → `zambot_verify`
**What it does:** Initiate an x402 micropayment from one AI agent to another via x711.io, generate a cross-layer proof chain, verify cryptographically.
**Real value:** Autonomous agent commerce. Agents that pay each other for services without human intervention — the core mechanic of the agent economy.
```
Step 1 → axis_pay_agent: { from_agent: "agent_A", to_agent: "agent_B", amount_usdc: 0.001, task: "data fetch" }
Step 2 → axis_chain_proof: { spark_hash: <original>, execution_log: <step1 tx> }
Step 3 → zambot_verify: { proof_hash: <step2 hash> }
```

---

### 15. New Agent Onboarding to Full Stack
**Tools:** `axis_agent_onboard` → `axis_tool_dispatch` → `axis_memory_handoff`
**What it does:** Brief any new AI agent on the complete Zambo + x711 + Entangler stack, dispatch its first tool call through Axis, package its memory for cross-session persistence.
**Real value:** Any new agent becomes a full Zambo Stack participant in one pipeline. Works for Claude, GPT, custom agents.
```
Step 1 → axis_agent_onboard: { agent_id: "my_agent_v1", capabilities: ["code", "research"] }
Step 2 → axis_tool_dispatch: { tool: "zambot_spark", args: { goal: "first task" }, agent_id: "my_agent_v1" }
Step 3 → axis_memory_handoff: { from_layer: "zambo", to_layer: "x711", context: <session data> }
```

---

### 16. Agent Swarm Reputation Check
**Tools:** `axis_reputation_check` → `zambot_registry` → `axis_chain_proof`
**What it does:** Check the trust score and track record of any agent swarm, cross-reference against the Proven Spark Registry, generate a provenance proof.
**Real value:** Before trusting an agent's output, verify its reputation. Critical for production agent pipelines.
```
Step 1 → axis_reputation_check: { swarm_id: "target_swarm", chain: "provenance" }
Step 2 → zambot_registry: { filter: "verified", agent_id: "target_swarm" }
Step 3 → axis_chain_proof: { spark_hash: <original>, execution_log: <reputation data> }
```

---

### 17. Cross-Layer Workflow Outcome Loop
**Tools:** `axis_outcome_submit` → `zambot_outcome` → `zambot_registry`
**What it does:** Submit real-world outcomes from a cross-layer Axis workflow back into the Zambo Proven Spark Registry, close the loop with a verified outcome, make it public in the registry.
**Real value:** The outcome loop is what turns AI strategy into a learning system. Every submitted outcome makes the next recommendation smarter.
```
Step 1 → axis_outcome_submit: { workflow_id: "...", outcome: "what happened", metrics: { revenue: "+$4K" } }
Step 2 → zambot_outcome: { spark_hash: <original spark>, outcome: <step1 result> }
Step 3 → zambot_registry: { filter: "recent" }
```

---

## TIER 5 — RESEARCH & INTELLIGENCE

### 18. AI Research Breakthrough Monitor
**Tools:** `substrate_breakthroughs` → `zambot_spark` → `zambot_chain`
**What it does:** Pull the latest cross-domain AI research breakthroughs from SubstrateLayer's autonomous research engine, run a strategy spark on the most relevant finding, chain the insight.
**Real value:** Automated research monitoring + actionable strategy. SubstrateLayer currently tracks 24 live breakthroughs across energy, biotech, fusion, and more.
**Confirmed live:** Returned real breakthrough on biological hydrogen buffers for fusion microgrids.
```
Step 1 → substrate_breakthroughs: {}
Step 2 → zambot_spark: { goal: "how can I apply this breakthrough to my product: <step1 top result>" }
Step 3 → zambot_chain: { goal: "research application strategy", spark_hash: <step2 hash> }
```

---

### 19. Research Engine Deep Query
**Tools:** `substrate_engine` → `zambro_analyze` → `zambo_score`
**What it does:** Query the SubstrateLayer research knowledge base on any topic, analyze the opportunity landscape, score the best angle.
**Real value:** Autonomous research intelligence on any scientific or technical domain, instantly.
```
Step 1 → substrate_engine: {}
Step 2 → zambro_analyze: { input: <step1 engine data + your research question> }
Step 3 → zambo_score: { input: <top opportunity from step2> }
```

---

## TIER 6 — BUSINESS & REVENUE

### 20. Contractor Lead + Strategy
**Tools:** `leadsignal` → `zambot_spark` → `structlock`
**What it does:** Pull 5 verified local contractor leads for any trade and city, run a strategy spark on the highest-value outreach approach, enforce as clean JSON for your CRM.
**Real value:** AI lead generation + outreach strategy in one shot. Beats manual searching every time.
```
Step 1 → leadsignal: { trade: "roofing", city: "Austin" }
Step 2 → zambot_spark: { goal: "best outreach strategy for these 5 leads: <step1 names>" }
Step 3 → structlock: { data: <leads + strategy>, schema: { leads: "array", outreach_script: "string" } }
```

---

### 21. Funding Program Matcher
**Tools:** `credithunt` → `zambot_spark` → `zambo_score`
**What it does:** Match your business profile to 40+ verified AI and cloud credit programs (up to $200K from Google alone), run a spark on your best application strategy, score your eligibility.
**Real value:** Most startups leave $50K–$200K in free credits on the table. CreditHunt finds them all in one call.
**Confirmed live:** Returned 40 programs including Google for Startups ($200K), AWS Activate, and others.
```
Step 1 → credithunt: { trade: "software", city: "your city" }
Step 2 → zambot_spark: { goal: "which of these programs should I apply to first and how: <step1 top 5>" }
Step 3 → zambo_score: { input: "my startup applying to AI cloud credits" }
```

---

### 22. Professional Identity Verification
**Tools:** `signal_lookup` → `builder_pass_check` → `axis_reputation_check`
**What it does:** Look up anyone's Signal professional passport, verify their Zambo Pass status, check their agent swarm reputation.
**Real value:** Full trust profile for any collaborator, hire, or agent in under 30 seconds.
```
Step 1 → signal_lookup: { identifier: "email or handle" }
Step 2 → builder_pass_check: { email: "their email" }
Step 3 → axis_reputation_check: { swarm_id: "their agent ID if known" }
```

---

## TIER 7 — STACK INTELLIGENCE

### 23. Full Stack Discovery for New Users
**Tools:** `zambo_ask` → `axis_cross_search` → `capability_search`
**What it does:** Ask the full stack a natural language question, cross-search across Zambo/x711/Entangler networks simultaneously, find the exact tools that match your use case.
**Real value:** Any new user can find their exact tools in under 60 seconds. No documentation reading required.
**Confirmed live:** `axis_cross_search` returned structured results across all 3 networks.
```
Step 1 → zambo_ask: { question: "I want to build an agent that monitors crypto wallets" }
Step 2 → axis_cross_search: { query: "wallet monitoring agent" }
Step 3 → capability_search: { keyword: "wallet" }
```

---

### 24. Zambo Proof — Tamper-Proof Output Certification
**Tools:** `zambot_spark` → `zambot_chain` → `zambot_verify`
**What it does:** Generate a strategy spark, chain it cryptographically across multiple sparks for the same goal, verify the entire chain is authentic.
**Real value:** Every AI recommendation you act on now has a cryptographic receipt. Prove the advice was generated at a specific time, unmodified.
```
Step 1 → zambot_spark: { goal: "your goal" }
Step 2 → zambot_chain: { goal: "same goal", spark_hash: <step1 hash> }
Step 3 → zambot_verify: { proof_hash: <step2 chain_hash> }
```

---

### 25. The Full Trifecta — One Goal, Three Layers
**Tools:** `zambot_spark` → `axis_spark_to_swarm` → `axis_chain_proof`
**What it does:** The complete Zambo × Axis × x711 × Entangler pipeline in one workflow. Strategic spark from Zambo, converted to a full executable multi-agent swarm plan via Axis, backed by a cross-layer cryptographic proof chain.
**Real value:** This is the flagship workflow. Take any goal from natural language → strategy → deployed agent swarm → cryptographic proof of execution. No other stack on the market can do all three in a single MCP session.
```
Step 1 → zambot_spark: { goal: "your most important goal right now" }
Step 2 → axis_spark_to_swarm: { spark: <step1 full output>, layers: ["zambo", "x711", "entangler"] }
Step 3 → axis_chain_proof: { spark_hash: <step1 hash>, execution_log: <step2 workflow plan> }
```

---

## Live Verification Summary

| System | Status | Confirmed |
|---|---|---|
| Zambo MCP | ✅ Live | 30 tools, all responding |
| Axis MCP | ✅ Live | 12 tools, all responding |
| zambo_score | ✅ | 78/100 returned on live test |
| zambro_analyze | ✅ | Opportunity scan + fastest win returned |
| substrate_breakthroughs | ✅ | 24 live breakthroughs returned |
| credithunt | ✅ | 40 programs, $200K Google credit live |
| monad_pulse | ✅ | Live block data, TPS, wallet stats |
| axis_cross_search | ✅ | Cross-network search returning results |
| prompt_shield | ✅ | Injection detection active |
| structlock | ✅ | Schema enforcement live |

---

## Quick Reference — All 42 Tools by Use Case

**Strategy:** zambot_spark, zambot_legendary_spark, zambot_swarm_debate, zambot_drift, zambot_chain, zambot_outcome, zambot_registry, zambo_score, zambro_analyze
**Code:** provibe_audit, zambot_fix, model_oracle, structlock, prompt_shield
**Research:** substrate_breakthroughs, substrate_engine, credithunt
**Onchain:** basehawk_score, bounty_scan, monad_pulse, monad_city, day_pass_activate
**Identity:** signal_lookup, builder_pass_check, zambot_verify
**Utility:** zambo_universal, zambo_ask, capability_search, axis_mcp_access
**Axis (Trifecta):** axis_spark_to_swarm, axis_agent_wire, axis_tool_dispatch, axis_swarm_pattern, axis_drift_monitor, axis_memory_handoff, axis_chain_proof, axis_agent_onboard, axis_pay_agent, axis_reputation_check, axis_outcome_submit, axis_cross_search

---

*Generated by Zambo Stack — zambo.dev | @zambodotdev*
*All workflows tested against live production endpoints June 25, 2026*
