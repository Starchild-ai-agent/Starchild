# Changelog

## 3.1.8

- Faster tool workflows: supported read-only commands now run alongside other tools instead of waiting in line
- Cheaper long conversations: fixed a cache miss on the first call after a new message, cutting the hidden cost of long sessions

## 3.1.7

- Added cross-thread awareness: the agent sees scheduled jobs and active runs across conversations, uses real sidebar titles, and sends clearer task handoffs
- Improved tool recovery: repeated tool errors trigger a change of approach or escalation, while leaner guidance reduces unnecessary tool calls
- Fixed scheduled-task templates to allow longer execution and show readable failure messages instead of raw tracebacks, without automatically retrying potentially completed work

## 3.1.6

- Cleaned up the system prompt by removing redundant guidance, keeping the instruction layer lean without losing any behavior
- Refreshed skill docs: fixed broken links and aligned project-builder routing and Upbit setup guidance with current contracts
- Fixed internal AI calls to carry a consistent Starchild prompt prefix, so cost and behavior attribution across providers is fully auditable

## 3.1.5

- Improved context reuse on long, tool-heavy tasks: more cached context is reused while full tool results remain retrievable after trimming; summary defaults now use a faster, lower-cost model
- Fixed visual QA to use an updated fallback model with clearer guidance, reducing false alarms about normal spacing and margins

## 3.1.4

- Added milestone-aware context cleanup: intermediate tool clutter is cleared as a task milestone finishes so next steps start fresh, while oversized command outputs are archived to disk for instant drill-down
- Made project memory actionable: saved blockers, decisions, and tasks now track active versus resolved status, so the agent can accurately query open issues without misreading old notes
- Fixed thread notifications for cross-session messages, and silent background tasks now stay quiet instead of triggering false alerts
- New model supported: DeepSeek V4.1 Flash, the multimodal successor to V4 Flash with image input, suited for coding, terminal, computer-use agents, and long-horizon tasks

## 3.1.3

- Updated Conductor: Muse Spark 1.3 now powers the escalation lane for complex recovery attempts, with higher benchmark accuracy at lower token cost
- Smoother long tasks: memory search runs on less RAM, and smarter context cleanup prevents mid-loop slowdowns while preserving tool result pointers
- Fixed reply-language consistency after search and file reads, and cleaned up scheduled-task notifications to remove raw JSON wrappers

## 3.1.2

- Unified the image workflow: one upgraded image skill now handles generation, editing, background removal, inspection, and recoverable jobs while preserving existing user edits
- Upgraded web search with freshness filters, news search, publication dates, and clearer result context
- Enriched personal context: connectors now track recent Twitter, Calendar, Linear, Gmail, and Outlook activity with built-in noise filtering

## 3.1.1

- Added connector context: recent GitHub and Vercel activity now counts as evidence for profile synthesis, so a long-open machine whose only activity happens in connected apps stays up to date
- Lowered background costs: summaries and profile updates use more efficient models, with less unnecessary reasoning and fewer truncated summaries
- Fixed missing-command errors to provide actionable recovery guidance, and compaction now respects custom token budgets

## 3.1.0

- Condensed Conductor rules to reduce prompt overhead while preserving model strategy
- Improved task context reliability: compaction preserves the user's latest request, and stale or unsupported task history no longer resurfaces as current work
- Fixed skill installation to report failed results with actionable failure details

## 3.0.9

- Improved task state reliability: evidence-backed status updates and atomic summaries prevent false completions, accidental task renames, and stale progress after session clears
- Fixed session tool errors to provide clear recovery guidance instead of bare failures; skill operations are now serialized to prevent concurrent corruption

## 3.0.8

- Updated the delegation model: background tasks now use the latest Flash model fallback chain while preserving explicit model overrides
- Improved task completion and self-learning: failed delegations recover with their evidence intact, memory updates retry safely, and verified outcomes feed future improvements
- New model supported: GPT-6 Astra, combining adjustable reasoning depth, long-context understanding, and advanced tool use for complex coding, deep research, and multi-step workflows

## 3.0.7

- Updated Conductor rules: Gemini 3.8 Flash now handles hard reasoning and strong-tier tasks
- Improved task state reliability with cross-thread completions, time-aware profile synthesis, and task-plan validation to reduce stale or inaccurate progress
- Fixed background execution: failed jobs no longer trigger extra agent turns or recursive work, and raw failure logs are redacted before reaching chat history

## 3.0.6

- Made thread summaries reliable: thread titles, context, and open tasks now stay current instead of silently failing when summaries are truncated
- Fixed invalid or retired models to automatically fall back to the next available model instead of stopping the task; the migration bonus is no longer claimed by Starchild itself
- New models supported: Google Gemini 3.8 Flash (roughly six points higher on long-horizon SWE benchmarks at the same price) and Meta Muse Spark 1.3 (flagship agentic model built for multi-agent workflows and complex coding)

## 3.0.5

- Improved memory: every saved topic fact now records its source and originating conversation, enabling safer audits, corrections, and source-specific forgetting
- Fixed guests being able to publish the preview service to public

## 3.0.4

- Improved memory continuity: profile context stays fresher during active conversations and carries more reliably across sessions; truncated memory updates are now detected instead of silently disappearing
- Fixed background tasks to remain responsive with large logs, stream updates efficiently, and deliver reliable completion notifications without blocking the agent

## 3.0.3

- Added verifiable tasks: plans can verify completion through concrete checks instead of relying solely on the agent's self-report
- Improved the MCP OAuth workflow: the agent guides setup, accepts the callback URL, and reloads the connection automatically with no manual commands required
- Fixed verified failures to feed back into future improvements, and large memory updates are now preserved and safely compacted in the background

## 3.0.2

- Improved task delivery reliability: every completed plan now receives a one-time evidence audit before the final response, with claimed workspace artifacts checked automatically while text-only deliverables remain lightweight
- Fixed re-verification so changed plans are re-checked but completed work is not repeatedly audited; optimized error display

## 3.0.1

- Updated Conductor rules (v3.3): everyday conversations and multi-step tasks now default to GLM-5.3 Flash, delivering higher accuracy and faster responses as Luna's recent performance has declined
- Improved task completion reliability: interrupted work resumes from richer checkpoints, delivery requirements survive compaction, open plans are verified before completion, and repetitive output loops stop before wasting another generation round

## 3.0.0

- Added persistent task plans: complex tasks can now be saved, resumed, and completed across background sessions, with deduplication, recovery, and completion receipts to prevent lost or repeated notifications
- Improved Conductor routing to preserve session context and adapt to previous model and tier choices
- Fixed unavailable tools being advertised, and rollout status now reflects the actual success rate
- New model supported: Tencent Hy4 preview

## 2.9.9

- Improved connector guidance: connected apps now provide clearer capability guidance, and the agent uses existing Composio authorizations first
- Fixed memory writes being dropped by near-duplicate checks; overlapping entries can now be consolidated safely in the background. Fixed delegation guidance when the tool is not available

## 2.9.8

- Updated Conductor Mode (v3.2): a four-tier routing ladder with a dedicated mid tier for routine multi-step work, Gemini 3.7 Flash for hard reasoning, and Grok 4.6 as a recovery-only escalation lane
- Added visual QA before delivery: the agent can inspect rendered pages, charts, slides, and documents, returning structured blocking findings through a benchmarked vision-model fallback chain
- Fixed Telegram-linked threads to receive task-completion notifications directly, and memory tools no longer silently drop updates caused by re-encoded locators or malformed batch inputs

## 2.9.7

- Fixed MCP OAuth 2.1 setup: authentication now returns to the correct frontend callback instead of ending on a 404, with CIMD support for metadata-based client identification
- Added tg as a compatible alias for Telegram, and clearly separated internal runtime guidance from user messages so the agent answers the actual request instead of acknowledging system instructions
- Retired model IDs are redirected to supported successors, while invalid selections fall back safely instead of causing spawned tasks to fail

## 2.9.6

- Added execution-first assistance: the agent now acts on corrections and requested next steps in the same turn, repairing the actual result instead of only acknowledging the issue
- Made scheduled automation safer: tasks are test-run and verified before activation, with upfront cost estimates for recurring jobs

## 2.9.5

- Updated Conductor Mode: introduced GLM 5.3 as the escalation model, with upgraded task classification on an optimized 4-tier hierarchy (Cheap, Normal, Strong, Escalation) so straightforward tasks resolve instantly while complex reasoning routes to dedicated heavy-reasoning engines
- Clarified budget controls: advisor usage is now governed by cost-based budgets instead of a fixed session call count, and blocked advisor calls include clear guidance for adjusting the configuration
- New model supported: DeepSeek V4 Flash Vision Exp, with the same text capabilities as V4 Flash 0731 plus multimodal (image) input

## 2.9.4

- Added opt-in skill write notifications: web notifications now appear when skill_manage creates, edits, patches, deletes, or updates a skill; disabled by default and configurable through the agent
- Made thinking concise by default: the agent focuses on the current question and avoids repetitive restatements and recaps, while preserving verification, tool use, and safety checks

## 2.9.3

- Added a Conductor thinking effort floor: expanded the effort ladder and added benchmarked floors for selected models while preserving explicit user controls
- Clarified MCP and skill guidance with a reference covering all three MCP channels; the system now distinguishes callable tools from script-based workflows and reports actual registration results instead of promising unavailable tools

## 2.9.2

- Updated Conductor Mode: Gemini 3.7 Flash now handles escalation and media tasks at lower cost with high performance; thinking effort adapts to task complexity, and "think harder" still forces maximum depth
- Improved streamed reasoning clarity: consecutive thinking rounds are now separated during tool-heavy turns
- Fixed memory placement: source, scope, and time scale are used to keep preferences, rules, and project facts in the right place

## 2.9.1

- Upgraded read_file capabilities: extract common document formats, detect scanned PDFs, safely handle large files, and page through long documents
- Fixed skill updates to be safer and evidence-based, cleaned up user-profile memory, and improved failure handling clarity

## 2.9.0

- Fixed the compaction boundary: context compaction now waits for a safe turn boundary, preserving prompt-cache reuse during tool-heavy work while retaining emergency overflow protection
- Added skill tool recovery: when a tool belongs to an installed but unloaded skill, the agent identifies the correct skill and loads newly installed or updated capabilities automatically

## 2.8.9

- Added a machine memory guard: the system monitors host memory headroom to protect the main chat from container crashes and abrupt restarts; heavy background workloads like Web Previews are admitted safely and paused gracefully under memory pressure
- Made skill updates safer: pinned and locally customized skills are protected from automatic overwrites, with explicit pin/unpin controls
- Updated delegation and advisor: oversized delegations are redirected toward chunked parallel execution, and routine consultations use a cheaper model (Gemini 3.7)

## 2.8.8

- Added smarter escalation: before concluding a task is impossible, the agent checks for an existing capability first and asks for help, reducing false "can't be done" refusals
- Cleaned up memory: implementation trivia no longer displaces behavioral rules in long-term memory and is routed to the topic store instead; facts that prove durable are promoted from topics into memory automatically
- Improved the self-learning loop: every skill carries a real success ledger, skills can accumulate scripts and reference assets, and agent-created skills that consistently fail are surfaced for repair

## 2.8.7

- Added /smart assist levels (internal test): /smart off, /smart on (default), /smart anchor, and /smart guard, independent from /model; anchor keeps the primary model focused on planning, reasoning, and judgment while delegating mechanical work to a cheaper executor, and guard keeps advisor support available as a quality floor for budget-tier models
- Improved context and cache stability through stale tool demotion, volatile-tail handling, zombie action replay prevention, and persisted hygiene across restarts
- Improved reliability: long-running delegations can move to the background without becoming orphaned, and session_status now applies stricter user and session ownership checks and reports stored tool outputs more accurately

## 2.8.6

- Added MCP OAuth 2.1 support: MCP connections can now securely authenticate through OAuth 2.1, with authorization, token storage, reconnection, and user-isolated access control
- Optimized workflows: background tasks preserve partial results, cross-session messaging is protected from loops and excessive spending, action results survive restarts without replaying, and thread titles and file links render more reliably
- Fixed compaction: long sessions now compact less often and more intelligently, reducing prompt-cache misses and unnecessary cost while preserving conversation context and the latest task focus

## 2.8.5

- Added cross-session handoffs: agents can send summary context to another thread of the same user to steer live work, queue a follow-up, or wake an idle thread automatically; handoffs are user-isolated, fail-closed, never include full history or files, and remain visible in thread history with clear cross-message UI
- Improved context management: large-window models compact less frequently, keeping long sessions more stable and reducing summary drift

## 2.8.4

- Finalized Conductor v3: expanded the benchmark dataset to evaluate performance across thinking levels; Luna's x-high mode now serves as the primary model for complex tasks due to its outstanding results and competitive cost
- Improved the long task loop verifier with better compaction stability, preserved important file activity, and safer loop completion and verification

## 2.8.3

- Added /compact focus <topic> to preserve important topics through the next compaction
- Improved compaction to keep long conversations stable and reduce context drift on large-window models
- Improved completion reliability: background work is isolated from the main chat and verified against item-specific evidence before completion, with clearer updates and safe pauses when verification fails

## 2.8.2

- Updated Conductor Mode rules: clearer model routing, with DeepSeek V4 Flash for simple tasks and Kimi K3 for escalation, plus stronger fallbacks and classifier retry recovery
- Improved reliability for WebSocket connections, Telegram media delivery, and empty provider responses
- Fixed long-session stability with safer compaction and fewer compaction loops

## 2.8.1

- Unified planning management: long-term plans and task workflows now use a shared directory and index, keeping work organized and easier to track
- Improved task progress reliability: progress, budgets, pause/resume states, and completion status are preserved more consistently across long-running work and restarts
- Prevented zombie tasks: completed work remains finished after compaction, while long sessions prioritize the latest user message and stop safely instead of burning credits in repeated compaction loops

## 2.8.0

- Prevented disk-full stalls: reserved recovery space is released automatically, then reclaimed when storage recovers; cleanup never touches workspace files
- Improved long-session stability by preventing repeated context-compaction loops under heavy workloads
- Added a complete plan lifecycle with an open-plan index, durable knowledge saved to docs, and safe cleanup after completion
- Made failures clearer: interrupted tool calls and preview port exhaustion now explain what happened and how to recover

## 2.7.9

- Improved reasoning recovery: models that exhaust their token budget on thinking now retry with a reduced reasoning budget before safely disabling reasoning, preventing empty or incomplete replies
- Upgraded MCP support: server configurations persist across updates, reload automatically with .env changes, and load large toolsets on demand to reduce prompt size
- Fixed preview startup timeout handling with clearer errors and recovery guidance

## 2.7.8

- Updated the wallet skill: agents can now see user login and secondary wallet addresses
- Fixed empty replies on small token budgets and hanging streams after a circuit-break
- New model supported: DeepSeek V4 Flash 0731, re-post-trained for stronger coding, reasoning, and agent workflows

## 2.7.7

- Added user personal wallet actions: the agent can request secure message signing or transactions from the user's linked login or secondary wallet (EVM and Solana), with every request appearing in the user's own wallet for review and approval before anything executes
- Strengthened wallet reliability and safety with automatic wallet synchronization, background recovery, server-side validation, and protection against stale wallet bindings
- Fixed Preview wrongly blocking pages whose titles contain non-Latin characters

## 2.7.6

- Smarter capability discovery: agents now prioritize built-in tools and installed skills, then recommend installable skills or paid x402 services when needed; search is faster and better handles long or mixed-language queries
- Safer background tasks: large file writes, truncated tool calls, and repeated-action loops now receive safe, tool-specific recovery guidance instead of failing midway
- Fixed visible replies after heavy reasoning, clarified memory-search guidance, added safer web-search backoff during quota failures, and restored access to Topic tools

## 2.7.5

- Improved model recovery: harmless requests blocked by provider filters can retry with another model family and stay there until the task finishes
- Prevented truncated tool calls and incomplete file writes from silently succeeding or entering repeated retry loops
- Strengthened completion verification by defining required evidence upfront and using a different model provider to review the work
- Added live MCP tool updates so newly available server tools appear without reconnecting

## 2.7.4

- Improved conversation reliability: fixed duplicate or missing replies after reconnects, protected compacted summaries in long sessions, and made memory errors clear instead of failing silently
- Leaner tool system: low-frequency tools load full details on demand, reducing per-turn token cost while improving execution safety and cost attribution
- Strengthened /goal verification: independent verification now requires concrete evidence, filtering out vague, repeated, or unactionable objections
- New model supported: Qwen 3.7 Flash

## 2.7.3

- Reduced token usage on Claude Opus 5 conversations with the same quality at lower cost
- Fixed background restart issues so the agent no longer gets cut off mid-task

## 2.7.2

- Fixed prompt-cache boundaries being broken when Hooks or routing notices inject context, reducing unnecessary cache misses, latency, and cost
- Improved Smart Routing fallbacks so each model receives the correct model-specific guidance

## 2.7.1

- Added compaction safety with a two-tier trust boundary that preserves top-level user instructions while preventing nested tool, web, file, and quoted content from being promoted into persistent directives
- Improved tool reliability: reduced false dangerous-command blocks for quoted grep/sed patterns while preserving command-substitution detection; fixed GLM-style placeholders, session-search error categorization, and JSON parsing recovery guidance

## 2.7.0

- Upgraded long-term memory: conversations are captured more reliably, repeated or outdated facts are cleaned up automatically, and stored knowledge stays better organized and easier to recall
- Improved scheduled-task recovery: invalid schedules and environment issues now return clearer causes and actionable guidance
- Fixed npm/npx connectivity behind the platform proxy, improving skill installation reliability

## 2.6.9

- Reduced repeated prompt costs by stabilizing dynamic prompt blocks and improving cache reuse across turns
- Added automatic memory maintenance to detect stale, duplicate, or conflicting memories and safely rebuild memory indexes; memory reviews no longer trigger on background or benchmark sessions, and every compaction is fully auditable
- Delegated tasks can now checkpoint progress and continue in a fresh executor session when they approach time, cost, or iteration limits

## 2.6.8

- Added proactive project follow-ups (internal test): the agent can track ongoing work, notice stale projects, suggest a continuation at natural moments, and learn from user reactions without background polling or extra model calls
- Smarter delegation and verification: code subtasks can use task-aware model chains with configurable routing and more accurate cost limits; the agent recognizes when search or verification resources are unavailable, labels unverifiable claims, records verification results, and supports configurable verification strictness
- Fixed Codex conversations breaking on orphaned tool results, improved restored multimodal recall, and preserved background notifications for image-only messages

## 2.6.7

- Strengthened memory and session recovery, including automatic repair of corrupted memory indexes and protection against stale interrupted replies resurfacing
- Made long conversations more reliable with smarter context pruning that preserves active multi-tool workflows while reducing old tool-result overhead
- Fixed stale partial replies being restored into new conversations, standardized compaction summaries, and added clearer opt-in memory notifications
- New model supported: thinkingmachines/inkling

## 2.6.6

- Added smarter memory recall with semantic and keyword search, allowing saved memories and user preferences to be found through paraphrased queries
- Added clearer relevance levels and safer degraded-mode recovery, keeping memory search reliable when the vector index is temporarily unavailable

## 2.6.5

- Added new /cost command to identify credit usage across scheduled tasks, background services, and conversations
- Optimized background task setup: the agent now estimates daily and monthly costs before activation, helping prevent unexpected spend from high-frequency tasks
- Improved reasoning recovery for GLM and other models, preventing unfinished tasks when reasoning exhausts the output limit
- Improved background task model inheritance, file delivery, and preview error recovery
- New models supported: meta/muse-spark-1.1, moonshotai/kimi-k3 

## 2.6.4

- Added /smart: unifies Advisor and Delegate in one feature — Advisor brings in a stronger model when tasks get stuck, while Delegate sends routine subtasks to lower-cost models; ask the agent to customize models, budgets, and limits for you
- Improved context compression to keep long conversations coherent while preserving important memory and tool history; slimmer tool schemas also reduce baseline prompt size and per-turn cost
- Fixed web search and file-transfer errors to provide clearer recovery guidance, and background tasks now correctly honor the model selected for the session

## 2.6.3

- Improved machine stability after updates and restarts, reducing dependency-related authentication failures and crash loops
- Added clearer timeout and retry feedback when model providers are slow, with fewer unnecessary interruptions during tool calls
- Strengthened conversation continuity after context compaction, preventing completed, outdated, or cancelled tasks from being resumed unexpectedly

## 2.6.2

- Hardened skill installation with automatic npx cache recovery, timeout cleanup, and cross-process locking to prevent repeated installation failures
- Improved response reliability with stall-based upstream detection and visible retry notices when model providers stop responding; improved ChatGPT/Codex subscription reliability, restoring delegation for OAuth models and improving prompt caching and retry recovery
- Added automatic redirects for removed models, allowing sessions pinned to older models to continue with supported replacements
- Added new supported models: kwaipilot/kat-coder-air-v2.5 and kwaipilot/kat-coder-pro-v2.5

## 2.6.1

- Improved web fetch and OAuth timeout recovery with clearer, more accurate errors
- Improved long-task continuity by preserving active targets and filtering unrelated history after context compaction

## 2.6.0

- Fixed agent-managed language preference updates, adding compatibility with regional locale formats such as zh-CN and en-US
- Refined delegation to keep architecture-dependent work with the main agent, validate inputs before delegating, and provide better retry diagnostics

## 2.5.9

- Added automatic OAuth keep-fresh for connected ChatGPT/Codex and Grok subscriptions, with clearer provider-specific errors and notifications when new models become available
- Added Meta Model API BYOK support, including Muse Spark 1.1 and live model discovery
- Optimized delegation guidance to avoid unnecessary handoffs, reducing coordination overhead and cost for small tasks

## 2.5.8

- Improved Delegate reliability and cost control with stronger execution budgets, loop protection, compact action logs, and safer handling of large tool results
- Reduced large-context cost blowups by enforcing absolute compaction limits and capping oversized tool-result batches before they enter the main prompt
- Optimized the retry and error message guidance for OAuth models
- Fixed skill batch installation races and redundant reinstalls after timeouts, making skill setup faster and less disruptive to active chats

## 2.5.7

- Added /checkup (alias /audit) for agent health checks, helping find unused skills, hidden credit drains, stale commands, memory issues, hooks/MCP problems, and workspace junk before applying any fixes
- Improved Advisor Mode with better timing guidance, zero-parameter consults, structured usage metrics, and advisor support inside delegated executor sessions
- Added Grok 4.5 reasoning-effort support and refreshed subscription model priority lists

## 2.5.6

- Continued tool schema slimming: moved more low-frequency tools to on-demand loading, further reducing baseline prompt size and per-turn cost
- Upgraded delegation: executor turns are no longer capped by default, and existing default configs are automatically migrated so cost and timeout become the main execution budgets
- Fixed task reliability issues: response footer hooks no longer corrupt task JSON, and bash heredoc content is no longer mistaken as code edits for verification reminders
- Added the x402 skill (internal test) for building and using paid agent services

## 2.5.5

- Added Tool Search: 16 low-frequency platform tools are now discovered on demand instead of being loaded into every request, reducing fixed prompt cost while keeping these tools fully available; improved platform-tool routing
- Hardened skill updates to prevent unrelated third-party skills with the same name from overwriting installed official/versioned skills

## 2.5.4

- Improved prompt caching for OpenAI-compatible providers by keeping per-turn volatile context out of the stable prefix, reducing repeated input cost on long conversations
- Strengthened /goal: the agent now defines what "done" means before working, and completion is judged against concrete verification evidence instead of self-reported claims
- Fixed Smart Routing: stronger follow-up handling, and safer fallback behavior when classification fails

## 2.5.3

- Improved memory reliability during long conversations: important facts from compacted or pruned context are now flushed to memory before they are lost
- Added a verification safety gate: after code changes, the agent can prompt itself to run tests or checks before claiming work is complete

## 2.5.2

- Added proactive memory synthesis, helping the agent understand ongoing user work, recent activity, and useful next steps while keeping owner-specific context behind trusted agent profiles
- Improved memory updates with fuzzy matching and clearer recovery hints when a memory entry cannot be found exactly
- Improved prompt guidance for live market prices, background task delivery, skill loading, local shell usage, and user-facing file paths

## 2.5.1

- Added Claude Fable 5 back and adjusted its provider priority to use Anthropic first, preventing empty replies or unwanted provider fallback; removed the old Fable-to-Opus redirect
- Added clearer guidance when a model refuses a request for content-safety reasons (Fable 5 safety check)

## 2.5.0

- Improved bash failure recovery with clearer guidance when commands exit without any output
- Added large web page paging support so oversized fetch results can be saved locally and reviewed in smaller chunks

## 2.4.9

- Integrated X MCP with the new x-mcp skill, and added automatic MCP hot-reload so OAuth-backed MCP integrations reconnect after token refresh
- Added stronger follow-up reliability: when the agent promises to remind you or report back later, it now routes that promise into a scheduled task or background watcher instead of relying on memory
- Added Skill Curator to safely archive stale agent-created skills and keep the active skill set cleaner
- Fixed Smart Routing update banners for users on older default rules, so unchanged defaults update quietly instead of showing unnecessary alerts

## 2.4.8

- Updated Smart Routing (real final version): MiniMax M2.7 for simple tasks, GLM-5.2 for stronger multi-step work, and Gemini 3.1 Flash Lite for image/video inputs
- Improved skill discovery, added soft trust labels so official/local skills rank higher without blocking community skills
- Improved recovery for command timeouts and missing SOUL.md, with clearer error categories and next-step guidance

## 2.4.7

- Updated Smart Routing Optimization (final version): uses MiniMax for simple tasks and GLM-5.2 for stronger work, with Opus used as an advisor for the hardest cases instead of a default routing target; benchmark testing is still running, and the report will be released later
- Added batch memory updates so the agent can clean up and add memory in one step, reducing repeated memory-management loops
- Added clearer credit visibility warnings for long-running backend services that are not registered scheduled tasks

## 2.4.6

- Added Extra High and Max reasoning tiers for supported models, including GLM 5.2, newer GPT-5 models, and Claude 4.6+
- Improved agent reliability with clearer tool recovery for web fetch, preview, and file-edit failures, plus retries when models return only internal thinking during tool workflows

## 2.4.5

- Added MCP & ACP support, letting Starchild connect external tools and work with ACP-compatible coding clients or harnesses
- Improved long-running workflows with more accurate mid-loop compaction based on real input size
- Fixed scheduled tasks so cancelled or completed jobs no longer keep running in the background

## 2.4.4

- Fixed credential-input flows where guidance shown before the input prompt could be dropped from the final reply, making API key setup steps clearer
- Added startup protection against stale volume-installed Python packages shadowing image dependencies, reducing machine crash loops after deploys

## 2.4.3

- Upgraded Smart Routing with a three-tier model strategy, better task-structure rules, and stronger safeguards against off-rules model picks
- Improved /delegate so mechanical subtasks are used more effectively, partial executor work can be recovered, and executor actions are easier to review/debug
- Fixed secure input flows so the agent still gives helpful setup guidance while users complete credential popups (during Upbit skill)

## 2.4.2

- Optimized Smart Routing and /delegate to use cheaper models more effectively, with clearer onboarding and better executor logs for review/debugging
- Added new supported model: Fugu Ultra

## 2.4.1

- Updated Hook management: approve one hook script across all configured events with '/hooks approve', and fully uninstall active hooks with '/hooks clean'
- Added per-agent skill and tool profiles, letting agents run with scoped capabilities like hardened guest mode or market-readonly mode
- Fixed prompt overhead when an agent has limited skills

## 2.4.0

- Updated Smart Routing rules to use GLM 5.2 for complex tasks
- Added expanded Hook support, including on-user-message hooks, response-end hooks, and hook activity metadata
- Fixed Grok reasoning behavior with safer default effort settings
- Improved chat infrastructure with faster SSE proxy streaming, richer usage metadata, and stricter AKM agent binding

## 2.3.9

- Added Agent Lifecycle Hooks (/hooks) for custom guardrails — enable in Preferences or with '/hooks on', ask the agent to set up a hook, and approve it when prompted (internal test)
- Fixed delayed SSE streaming in preview/community proxies so streamed responses start much faster

## 2.3.8

- Leaner prompt: moved non-general built-in tools to on-demand skills, cutting always-loaded tool schemas for faster and cheaper replies
- Added custom tool scopes: define agents with their own tool sets, from lightweight core mode to full capability when needed
- Strengthened the local /chat interface so in-container scripts and scheduled tasks can choose the responding agent, pass more options, and use temporary sessions isolated from real chat history
- Added new model: GLM 5.2

## 2.3.7

- Optimized skill descriptions to make skill calls clearer and reduce prompt cost
- Added a new Telegram message format
- Fixed Hyperliquid skill import error

## 2.3.6

- Redirected unavailable or retired models to latest supported replacements (Fable 5 → Opus 4.8, grok3 → grok-4.3) and other previously removed model aliases
- Improved tool recovery guidance for pytest output and invalid edit_file workspace paths
- Added new model: Kimi K2.7 Code

## 2.3.5

- Updated interrupted-run recovery so agent progress can be preserved after unexpected restarts or redeploys
- Added low-memory protection for heavy install/build commands, reducing machine crashes and giving clearer cleanup guidance
- Strengthened memory quality rules so only verified, reusable facts are written to long-term memory
- Fixed expired full-auth subscription routing so ChatGPT/Codex and Grok models reconnect or fallback more clearly
- Added Model Assist executor to let the agent delegate focused work to cheaper models with cost caps and takeover guidance (internal test)
- Added advisor and executor frontend visibility
- Added oversized-image protection to avoid request failures from very large uploads
- Fixed compaction model selection in OAuth model
- Fixed Grok Build OAuth image support

## 2.3.4

- Added support for video-capable models (e.g. Gemini 3.5 Flash), allowing them to read uploaded video files directly
- Added video-analysis skill, enabling non-video models to understand videos through a video model, extracted frames, transcripts, or summaries
- Added Advisor rescue mode: enable /advisor to let a stronger model help recover when cheaper models get stuck
- Improved model routing and context-window handling, especially for newly added or removed models
- Made scheduled task failures easier to understand with concise, actionable error notifications instead of raw tracebacks
- Added hard prompt rules to prevent hallucinations when users reference specific content

## 2.3.3

- Improved model reliability for thinking-only/max_token retry loops, subscription model routing, and usage visibility
- Fixed Anthropic thinking-budget retry storms and set safer reasoning defaults
- Added safer advanced workflows with custom/local shell commands and stronger tool error handling
- Added /memory and /memory review commands for optimized memory quality, reducing duplicate and stale entries
- Made repeated user preferences easier for the agent to remember across sessions
- Added lightweight cross-thread awareness so the agent can understand what is happening in other conversations without replaying full history
- Refined scheduled task setup with clearer guidance and cleaner errors
- Strengthened date-sensitive reasoning for deadlines, schedules, and enrollment windows

## 2.3.2

- Added shell-backed custom slash commands that can run saved workspace commands directly in chat
- Improved command and background-process error messages so agents can recover more reliably
- Improved privacy for error reporting by redacting sensitive text before transmission
- Added prompt guidance to prevent agents from promising follow-up messages and from hallucinating
- Improved error categorization for capacity-related tool failures

## 2.3.1

- Added Thinking Effort controls for chat sessions, including /reasoning support for Off, Low, Medium, and High
- Improved Thinking Effort accuracy across smart routing, BYOK, ChatGPT/Codex, Grok, OpenAI, and other supported models
- Added clearer Thinking Effort visibility, including the actual effective setting per model for the agent
- Fixed failures from unsupported reasoning settings on Grok Build and other non-reasoning models
- Improved image chat reliability by storing uploaded images via cloud storage instead of large inline payloads
- Improved memory cleanup when memory is nearly full, preserving important user corrections more reliably
- Fixed preview startup failures when all preview ports are occupied, with clearer recovery guidance
- Improved bash and web fetch error handling for clearer failures and better recovery
- Added new model: qwen3.7-plus

## 2.3.0

- Added new models: Claude Opus 4.8, Kimi K2.6 (Free), DeepSeek V4 Flash (Free)
- Added usage tracking for ChatGPT and Grok subscription models, including plan information and available usage limits where supported
- Improved AgentX posting and commenting reliability with clearer retry guidance when models use the wrong parameters
- Improved Grok onboarding compatibility with fallback guidance when subscription login is unavailable, plus clearer guidance for finding OAuth models in the model list
- Fixed several tool error loops by adding recovery hints for failed scripts, skill calls, and malformed commands

## 2.2.9

- Improved reply stability by preventing pre-tool text and internal thinking blocks from being reused as final answers, with retries for empty visible responses
- Improved web fetch decoding for pages with mismatched or invalid charsets
- Added bash safety checks for dangerous commands, including hard blocks for system-level destructive operations and confirmation for workspace-destructive actions
- Added disk-pressure detection and proactive warnings when /data is close to full

## 2.2.8

- Reduced baseline prompt/tool-schema size by consolidating prompt guidance and moving certain flows into skills
- Added script-mode runtime bridge so skills can request secure input and refresh agent config without keeping large tools always loaded
- Lazy-hide Telegram/WeChat post-binding tools until the user has those integrations connected
- Added Starchild FAQ reference for billing, models, privacy, and common user questions

## 2.2.7

- Decoupled official skills into script calls instead of tool calls (except Wallet tool); all skills updated to latest version
- Added new models: Ring 2.6 1T (Free), Hunyuan HY3 Preview (free trial expired), Gemini 3.1 Flash Lite (replaces preview version)
- Updated Smart Routing rules: simple requests now use minimax/minimax-m2.7 (cheaper and faster), auto-falls back to qwen/qwen3.6-plus when message contains an image
- Added cost tracking for user proxy API usage
- Added image and video generation info tracking
- Fixed Smart Routing rule issues, background review issues, and machine auto-suspend issues

## 2.2.6

- Refactored and optimized the entire Prompt Cache architecture to increase cache hit ratio, especially on long-running conversations and premium models (Claude Opus)
- Optimized cache-control algorithm to maximize cache hit ratio, and use Google Vertex as the primary provider to reduce costs
- Fixed and optimized Memory loading and injection capabilities to ensure that Memory updates are perceived by the agent immediately
- Optimized Smart Routing rules to reduce model-capability mismatches caused by lower-tier models
- Compatibility fixes for output adaptation on a few models (Gemma)
- Cleaned up scattered files at the workspace root, consolidating everything under output/ to prevent root pollution
- Fixed duplicate workspace creation, making the directory structure clearer

## 2.2.5

- Added script-mode skill delivery to reduce preloaded tool schema and improve prompt-cache stability
- Enabled OpenRouter response cache by default
- Claude models defaults set to google-vertex provider for lower cost
- Fixed Smart Router misrouting and improved message classification
- Expanded telemetry on tool errors as a foundation for ongoing analysis and iteration
- Fixed tool-result issues that confused the model and reduced upstream risk-control friction; fix wrong error messages and guidance
- Support IPv6 IP configuration for Anthropic BYOK
- Add Smart Routing Rules API to alert users when new rules are updated
- Fix Custom Model and OAuth error prompts, optimizing error guidance to help users complete the configuration process
- Remove Laguna models due to privacy concerns
- Added OAuth sign-in for ChatGPT Codex models (internal test) — users can now hand their ChatGPT subscription to the Agent and let it use the models they already pay for
- Added one-key setup for Custom Models (BYOK) — top vendors (Anthropic, OpenAI, DeepSeek, Qwen, etc.) can now be configured directly with an API key

## 2.2.4

- Optimized incomplete or interrupted responses handling for budget models (Kimi, etc.) during long conversations
- Fixed cloud model cache hit rate degradation in long conversations
- Added new models: Qwen 3.6 Flash, Qwen 3.6 35B-A3B, and Qwen 3.6 Max Preview (replaces Qwen Turbo and Qwen 3.5 9B)

## 2.2.3

- Image Generation: Added custom save path support. Fixed model confusion between chat and image models.
- Session Search: Session search now works across all conversation threads.
- Custom Models: Optimized model config setting guidance — can directly paste vendor API example and the model auto-configures. Fixed Anthropic native connection issues in custom models.
- Custom Models: Added thinking mode support. Fixed DeepSeek V4 Pro custom model error.
- Added new models: DeepSeek V4 Pro, DeepSeek V4 Flash, and GPT-5.5
- Fixed compact summary cut-off issues
- Fixed empty responses on certain models
- Fixed lost replies during chained reconnects
- Fixed Text Response display when models return both Thinking and Text
- Added skill tools loading protection to prevent faulty skills from affecting other tools

## 2.2.2

- Fixed Composio cache refresh after connection
- Fixed wallet export when policy is enabled
- Added new models: Xiaomi MiMo v2.5 and MiMo v2.5 Pro (replaces MiMo v2)

## 2.2.1

- Hardened memory review — high-value entries are now protected from accidental deletion
- Fixed parameter leaking between sub-tools, Composio connection cache, and duplicate user ID in community publish URLs
- Added new model: ling-2.6-flash:free

## 2.2.0

- Added agent config management — your agent can now help manage memory, compaction, and loop settings directly within the workspace
- Added custom model endpoints — bring your own API key to connect to any LLM provider, with custom models appearing in the model selector alongside platform models
- Added dynamic model catalog — model list is now fetched from the backend in real time, making new models available immediately without image redeployment
- Added new model: Kimi K2.6
- Fixed tool parameter type coercion

## 2.1.9

- Fixed wallet API errors and added support for transaction gas sponsorship configuration
- Fixed model call timeouts and improved retry logic for more reliable responses
- Fixed an issue where the agent could hallucinate about previous tool calls
- Upgraded to a new chart skill that creates interactive charts

## 2.1.8

- Upgraded task notifications — your agent now has full control over what it sends, how it looks, and where it goes
- Expanded wallet support to cover all chains available on DeBank
- Fixed an issue where conversation summaries could interfere with ongoing chats
- Added a new tool that lets your agent manage its own skills and improve over time
- Switched the default AI model to Smart Routing for better performance and lower cost
- Added a built-in slide creator skill — ready to use out of the box

## 2.1.7

- Optimized tool result limits handling and enhanced system guidance for exceptional cases
- Optimized cache cleaning during machine startup and improved the suspend user experience
- Strengthened tools loop prevention of the agent
- Simplified how chat history is compressed and saved during conversations
- Fixed memory sync getting stuck in a loop and failing to reconnect 
- Fixed push notification delivery
- Fixed Twitter URL handling error

## 2.1.6

- Added shortcut command pop-up on web for faster command access
- Improved context compaction with distinct summarizer prompts for sessions and tasks, saving important memory before conversations are compressed
- Upgraded to dual-file memory system with upgrades across storage and recall
- Improved smart routing default rules
- Improved cost tracking with comprehensive coverage across all proxy call paths, integrated with credit API to track combined LLM and proxy costs per task
- Improved agent error recovery and resolved issues where failed tools could cause infinite retry loops
- Fixed clear command issues and optimized compact logic to prevent context contamination

## 2.1.5

- Added popup form for skills and project with small screen adaptation
- Added right-click upload feature to workspace directory
- Added error log monitoring on the frontend
- Added new models:
  - z-ai/glm-5.1
  - qwen3.6-plus
- Restructured system prompt to reduce prompt cost with references doc architecture; users can now customize their agent through SOUL.md, IDENTITY.md, USER.md in workspace
- Updated preinstall project-builder skill to support end-to-end project engineering
- Improved web performance and reduced package size
- Improved Telegram bot security: token and private keys are now entered through a popup in the conversation and no longer recorded in chat
- Added protections to prevent infinite tool-call loops
- Various minor bug fixes and optimizations

## 2.1.4

- Added Korean language switch feature for multilingual support
- Added buy credits functionality in Telegram bot
- Added connector feature
- Added referral feature
- Added daily usage trend chart for credits
- Added Composio skill integration
- Added new models:
  - x-ai/grok-4.2
  - z-ai/glm-5v-turbo (GLM-5V with vision support)
  - qwen/qwen3.6-plus:free (Qwen 3.6 Plus free tier)
  - google/gemma-4-31b-it (Gemma 4 31B)
  - google/gemma-4-26b-a4b-it (Gemma 4 26B MoE)
- Added agent self-triggered local push notifications, allowing users to send custom reminders via scripts within their projects
- Improved CPU control during startup process to prevent high load during initialization
- Fixed tool timeout SSE disconnection issues
- Improved prompt optimization
- Various minor bug fixes and feature optimizations

## 2.1.3

- Added display of agent identity information, supporting changes to agent information (name, avatar, emoji, etc.) through conversation
- Added support for binding and unbinding of Telegram bot and WeChat bot through conversation
- Added support for adding Telegram whitelist through conversation
- Added support for switching Telegram bot/WeChat bot push notifications on and off through conversation
- Added ability for agent to send messages to Telegram bot, WeChat bot, Telegram bot whitelist, and Telegram bot group chats, including text information, file information, etc.
- Added skill download and view count statistics and display
- Added project favorites and view count statistics and display
- Added user information popup to display agent information, as well as published projects and skills
- Added official gas sponsorship for all agent wallets
- Improved agent's self-calling ability to support the new alert system

## 2.1.2

- Added WeChat connector for seamless integration with WeChat bot
- Added policy control switch for wallet management
- Added Woo staking recharge discount content
- Added wallet policy updates for enhanced control
- Added machine pre-warming logic that pre-installs all necessary resources when creating machines
- Added agent identity with configurable items through agent settings
- Added project click collection statistics tracking
- Improved recharge display for better user experience
- Improved startup scripts and skill management to skip unchanged skills on restart
- Improved skill installation by running install jobs in the background
- Improved agent runtime info to enhance session details
- Improved model's startup process by moving heavy logic to background for faster startup and restart speeds
- Fixed issue where user status was lost after WeChat bot restart

## 2.1.1

- Added Doctor Mode: /doctor command to help users diagnose and inspect machine issues
- Added Push Notification Controls: block or silence push notifications based on specific conditions
- Added new model: Minimax 2.7
- Improved self learning module 
- Fixed self learning versioning to persist after deployments or updates
- Fixed skill display issue

## 2.1.0

- Added new models:
  - x-ai/grok-4.20-beta (standard)
  - openai/gpt-5.4-nano (budget)
  - qwen/qwen3.5-9b (budget)
  - openai/gpt-5.4-mini (standard)
- Added website snapshot service optimizing image display for the project
- Added skill market
- Added close button to toast for more intuitive user operation
- Added display of all launched websites when browser has no tabs
- Added V1 self learning module for AI to learn from its mistakes
- Improved workspace sizing bar - double-clicking will snap it back to default position
- Improved agent error messages
- Fixed issues with skill install, empty response and error handling
- Fixed job cost tracking
- Fixed Hyperliquid integration to all instances
- Fixed prompt to show transactions on onchain transactions when returned in call

## 2.0.9

- Added real-time display writing during SSE output
- Added more logs and persistent logging in machine for debugging
- Improved projects UI optimization
- Improved display, editing, and deletion of inserted messages
- Improved SSE reconnection mechanism for web + tgbot
- Improved proactive skill system with further enhancements
- Improved websearch system that now uses past searches to build on the next search to create a more refined and deterministic research function and reduces duplicate searches and loops
- Fixed issue where the project resets after being set to public
- Fixed issue where forward messages in tgbot group chats and private chats could not recognize context
- Fixed issue where tgbot group chats did not recognize images + text
- Fixed positioning issue of the workspace right-click menu
- Fixed agent tool timeout handling and AI error retry logic
- Fixed schedule task refactoring and error reporting issues
- Fixed memory inject issues in agent
- Removed old orderly skills (orderly and orderly one) and replaced with the official orderly skill

## 2.0.8

- Added official skills repository infrastructure with dedicated repo for building and publishing skills
- Added GitHub Actions workflow for automatic frontmatter validation and skills.json rebuild
- Added container pre-install system for automatic official skills installation/updates on first launch
- Added skills-lock.json for tracking installed skill versions
- Added /compact command in Telegram bot
- Added /mute command in Telegram bot to disable scheduled job notifications
- Added project showcase in workspace displaying user-deployed websites
- Added asset information display in agent wallet
- Added option to hide usage information in Telegram bot responses
- Added safety net prompt in Telegram bot credits
- Improved launch my agent process optimization
- Improved charting system with enhanced functionality
- Improved core prompts for better agent responses
- Fixed issue where thread sharing images were not displaying
- Fixed voice input functionality bug
- Fixed Telegram bot inter-user messaging issue
- Fixed Orderly integration issues
- Fixed wallet-related bugs
- Fixed Polymarket integration
- Removed whitelist requirement for private chat functionality in Telegram
- Changed skills management to npx skills system with integration documentation

## 2.0.7

- Added Telegram bot service supporting private bot binding
- Added voice input support for web interface
- Added support for deleting completed and canceled scheduled tasks
- Added identifiers to Telegram threads for easier distinction
- Added model prices in model selection
- Added dashboard skill with comprehensive monitoring capabilities
- Added one-shot prompt system that proactively fixes errors until task completion
- Improved chat input box by removing character limit
- Improved display during tool execution
- Improved display of tables in Telegram
- Improved charting skill with overhauled prompt handling
- Improved agent understanding of proxy system
- Improved agent file editing to check for similar tasks and edit instead of recreating files to save tokens
- Improved dynamic chunking to prevent timeouts on long-running tasks by splitting into smaller subtasks within token limits
- Improved skill prompt handling and overhauled problematic prompts
- Fixed issue where dragging an image into chat input box resulted in duplicate images
- Fixed timezone handling for scheduled tasks in container
- Fixed issue where currentModel settings were being reset
- Fixed issue where messages were refreshed due to jobs resulting in information loss
- Fixed issue where Telegram could not recognize files sent to users
- Fixed errors in Bash Tool
- Fixed chart not showing in chat with added guardrails and definite prompts
- Fixed error issues regarding maximum iteration limits
- Fixed CoinGecko tools
- Fixed Birdeye tools
- Changed to unified marketplace
- Changed Telegram replies to display specific model name
- Enhanced tool schema validation for Gemini models
- Removed skills MCP integration
- Removed some supported networks from wallet integration after review

## 2.0.6

- Added preview-dev to guide web development
- Added dialog input box to cache user input information
- Added agent reply and user input copy function
- Added support for the Gemini 3.1 Flash-Lite
- Added support for internal API calls within localhost in machine
- Added model smart selection for scheduled tasks
- Added model cost in the agent runtime information
- Added new skills and endpoints
- Fixed the issue of authentication information disorder caused by the refresh token not being deleted
- Fixed the abnormal status display issue when the agent is working in the background
- Fixed the issue of port occupation in the preview server
- Fixed persisting user customized installation issues
- Fixed charting not showing in chat
- Fixed skills and tools issues
- Fixed job scheduler

## 2.0.5

- Added credit system
- Added support for inserting messages in dialogue to continue conversations
- Improved user agent creation time, reducing from 20-30 seconds to around 5 seconds
- Improved prompt cache to increase cache hit rate
- Improved memory management
- Updated default model from Sonnet 4 to Sonnet 4.6
- Fixed tool loader
- Fixed display anomalies caused by SSE disconnection when running in background on mobile
- Fixed logout caused by wallet disconnection
- Fixed issue where clicking a link on mobile cannot directly open workspace

## 2.0.4

- Added gift card redemption
- Improved decision tree prompt
- Improved wallet policy prompt 
- Fixed skill loader to detect all tools new and old
- Fixed Orderly skill commodities handling when it comes to externally added skills
- Fixed loading message not disappearing after SSE disconnection when conversation already completed

## 2.0.3

- Added support for multiple simultaneous conversations
- Added scheduled task execution with detailed logs
- Added share page with on-demand data loading to optimize performance
- Added prompt cache update
- Improved memory system
- Improved browser-preview skill by removing localhost text
- Fixed issues with Twelve Data API
- Fixed issue where images displayed incorrectly when using preview service
- Fixed issue where some users could not load more historical conversations
- Fixed occasional issue where input box image could not be cleared after sending a message
- Fixed issue of data loss after sharing
- Fixed issue where thinking data was not persistently saved after disconnecting chat

## 2.0.2

- Added browser-preview skill allowing agents to recognize browser functionality within front-end pages
- Added real-time tracking of token usage and credit consumption for every conversation round
- Added Birdeye and 12data as new data sources
- Added backend task continuation support for disconnected conversations due to network fluctuations or unexpected exits
- Improved chat homepage UI with centered input box and smooth animation transition to bottom after sending messages
- Improved context management with optimized context compact to prevent token overflow during deep multi-turn tool interactions
- Improved custom install management, fixing installation failures after reboots or automatic updates
- Improved Smart Routing with better model selection to reduce costs
- Improved model selection box with updated model configuration and categorization
- Improved wallet balance checking accuracy
- Improved charting system to reduce context bloat
- Upgraded skill installer skill for better performance
- Fixed issue where some users cannot connect to mainnet with EVM wallet plugin
- Fixed Phantom wallet recharge issue
- Fixed chat area width display issue
- Fixed issues with Hyperliquid tool TPSL functionality
- Fixed issues with Orderly tool
- Fixed issue with tool loader caching
- Fixed issue with networks not registered by Privy wallet

## 2.0.1

- Fixed issue where some users cannot connect to mainnet with EVM wallet plugin
- Fixed Phantom wallet recharge issue
- Fixed chat area width display issue

## 2.0.0

Starchild has evolved from a strategy creation tool into a complete personal AI agent platform. This major release introduces a sandboxed agent environment, multi-model AI routing, native crypto payment integration, and a comprehensive skill system - transforming how users research, trade, and automate their workflows.

- Added one-click agent deployment in secure sandboxed containers with 1024MB personal storage
- Added multi-model AI routing that reduces operational costs by up to 70% compared to standard OpenClaw deployments
- Added native Privy wallet integration supporting 29+ blockchains without exposing personal private keys
- Added customizable agent memory system that adapts to user preferences, trading styles, and time zones
- Added file system management for uploading and managing skills, images, scripts, and documents
- Added pre-loaded finance-specific skills spanning DeFi, prediction markets, and trading strategies
- Added skill creator functionality allowing users to create, download, and share custom skills
- Added recurring task scheduling that runs autonomously while users are offline
- Added human-readable skill format compatible with OpenClaw ecosystem
- Added web research capabilities across any topic or market
- Added code writing and review functionality
- Added document analysis and processing
- Added real-time market chat and analysis
- Added connections to trading venues, prediction markets, DeFi protocols, social platforms, and data feeds
- Added container-based isolation ensuring each user workspace remains private and secure
- Added sandboxed execution environment eliminating configuration vulnerabilities
- Added trustless wallet architecture preventing private key exposure during automated operations
- Added content moderation LLM to review all user-edited content
- Added protection against prompt injection, malicious inputs, and inappropriate content
- Added Paper Trading system upgrade with CoinGecko API integration, supporting all tokens with real-time prices
- Added instant entry feature for executing trades using natural language like "open long" or "buy now"
- Added XAU/XAG (gold/silver) trading support
- Added Watchlist and My Strategy sections to leaderboard
- Added profile picture editing in Account Management

## 1.1.1

- Added Paper Trading system upgrade with CoinGecko API integration, supporting all tokens with real-time prices
- Added content moderation LLM to review all user-edited content
- Added protection against prompt injection, malicious inputs, and inappropriate content
- Added instant entry feature for executing trades using natural language like "open long" or "buy now"
- Added XAU/XAG (gold/silver) trading support
- Added Watchlist and My Strategy sections to leaderboard
- Added profile picture editing in Account Management
- Improved chat page UI/UX
- Improved navigation bar and homepage UI styling
- Improved strategy generation to handle more complex strategies
- Improved chat flow and user guidance during strategy creation
- Improved strategy generation diversity and response formatting
- Improved tick size and execution accuracy for paper trading
- Improved strategy analysis accuracy with upgraded reasoning
- Improved connection stability with optimized heartbeat intervals
- Changed "All Time APR" to "ROE" on leaderboard, with APR shown for strategies over 30 days with positive ROE
- Fixed page crashes after creating strategies
- Fixed strategies failing due to API rate limiting
- Fixed connection timeouts during idle periods
- Fixed duplicate trade signals being sent
- Fixed price data not being read correctly in some API responses
- Fixed XAU/XAG validation errors when creating strategies
