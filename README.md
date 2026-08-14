# SwarmTrade™ V5 Runtime Architecture

## Persistent Multi-System Market Intelligence Infrastructure

10XT SwarmTrade™ V5 is a production runtime for continuously evaluating, synthesizing, ranking, and maintaining market intelligence across multiple independent trading systems.

Six specialist systems continuously evaluate the same eligible universe of liquid crypto markets through distinct methodologies:

* Trend
* Momentum
* Volatility
* Breakout
* Mean Reversion
* Structure / Wyckoff

Their outputs are not distributed as six independent signals.

SwarmTrade continuously normalizes and synthesizes their evidence into a persistent market state consisting of:

* directional bias
* system confluence
* Swarm Score
* market ranking
* leading methodology
* freshness / last validation
* lifecycle state

Every qualifying Long or Short conviction event is timestamped when it forms and measured forward through maximum favorable excursion (MFE), maximum adverse excursion (MAE), duration, and the market state when conviction fades.

This creates a continuously expanding forward evidence ledger of:

**what the systems observed → when conviction formed → how the market subsequently behaved.**

The execution boundary is explicit.

10XT owns the intelligence, evidence, ranking, state persistence, monitoring, and forward measurement layers. When a trader chooses to act, `Trade This Market` hands the user to the appropriate instrument on their exchange.

Position size, leverage, order type, stop loss, take profit, trailing logic, and final execution remain under the trader's control at the venue.

SwarmTrade is therefore not a conventional screener, signal feed, strategy marketplace, or black-box trading bot.

**It is a persistent market-intelligence orchestration layer between raw market data and venue-native execution.**

---

# 1. The Infrastructure Problem

Most trading products operate on one part of the trading workflow.

Screeners filter markets.

Charts visualize them.

Indicators describe individual conditions.

Signals identify discrete opportunities.

Bots execute predefined logic.

Exchanges execute orders.

The missing layer is the infrastructure required to continuously reconcile multiple independent trading methodologies into a persistent, ranked view of market state.

A trader operating manually must repeatedly:

**search markets**

→ **evaluate multiple methodologies**

→ **reconcile conflicting evidence**

→ **determine directional conviction**

→ **prioritize opportunities**

→ **monitor changing conditions**

→ **decide whether to act**

SwarmTrade moves this process into a continuously operating runtime.

The system repeatedly asks:

> **Across the eligible market universe, where does independent trading evidence currently converge strongly enough to deserve attention?**

The output is not another isolated prediction.

It is a continuously maintained intelligence state.

---

# 2. From Trading-System Runtime to Swarm Runtime

The SwarmTrade architecture builds on infrastructure originally developed by 10XT to operate continuously running trading systems.

The original runtime problem was:

**Strategy Logic**

→ **Runtime Initialization**

→ **Persistent System**

→ **Exchange Execution**

Running strategy code reliably required infrastructure beyond the strategy itself:

* runtime provisioning
* process isolation
* container orchestration
* configuration management
* exchange connectivity
* lifecycle controls
* logging
* health monitoring
* execution state
* restart and recovery
* deployment reproducibility

10XT built this infrastructure to operate individual systematic trading strategies as persistent production systems.

SwarmTrade V5 extends that architecture upstream.

Instead of asking only:

> **How do we keep one trading system operating?**

V5 asks:

> **How do we operate multiple independent trading systems continuously against the same market universe, reconcile their evidence, preserve their state, and determine which markets deserve attention now?**

The architecture therefore evolved from:

**Strategy → Runtime → Execution**

to:

**Market Universe**

→ **Multiple Independent Systems**

→ **Swarm Synthesis**

→ **Persistent Market State**

→ **Ranking**

→ **Market Intelligence Profile**

→ **Continuous Monitoring**

→ **Forward Evidence**

→ **User Decision**

→ **Venue-Native Execution**

The production runtime remains underneath the Swarm.

It is now the infrastructure supporting a larger intelligence system.

---

# 3. Market Universe and Ingestion

SwarmTrade begins with a professionally curated reference universe of liquid crypto markets.

The purpose of the universe is not to maximize the number of markets observed.

It is to provide a sufficiently broad but execution-relevant set of instruments against which the same intelligence process can operate continuously.

The ingestion layer handles:

* exchange market data
* symbol metadata
* market normalization
* venue availability
* eligible instrument mapping
* price and volume state
* freshness validation
* liquidity / venue checks

Markets unavailable through supported venues can be excluded from the execution-relevant universe.

This creates a normalized market layer before strategy-specific interpretation begins.

Conceptually:

**Exchange Data**

*

**Market Metadata**

*

**Venue Availability**

↓

**Normalized Eligible Universe**

↓

**Six-System Evaluation**

The universe is therefore an input to the intelligence engine rather than a collection of manually selected trade ideas.

---

# 4. Six Independent Intelligence Systems

Each eligible market is evaluated through six distinct trading methodologies.

## Trend

Evaluates directional persistence and established market movement.

## Momentum

Evaluates acceleration and directional strength.

## Volatility

Evaluates expansion, compression, and volatility-driven opportunity.

## Breakout

Evaluates movement beyond established price structures and ranges.

## Mean Reversion

Evaluates displacement from conditions where reversion may become statistically or structurally relevant.

## Structure / Wyckoff

Evaluates market structure, accumulation/distribution behavior, and structural conditions not necessarily captured by faster directional methodologies.

These systems are intentionally heterogeneous.

They are not six copies of the same directional model.

They can:

* agree
* disagree
* remain inactive
* become relevant at different points in a market cycle
* withdraw support as conditions change

This distinction is important.

A displayed state such as **4/6 Long** does not necessarily imply that two systems are actively Short.

The remaining methodologies may simply lack a qualifying condition.

For example:

**Trend — Long**

**Momentum — Long**

**Volatility — Long**

**Breakout — Long**

**Mean Reversion — No qualifying state**

**Structure / Wyckoff — No qualifying state**

This is fundamentally different from four Long systems opposed by two Short systems.

SwarmTrade's value therefore lies not merely in counting votes, but in synthesizing heterogeneous evidence into usable market state.

---

# 5. Swarm Synthesis

The synthesis layer converts independent system outputs into a unified market-intelligence object.

For every evaluated market, the Swarm can maintain:

* system-level evidence
* system alignment
* directional confluence
* opposing evidence
* directional bias
* Swarm Score
* leading methodology
* market ranking
* freshness
* last validation
* lifecycle state

The output is a persistent representation of the market rather than an isolated alert.

Conceptually:

**Trend**

**Momentum**

**Volatility**

**Breakout**

**Mean Reversion**

**Structure / Wyckoff**

↓

**Normalize**

↓

**Align**

↓

**Measure Confluence**

↓

**Determine Bias**

↓

**Calculate Swarm State**

↓

**Rank**

↓

**Persist**

↓

**Revalidate**

This synthesis process is the core orchestration layer of SwarmTrade.

---

# 6. Bias Formation

Markets can occupy three primary directional states:

**Long**

**Short**

**Neutral**

Long and Short states represent qualifying directional convergence among the independent systems.

Neutral does not mean the market lacks information.

It means the evidence has not reached the threshold required for directional Swarm conviction.

This allows the system to distinguish between:

> **interesting market activity**

and

> **sufficiently aligned directional evidence.**

Neutral markets can continue to be evaluated continuously.

As evidence changes, a market can move through states such as:

**Neutral**

→ **forming directional confluence**

→ **Long / Short**

→ **persistent conviction**

→ **deteriorating confluence**

→ **Neutral**

This lifecycle is central to the architecture.

SwarmTrade does not simply generate a Long or Short alert and stop observing the market.

The market remains inside the intelligence system.

---

# 7. Swarm Score and Ranking

Swarm Score is designed to represent the strength of the current multi-system evidence.

It is not a predicted return.

It is not a probability that a trade will be profitable.

It is not intended to imply that a market with a score of 75 must outperform a market with a score of 65.

The score contributes to a larger ranking process designed to answer a different question:

> **Which currently qualifying markets deserve the trader's attention first?**

This distinction is fundamental.

The product is not optimized around maximizing the number of signals.

It is designed around **market prioritization**.

The system can evaluate a broad universe while presenting only a much smaller ranked subset to the trader.

The resulting workflow is:

**Large Market Universe**

↓

**Continuous Evaluation**

↓

**Qualifying Directional States**

↓

**Relative Ranking**

↓

**Top Opportunities**

This converts market-wide monitoring into a focused decision surface.

---

# 8. Five-Minute Continuous Revalidation

Market intelligence decays.

A directional condition that was valid fifteen minutes ago cannot simply be assumed to remain valid.

SwarmTrade therefore operates as a continuous system rather than an event generator.

The current Swarm cadence re-evaluates the eligible market universe every five minutes.

Each cycle can update:

* system evidence
* confluence
* directional bias
* Swarm Score
* ranking
* leading methodology
* freshness
* lifecycle state

This creates an important architectural distinction.

A traditional signal system produces:

**Event → Alert**

SwarmTrade maintains:

**State → Revalidation → State Change → Revalidation**

The intelligence object remains alive while the market evolves.

---

# 9. Persistent Market State

Persistent state is one of the defining characteristics of the architecture.

A market is not represented only by its current price or most recent signal.

SwarmTrade maintains the context required to understand how its intelligence state developed.

That state can include:

* when directional conviction formed
* current direction
* current confluence
* Swarm Score
* leading system
* last validation
* duration in state
* whether conviction remains active
* whether the market has faded back to Neutral
* forward movement since formation

This allows the system to distinguish between:

**a newly formed state**

and

**a market that has remained in conviction for an extended period.**

That distinction is important for both traders and forward measurement.

---

# 10. Market Intelligence Profile

Once a market qualifies for elevation, SwarmTrade can structure its current state into a Market Intelligence Profile.

The profile is the bridge between market-wide ranking and individual market evaluation.

It can present:

* market
* directional bias
* Swarm Score
* system confluence
* leading methodology
* current market context
* evidence summary
* freshness / last validation
* relevant structural information

The profile is not intended to make the user's execution decision for them.

Its purpose is to transform:

> **“This market ranks highly.”**

into:

> **“This is the evidence underlying the current ranking.”**

This preserves transparency between ranking and user action.

---

# 11. Vault Monitoring

Markets selected by the user can remain under continuous observation through the Vault.

The Vault is not a static watchlist.

The underlying Swarm continues to re-evaluate the saved market.

As conditions change, the system can update:

* directional state
* confluence
* Swarm Score
* freshness
* ranking
* supporting evidence

This preserves continuity between discovery and monitoring.

The workflow becomes:

**Discover**

→ **Evaluate**

→ **Save**

→ **Continue Monitoring**

rather than:

**Discover → Forget**

The same intelligence engine remains active underneath the user's selected universe.

---

# 12. Forward Evidence Ledger

Every qualifying directional event can create a timestamped evidence record when conviction forms.

The system then measures what happens afterward.

A forward evidence record can include:

* market
* side
* opened timestamp
* Swarm Score
* confluence
* leading methodology
* lifecycle status
* duration
* maximum favorable excursion
* maximum adverse excursion
* return when conviction fades
* last validation

The purpose is not to construct hypothetical trading returns.

It is to measure the behavior of the market after Swarm conviction formed.

This distinction is critical.

SwarmTrade does not need to assume:

* user leverage
* position size
* stop placement
* take-profit level
* trailing-stop methodology
* execution timing
* slippage
* fees
* funding

Those variables belong to the trader and the venue.

The evidence ledger instead answers:

> **After the Swarm formed directional conviction, what did the underlying market actually do?**

---

# 13. MFE and MAE

Two measurements are particularly important.

## Maximum Favorable Excursion — MFE

The largest favorable underlying market movement observed after conviction formed.

## Maximum Adverse Excursion — MAE

The largest adverse underlying market movement observed during the same lifecycle.

These are measured on the underlying market rather than hypothetical leveraged P&L.

For an advanced trader, the combination of:

**MFE**

**MAE**

**duration**

**time in conviction**

can be considerably more informative than an arbitrary fixed exit assumption.

This preserves the objectivity of the intelligence layer.

A market that moves +0.50% before conviction fades has produced a +0.50% favorable underlying excursion regardless of whether an individual trader:

* took profit at +0.20%
* trailed the position
* exited manually
* remained in the position
* never traded the opportunity

The evidence layer measures the market.

The trader determines execution.

---

# 14. Evidence Before Outcome

The timing of the evidence record is fundamental.

Swarm events are recorded when the qualifying state forms, before the subsequent market outcome is known.

This creates the sequence:

**Evidence**

↓

**Conviction**

↓

**Timestamp**

↓

**Forward Market Behavior**

↓

**Measurement**

rather than:

**Historical Outcome**

↓

**Retrospective Signal Selection**

The architecture is therefore designed to produce an accumulating forward record of Swarm behavior.

Over time, this creates a dataset that can be analyzed across:

* market
* direction
* score
* confluence
* leading methodology
* duration
* MFE
* MAE
* market regime

The objective is transparent measurement rather than retrospective performance construction.

---

# 15. Execution Boundary

SwarmTrade V5 has an explicit execution boundary.

10XT owns:

* market evaluation
* multi-system evidence
* confluence
* directional state
* ranking
* Swarm Score
* Market Intelligence Profiles
* freshness
* monitoring
* state persistence
* forward evidence
* archive

The exchange owns:

* order entry
* leverage
* position sizing
* stop loss
* take profit
* trailing stop
* exchange-native risk controls
* fill execution
* venue-specific order behavior

The trader owns the decision.

This separation is intentional.

---

# 16. Trade This Market

When a trader chooses to act on a Swarm opportunity, `Trade This Market` provides the transition from intelligence to execution.

V5 does not require 10XT to recreate the exchange's order ticket.

Instead, the user is handed to the appropriate market/instrument through the supported venue workflow.

The sequence is:

**Swarm Ranking**

↓

**Market Intelligence Profile**

↓

**User Review**

↓

**Trade This Market**

↓

**Exchange / Instrument Handoff**

↓

**User Configures Trade**

↓

**Venue-Native Execution**

The trader can then configure the execution parameters supported by the exchange, including:

* order type
* position size
* leverage
* stop loss
* take profit
* trailing stop
* other venue-specific controls

This keeps execution where the trader already expects it to occur.

---

# 17. Non-Custodial Design

10XT does not need to take custody of user capital to provide the intelligence layer.

The architectural principle is:

> **Intelligence in. Execution out.**

The trader remains in control of:

* exchange account
* capital
* leverage
* position sizing
* risk controls
* final order submission

This preserves a clean boundary between market intelligence and venue-native execution.

The system's job is to answer:

> **Where should I look, why does it matter, and what does the current evidence say?**

The exchange's job is to execute the trader's decision.

---

# 18. Production Runtime Architecture

SwarmTrade is supported by the production infrastructure originally developed to operate persistent trading systems.

The runtime stack includes:

* Kubernetes / EKS orchestration
* isolated system deployments
* pod-per-system architecture
* Helm-rendered deployment infrastructure
* backend runtime services
* Flask / Uvicorn services
* Supabase authentication and persistence
* runtime logging
* trade-state persistence
* health endpoints
* heartbeat monitoring
* stale-state detection
* secure ingress
* supported exchange connectivity

The architecture separates intelligence logic from the infrastructure required to keep that logic continuously operational.

---

# 19. System Isolation

Independent trading systems operate within defined runtime boundaries.

Isolation provides:

* process separation
* configuration separation
* lifecycle independence
* fault containment
* reproducible deployment
* system-specific observability

A failure or restart in one system should not require interruption of unrelated systems.

This matters increasingly as SwarmTrade moves from operating individual systems to coordinating multiple systems continuously across the same market universe.

---

# 20. Health and Runtime Monitoring

Continuous intelligence requires continuous infrastructure.

The runtime therefore maintains operational health independently of market intelligence.

The architecture includes:

* 60-second heartbeat monitoring
* 120-second stale-state threshold
* runtime health endpoints
* system status
* structured logs
* execution-state visibility

A system that stops reporting expected runtime state can be identified independently of its strategy output.

This separates:

**“The system currently sees no opportunity.”**

from:

**“The system is not operating correctly.”**

That distinction is essential in an always-on intelligence architecture.

---

# 21. Runtime Reliability

The production runtime has operated more than 100 founder systems, including systems maintained continuously for periods extending beyond six months.

Management's runtime record to date has been effectively 100% uptime across those systems, with no known system loss attributable to the runtime layer.

This claim is separate from strategy performance.

A trading methodology can be profitable or unprofitable.

A market can move favorably or adversely.

Those are trading outcomes.

Runtime reliability asks a different question:

> **Did the system remain operational and continue executing its intended process?**

The infrastructure is designed to make those two questions independently measurable.

---

# 22. Programmatic Deployment

Trading-system environments can be initialized programmatically.

Deployment inputs can include:

`namespace`

Unique identifier for the deployment.

`strategy_class`

Python class defining the strategy implementation.

`strategy_code`

Strategy code supplied to the runtime.

`config`

JSON-serializable runtime and execution configuration.

The backend translates these inputs into deployable runtime infrastructure.

Conceptually:

**Deployment Request**

↓

**Validation**

↓

**Runtime Configuration**

↓

**Manifest Generation**

↓

**Namespace Provisioning**

↓

**System Deployment**

↓

**Health Verification**

↓

**Persistent System**

This allows trading-system deployment to become a machine-driven infrastructure operation rather than a manual server-management process.

---

# 23. Runtime-Aware Development

The underlying runtime preserves visibility into deployed systems.

Operators can inspect:

* execution behavior
* runtime logs
* operational state
* system health
