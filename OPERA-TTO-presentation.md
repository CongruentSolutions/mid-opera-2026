# TTO at OPERA: six months of work, and the world of Bifrost

*Midyear OPERA organization jamboree · FY 2026-27 · 50 minutes · data as of 15 Oct 2026*

## Executive summary

**The Spark Initiative is complete. It was our internal target to build demos for conference season: the payroll prototype is done, and two further prototypes are built.**

- **Vaneesa, our ERISA bot, is operational.**
- **Three prototypes are built** on CORE through Bifrost: payroll with match and profit-sharing maths, participant investment analytics, and multi-agent orchestration with Camunda.
- **Two run live today**; the third is presented as architecture.
- **Bifrost holds 12 domain slices on main** and is the only door into CORE; Athena's agents propose and humans decide.
- **Toledo is at 9% (the average of its five key results) against a 31 Mar 2027 deadline.** The deck rates three at 0%: the orchestrator, the Requirement Engine and the coding agents.
- **The orchestrator has a working skeleton** (about 15–20% by our code review); the Requirement Engine and the coding agents have designs but no code.
- **Cordoba's traceability engine is ahead of its 15% rating**, at about 40–60% of scope by our code review.
- **RDX, the neutral industry exchange, has a full design and no code**, and no key result.
- **The Toledo, Cordoba and Dr Watson repositories have had no commits since August**, because the effort moved to the Spark prototypes.
- **Next:** finish Toledo, Cordoba and Dr Watson, use them to complete Bifrost, then build CORE module by module.
- **Plan for the next half:** restart the three key results the deck rates at 0%, with a plan to the 31 Mar 2027 deadline.

*Percentages marked "by our code review" are estimates from reading repositories, not deck figures.*

**Terms used**

| Term | Meaning |
|---|---|
| TTO | Technology Transformation Office. |
| OPERA | The organization's midyear review, where every department presents its last six months. |
| Key result | A measurable commitment under an objective. The deck tracks nine. |
| CORE | The recordkeeping platform for retirement plans. |
| Bifrost | The integration hub, and the only door into CORE. |
| Athena | The front end where agents prepare work and people approve it. |
| Toledo | The agentic software factory for CORE development. |
| Cordoba | The context brain for Toledo: it builds code context and links requirements to code and tests. |
| Dr Watson | The testing engine: it generates and runs test cases. |
| RDX | A neutral data exchange for the retirement industry. |
| Spark Initiative | Our internal target to build three agentic prototypes with CORE as demos for conference season. |
| CIATA | The draft framework that governs AI agents. |
| AGRUF | The draft framework that governs how people use AI tools. |
| MCP, A2A | Two standard ways for agents to call a service. |
| TPA | Third-party administrator of retirement plans. |

| Min | Segment | Format | Presenter |
|---|---|---|---|
| 0–5 | 1. Six-month progress | Talk | |
| 5–10 | 2. The world of Bifrost | Talk and diagram | |
| 10–20 | 3. Prototype 1: payroll and match / profit sharing math engine | Live demo | Srivas |
| 20–30 | 4. Prototype 2: participant investment analytics | Live demo | Amirtha Varshini, Haritha |
| 30–40 | 5. Prototype 3 architecture (multi-agent CORE orchestration), then what's next | Talk and diagram | |
| 40–50 | 6. Questions | | |

## 1. Six-month progress

**Opening line:** Vaneesa, our ERISA bot, is operational.

**Speaker line:** Nine key results sit under three objectives. The deck rates all nine on track against the 31 Mar 2027 due date. Here is what the work shows behind each number.

| Objective | Key result | Deck | Our actual progress | Why |
|---|---|---|---|---|
| CORE re-imaging | Spark Initiative | 60% | **100%** (owner-reported) | Payroll was the accepted scope and it is done. Two more prototypes are built. |
| CORE re-imaging | Bifrost, complete end to end | 30% | **Ahead of deck** | 12 domain slices on main, a CLI, agent endpoints, a participant API and a showcase. |
| Toledo | Dr Watson testing engine | 30% | **About 30%** (estimate) | A pipeline turns manual test cases into intent, and a .NET framework runs about 486 feature files. The two halves are not yet joined. |
| Toledo | Cordoba, the context brain | 15% | **About 40–60%** (estimate) | Scope is requirement-to-test traceability. It has a spec store, a matcher, 51 service specs and a portal. |
| Toledo | Agentic harness orchestrator | 0% | **About 15–20%** (estimate) | A working skeleton: intake gateways, a durable orchestrator shell, infrastructure code and CI. |
| Toledo | Requirement Engine | 0% | **0% code** | Business, functional and system requirement designs are written. |
| Toledo | Coding and review agents | 0% | **0% code** | Not started in code. |
| Organizational AI capability | Team capability | 0% | **Deck figure** | No repository evidence. |
| Organizational AI capability | AI practitioner guild | 20% | **Deck figure** | No repository evidence. |

*Percentages marked estimate come from reading the repositories and commit history. Nothing was run to produce them.*

**What to say**
- **The deck understates our progress in four places:** Spark, Bifrost, Cordoba and the Toledo orchestrator.
- **Spark moved the most** because the October effort went into the prototypes you will see today. That is also why the Toledo, Cordoba and Dr Watson repositories are quiet since August.
- **Toledo's foundation is laid.** The delivery environment, work-item setup, intake and CI are in place. The agents are the next layer on top.
- **Not shown in the deck:** RDX, the neutral industry exchange, has a full design and no code.

## 2. The world of Bifrost

**Speaker line:** Everything we built this half sits on one idea. CORE keeps the financial truth, Bifrost is the only door into it, and AI agents work through that door under rules.

```
                          THE WORLD OF BIFROST

 INDUSTRY SIDE                                              CORE SIDE

 Payroll providers ─┐
 TPAs ──────────────┤
 Compliance engines ┼──► RDX ───────────┐
 Other recordkeepers┘   neutral exchange│
                        map once,       │
                        connect many    ▼
 ATHENA ───────────────────────►  BIFROST  ───────────►  CORE
 (agents propose,                (authorization,        (validate, calculate,
  humans decide)                  gates, audit)          human review)
                                     ▲
 External orchestrators ─────────────┘      Consent providers
 (e.g. Camunda)
```

**The four pieces, in one line each**

| Piece | What it is | What it does not do |
|---|---|---|
| CORE | The recordkeeping system: plans, payroll, accounts, distributions, loans. | It is not reachable except through Bifrost. |
| Bifrost | The integration hub and the only door into CORE. It holds authorization, approvals, idempotency, events and audit, and speaks REST, MCP and A2A. | It does not decide on a person's behalf. |
| Athena | The front end for people and agents. Agents prepare and explain; a human approves. | It never touches CORE directly. |
| RDX | A neutral exchange for the retirement industry. A payroll provider or TPA connects once and reaches every recordkeeper. CORE is one participant, reached through Bifrost. | It does not judge the meaning of data, and it is not built on CORE's stack. Today it is a design, with no code yet. |

**Why the shape matters**
- Agents are fast and can be wrong, so authority stays in the middle. Athena proposes, a human decides, Bifrost verifies and records, and CORE applies the change.
- Any agent, ours or a partner's such as Camunda, uses the same door and the same rules.
- RDX is separate on purpose. If competing recordkeepers are to trust it, it cannot be owned by one of them.

**The trust layer around it (draft framework from the AI Reboot)**
- **CIATA** governs agents: each agent has an identity, a scope, an autonomy level from 0 to 4, human-in-the-loop rules, and a replayable log.
- **AGRUF** governs how people in the company use AI tools: approved tools, data-use rules, a signed declaration, and checking AI output before use.

## 3. Prototype 1: payroll and match / profit sharing math engine

**Presenter: Srivas.** Live demo, 10 minutes.

## 4. Prototype 2: participant investment analytics

**Presenters: Amirtha Varshini and Haritha.** Live demo, 10 minutes.

## 5. Prototype 3 architecture, and what's next

**Speaker line:** The third prototype shows what happens when several agents and a process engine work one CORE task together. We present its architecture today.

**The use case: a participant withdrawal.** A withdrawal arrives as a document. It has to be read, checked against plan facts, consented to, submitted and approved by a person, and every step must be auditable.

```
 Camunda                Athena               Bifrost                 CORE            Consent provider
 (process engine)       (evidence agent)     (MCP + A2A gateway)

 1 UNDERSTAND THE DOCUMENT
 document + hash ─────► reads layout,
                        classifies content
                        ──── authorized fact reads (MCP) ────►
                        ◄──── participant and plan facts ─────
 ◄── evidence + findings
     Athena's work ends here.

 2 PREPARE THE REQUEST
 extracted data ─────────────────(A2A task)────────►  stores incomplete  ───►
 ◄── task ID, request revision, evidence still required ──   request

 3 CONSENT
 start signing / notarization ──────────────────────────────────────────────────►
 ◄── authentic callback + provider evidence ────────────────────────────────────
 attach consent evidence ─────────(MCP)───────────►
 submit under accepted human authority ───(MCP)───►  revalidates ───► submits

 4 HUMAN REVIEW IN CORE
                                                              person reviews in CORE UI
 ◄─── recorded outcome: approved or rejected (A2A) ──  ◄──── authoritative decision
```

**What the audience should take from it**
- **Each party has one job.** Camunda runs the process, Athena prepares evidence, Bifrost governs and records, CORE decides through a person.
- **Agents never hold final authority.** Athena stops at the evidence handoff. Submission needs accepted human authority, and a person in CORE gives the decision.
- **A partner's agent can use the same door.** Camunda uses Bifrost's agent endpoints (MCP and A2A), and a partner's agent would use the same ones under the same rules.
- **It follows CIATA.** Roles, scope, human checkpoints and a replayable log are designed into the flow. CIATA is a draft framework.

**What is in place**
- Athena's evidence preparation, reading documents and facts through Bifrost.
- Bifrost's agent endpoints (MCP and A2A) and the withdrawal inputs on its API.
- A Camunda sample worker and receiver.
- The CORE consumer that receives the withdrawal request.

### What's next

**Immediate focus: finish the Toledo software factory.** Toledo, Cordoba and Dr Watson come first.

1. **Complete Toledo, Cordoba and Dr Watson.** Toledo's orchestrator, Requirement Engine and coding and review agents, Cordoba's code context, and Dr Watson's test generation and execution.
2. **Use them to complete Bifrost.** The factory builds, tests and traces Bifrost's remaining work end to end.
3. **Then build CORE module by module.** Each module goes through the same factory, behind Bifrost, with CIATA governing every agent.

**Also on the plan**
- **Restart the three Toledo key results the deck rates at 0%** (orchestrator, Requirement Engine, coding and review agents) with a plan to the 31 Mar 2027 deadline.
- **Connect Dr Watson's two halves** so test cases flow from requirements to executable tests.
- **Decide RDX:** build, defer, or fold into Spark, and give it a key result if built.
- **Adopt CIATA** as the standard for every agent, and publish AGRUF to the company.

## 6. Questions

**Speaker line:** Ten minutes for questions. Bring anything about the architecture, the prototypes, or how your team can use them.

**Likely questions and short answers**

| Question | Answer |
|---|---|
| Can an agent move money on its own? | No, not in any flow we have built. Agents prepare and explain. A person approves, Bifrost verifies the person, and CORE applies the change. |
| How do we know what an agent did? | Bifrost records the actions and approvals. CIATA requires every agent to have an identity, scope and replayable log. |
| What stops an agent from seeing data it should not? | Agents reach CORE only through Bifrost, with authorization checked at Bifrost. AGRUF sets the rules for people using AI tools. |
| Can a partner's agent connect? | Yes, through the same Bifrost endpoints (MCP and A2A) under the same rules. |
| What is RDX, and how is it different from Bifrost? | Bifrost is CORE's door. RDX is a neutral exchange for the industry, and CORE is one participant behind it. |
| What does the Spark result mean? | Spark was our internal target to build demos for conference season. Payroll was the accepted scope and it is done; the participant and orchestration prototypes extend it. |
| Why are three Toledo key results rated 0%? | The orchestrator has a working skeleton. The Requirement Engine and the coding agents have designs and no code yet. Finishing Toledo, Cordoba and Dr Watson is the immediate focus. |
| Why no commits since August? | The effort moved to the Spark prototypes. Toledo, Cordoba and Dr Watson are the immediate focus next. |
| How can my team get involved? | Join the AI practitioner guild and bring a workflow to redesign with agents. |

*Fill in the last answer with the real guild contact and next date.*
