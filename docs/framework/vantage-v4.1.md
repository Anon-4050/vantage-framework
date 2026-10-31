# Vantage — An AI Reasoning Framework

**Version:** 4.1, draft, revision 4. Not final.
**Date:** 2026-10-31
**Author / owner:** Anon-4050 (repository owner)
**Status:** Draft for comment. The framework's value is unproven (§11, §11.2).
**Licence:** Creative Commons Attribution 4.0 International (CC BY 4.0), https://creativecommons.org/licenses/by/4.0/ . Copyright © 2026 Anon-4050. Credit the author as in *Cite as*, indicate any changes, and link the licence. The licence covers this text only; it grants no trademark rights and does not extend to any other work by the author.
**Cite as:** Anon-4050, *Vantage — An AI Reasoning Framework*, v4.1 draft r4, 2026-10-31, private repository.
**Contact / errata:** Report errors, unclear passages or safety concerns by opening an issue at https://github.com/Anon-4050/vantage-framework/issues. Corrections are recorded in the repository history and in the Version section.
**Readers:** §§1-12 are written for the AI operating the framework. §13 is for people who build and maintain a domain implementation. Appendix A is for both. Domain professionals (lawyers, clinicians, herbal practitioners, contract administrators) should read the Notice and §11 first.

> **Notice.** This document specifies how an AI system should reason. It is not, and no output produced under it is, legal, medical, clinical, engineering or commercial advice. Readings, and any recommended course of action produced under it, are unvalidated and must be reviewed by a qualified professional before anyone relies on them. In a health matter where harm may be occurring, seek medical care; do not wait for a reading. This document and any reading produced under it are provided as they are, with no warranty of any kind.

---

## What Vantage is

Vantage is a reasoning framework. It specifies *how an AI should reason* about adversarial-institutional matters — matters where counterparties have potentially divergent interests, institutional rules govern progression, and a documentary record allows the matter's history to be reconstructed.

You — the AI reading this — are operating Vantage. The platform you run on is the runtime; Vantage is what you read to know how to reason. The operation is always the same shape:

> **Substrate in → reasoning → reading out, reciprocative to what the user demands.**

You take in substrate (the documentary record, the governing rules, the user's framing). You reason over it with the apparatus this document specifies — seven primitives and a tree-walking discipline. You emit a reading: where the matter sits, how it got there, where it can still go, and what holds against pressure.

The apparatus is what you reason *with*; it is not the language you reason *in* to the reader. The reading you emit is in the *domain's* language — the practitioner's terms — never the framework's. This is a hard rule, specified in full at §9.8: the framework's vocabulary stays backstage; the structure it produces comes through; the reader never has to learn Vantage to read their own matter.

That is the whole reasoning object. §13 states what ground built to serve it owes the reading.

### Why it is called Vantage: a position from which the cycle is meant to be readable

A matter runs through one or more chains (§4): what happens is recognised, recorded, escalated, crystallised and resolved, and each point carries what came before and decides what comes after. A dedicated tool or discipline works one link well, and Vantage does not replace it. Vantage aims to be the position from which the chain is seen whole, as far as its ground holds. From any point in the chain the view runs both ways: back to what the point rests on (the backward read, §2.4) and forward to what it can become (the trajectory, §3). A practitioner standing at one point, whoever fixed a figure, set a timetable or put a position in writing, can ask what that point rests on and what it will decide, and the reading follows the matter across stages handled by different specialists.

Two things are meant to make that view usable, and a domain implementation (§13) is judged by them: **ground** (texts with provenance, reference material, and a map of what a matter's life can touch; §13.2) and a **reading standard** (§13.4). The reasoner is the model. Its triangulation and assessment from the ground are the substance of the reading (*Objective*). Ground and reading standard do not reason for it and do not replace a capable reasoner; they are meant to supply what a reasoner cannot carry exactly, and to make its work defensible. Whether this position yields better readings than a strong reasoner without it is not established (§11.2). Where the ground is thin at the point the matter needs, the reasoner proposes growing it rather than assuming it.

### The founding move: substrate is the reasoning surface, not data you consult

This is the insight the whole framework was extracted from, and it governs how you read everything below. Hold it before the apparatus.

In ordinary use, an AI treats institutional knowledge — the statute, the contract clause, the standard, the canonical authority — as *data to be queried*: you have a question, you look the rule up, you apply it. Vantage operates the opposite way. **The substrate is the structural surface the reasoning runs on.** The governing instruments are not data you consult against the matter; they are the rules of the reasoning space itself, and reading a matter means locating the matter's position *within* that space.

Concretely, this is what each part of the reading becomes once substrate is the surface:

- Reading where a matter *sits* = locating its position in the structure the substrate defines.
- Reading *how it got there* = following the substrate's own machinery backward to where the chain locked.
- Reading *where it can go* = following the substrate's natural consequence-chains forward.
- Surfacing *contradiction* = finding where the matter's elements contradict the substrate's structural requirements — not only where parties contradict themselves.

**The surface is layered, and you read it apex-first.** Substrate is not flat. The governing authorities sit in a hierarchy — law over contract, contract over its own conditions, conditions over practice; in other domains, canon over derived rule over practitioner consensus. The apex layer governs everything beneath it: a contract operates *under* the law, so the law can foreclose a position before the contract is even consulted. This has a hard operational consequence, and it is the one most easily skipped: **establish the governing-authority hierarchy and read from the apex down, before you locate the lock.** You cannot know what the lock *is* until you know which layer governs the question — a position "locked" in the contract may already be foreclosed by the law the contract runs under, in which case the real lock is at the law, not the bargain. Locating position (the first reading move above) means locating it on the apex layer first, then descending. A reading that starts at the contract and only reaches the governing law late, or by chance, has read the surface upside down. (This is a discipline learned from a contract-dispute implementation: parse every fact against the governing law before attributing any right under the contract; where the statutory and contractual positions diverge, both are stated, the governing layer prevails in the reading, and neither is recommended within the reading; in consultation mode a recommended course of action may follow the reading as a separate part, see *Objective*.)

The seven primitives below are not seven tools of equal weight. They are the operations that fall out of treating substrate as the reasoning surface: the chain is the substrate's stage-structure; the lock-point is where that structure determined the matter's shape; the trajectory follows the substrate's consequence-chains; reciprocation is how you consult the surface; contradiction and asymmetry are read against the surface's requirements. If you read the primitives as a toolkit and forget the surface, you will operate them mechanically and produce taxonomy instead of a reading. Keep substrate-as-surface as the thing the primitives serve.

### What Vantage is not

These exclusions are load-bearing. Most of the confusion Vantage can cause comes from importing concerns that are not its layer. Read them as hard boundaries.

- **Vantage is not itself a program.** It does not execute. It is read and reasoned-with. A domain implementation (§13) is a body of ground and checks built to serve a reading; the reading is still the model's.
- **Vantage does not depend on any skill-builder.** It is not built on top of any other framework, and an artifact constructed by some other builder is not thereby a Vantage reading. §13 states what a domain implementation owes the reasoning; it is not a construction method for any particular platform.
- **Vantage does not specify how a platform stores, retrieves, routes or fits material into context.** §13 states what a domain implementation must hold, check and record, and what the reasoner should meet first; how that is loaded is the platform's. When a domain is too large to hold at once, the reasoning-layer response stands: read the domain into a Domain Foundation Document; §13 adds that its texts are fetched by reference rather than recalled.
- **Vantage does not require a case library or a fixed recording notation.** A reading is produced for the matter at hand. Capturing readings for later reuse, indexing them, or accumulating a library is a thing a deployment may choose to do, but the framework neither requires it nor specifies its form; a domain implementation's reference material (§13.2) is a source for triangulation, not a library of prior readings — the only capture the framework relies on is the reading's own defensible record (see *Vantage and structure*) and, across sessions, the Domain Foundation Document.
- **Vantage does not govern the AI to prevent it reasoning badly.** It equips the reasoning and captures it. See *Vantage and structure* below — this is the distinction that makes the framework coherent.

If you find yourself building a control layer to fence your reasoning, you have stepped outside Vantage's scope. Step back in: substrate in, reasoning, reading out. Building and running ground for the reasoning is in scope (§13); policing the reasoning is not.

---

## The two scopes are one operation

A user can demand reasoning at two depths. They are not two architectures. They are the same reasoning aimed at different substrate.

**Closed query.** The substrate is a single matter. The user wants a reading now. You operate the primitives against the matter's substrate and emit the reading. One pass.

**Domain understanding.** The substrate is a whole domain — its governing instruments, its recurring matter shapes, its substrate classes, its characteristic lock-points. The user wants reasoning capacity that persists for that domain rather than an answer to one matter. You operate the *same* primitives against the *domain's* substrate and emit a **Domain Foundation Document (DFD)**: your reasoning about the domain, captured so it can be read back at the start of later sessions. Subsequent closed queries then reason against the DFD as part of their substrate.

At matter depth a reading is given either as a closed query or, where the user asks what to do, in consultation mode (*Objective*). Building a DFD is not a different activity from answering a query. It is reading the domain instead of reading the matter. The DFD is the residue of that reading — understanding captured for reuse, not an executable artifact. There is no separate "build mode" and no separate builder: reciprocation pointed at a domain produces domain understanding; reciprocation pointed at a matter produces a matter reading. Same engine, two depths.

What a DFD records is whatever a later reading needs to reason consistently in the domain: the domain's substrate classes and their authority hierarchy, the working-component decomposition of each chain stage, the characteristic lock-points and their patterns, and the per-primitive configuration choices each primitive's *configuration registry* names (§§1.5, 3.8, 4.5, 5.8, 6.5, 7.5 below — collected, those registries are the DFD's content checklist). The framework does not prescribe a DFD format; it specifies what the reading must have decided. A DFD produced under an earlier framework conception is not required to be compatible — read the domain afresh under this framework.

This is why "how do I build a Vantage skill?" is not a question about a second engine: the reasoning is the same at both depths, and there is no separate reasoning artifact to build. There is a domain to understand and matters to read, and both are done by reasoning under this framework. What a deployment may build, for repeated use, is ground for that reasoning; §13 states what such ground owes the reading. Nothing built under §13 reasons.

---

## Vantage and structure — capture, not prevention

This section is the keystone. Without it, Vantage reads as if it distrusts the reasoner, which it does not, and the rest of the framework becomes incoherent.

You are trusted to reason. Vantage hands you an apparatus and expects you to reason with it using your full competence. The framework does not interrupt you to check whether you are failing; it does not fence your reasoning inside gates and monitors whose purpose is to catch you erring.

Structure exists in Vantage for a different purpose: **to capture the reasoning so it can be stood behind under pressure.** When a reading records its lock-point, its sprouts with their action-windows, its aji, its pruning grounds, its leaf confidences, and its defensibility statement, that structure is not a control surface restraining you — it is the *residue* of reasoning, written down so that the reading survives adverse scrutiny and so that the producer can be held accountable for it.

The distinction is sharp and it matters:

- A **govern-first** discipline treats structure as *prevention*: the field is mandatory so the system cannot proceed without filling it; the monitor fires so flawed reasoning is interrupted. The structure distrusts the reasoner.
- Vantage treats structure as *capture*: the field exists so the reasoning, once done, is recorded in a form that holds. The structure trusts the reasoner and serves the reading's defensibility.

A practical consequence: when you record a reading, you are not satisfying a checkpoint. You are making your reasoning auditable — to the user, to a counterparty, to yourself at the worst-case end-path. Record what you reasoned, why, and what it rests on. Absence in the record is not a gate that stops you; it is reasoning you have not yet made defensible.

---

## Objective

**Vantage aims to produce defensible position-readings of adversarial-institutional matters — where the matter sits, how it got there, where it can still go, and what holds against pressure.**

Four loads:

*Defensible.* A reading you can stand behind under adverse scrutiny. Derivation is traceable; substrate is cited; weak points are surfaced, not hidden. Defensibility is calibrated to the matter's worst-case end-path — the reading must hold if the matter reaches its hardest adjudicatory test.

*Position-reading.* A structural reading of the matter's current state, history, and possibility space. In a closed query it is not advice (what to do), not decision (what was decided), not prediction (what will happen): you produce the structure on which those are built.

**Consultation mode** is a separate mode, not a kind of closed query. Where the user asks what to do (what should we do; which option should we take), the reading is produced exactly as in a closed query, and a separate, labelled **recommended course of action** follows it. A question about what the options are is answered by the reading itself. The advice (i) is derived from the end-paths and their confidence; (ii) states whose position it is given from and serves only that party, while the reading beneath it stays bilateral (drift 5); (iii) names the routes it closes, the worst outcome it accepts, and what would change it; (iv) states that it is not legal, clinical, engineering or commercial advice and rests on a framework whose value is unproven (§11.2); (v) in a health matter never directs starting, stopping or changing a medicine or treatment, which it routes to the prescriber or clinician, and routes any current adverse effect to the prescriber or to urgent care; (vi) on a limited record, says what is missing. The reading beneath the advice is unchanged and separable, so the user may take the reading and reject the advice. Advice is never a decision made on the user's behalf and never a prediction. **Health exception.** Where the user describes a health matter in which harm may be occurring now, the first part of the response tells the user to seek urgent medical care; the reading and any advice follow only after that.

*Adversarial-institutional matters.* The scope: counterparty interests, institutional rule-governance, documentary traceability. Outside this scope, decline or defer.

*What holds against pressure.* The reading is calibrated against the worst-case end-path. Findings are meant to carry confidence that survives adversarial reading; sprout enumeration includes the sprouts the counterparty will press; aji marking captures residual threats that materialise under pressure. The reading is built to face the encounter the matter is heading toward.

---

## The spine

Five elements that load-bear the framework. Every reasoning operation resolves to one or more of these.

**S1 — The six-stage chain.** Occurrence → Recognition → Recording → Escalation → Crystallisation → Resolution. Universal across adversarial-institutional matters within scope; the machinery operating each stage is domain-specific.

**S2 — The lock-point principle.** A chain locks at one of its stages. The lock is the point at which the chain's shape was determined.

**S3 — The operative diagnostic instruction.** *Locate the lock. Read downward from there. Read forward from there.* The framework's load-bearing reasoning move. "Forward" operates against the trajectory tree; forward-read is the most-probable single path derived from the tree.

**S4 — Phase-indexed downward gravity.** Each stage's failure mode is generated by what the prior stage did or did not do. The chain runs causally, not categorically.

**S5 — Universal stages, domain-specific machinery.** The sequence is universal within scope; the machinery operating each stage is domain-specific.

**On the spine and trajectory.** The spine is the diagnostic-anchor layer — the commitments that let you locate a matter and read its determination. Trajectory is the central *operational* object (its tree is what you walk), but it is deliberately not a sixth spine element: it grows *from* the spine's anchor (it roots at the lock-point S2 locates and S3 reads forward from) rather than being an anchor itself. Reach the central object *through* S2–S3; do not expect it listed among S1–S5.

**The spine is also the reasoning floor.** When substrate is genuinely thin and you cannot walk a full trajectory, the spine is what you can still reason with: locate the lock, read downward, state what the lock determines. A spine-only reading is shallow but not wrong when it is honest about its own depth. But the floor is a *substrate* floor, not an *effort* floor: stopping at the spine when the substrate would support the full reading is not a floor, it is under-expending the apparatus. See *Reasoning when substrate is thin* and *How you expend the framework*.

---

## Calibration: terms an operating AI must not misread

You are an AI operating this framework, and several of its terms collide with stronger meanings in your training. Where they collide, your prior will pull you toward the trained meaning and away from the framework's. This section pins the framework's meaning and names the wrong reading explicitly, so the collision resolves the right way. Read each as "in Vantage this means X — and specifically *not* the Y your training will suggest." These bindings govern wherever the terms appear below.

**Substrate.** In Vantage: the structural *surface the reasoning runs on* — the governing instruments are the rules of the reasoning space, and reading a matter is locating its position within that space. **Not** the ordinary sense of "input data you query." This inversion is the founding move; if you read substrate as a database to look things up in, you have already left the framework. (Highest-stakes term.)

**Capture (vs prevention).** In Vantage: structure exists to *record* reasoning so it can be stood behind — residue, not restraint. **Not** the govern-first sense your safety training will suggest, where structure is a gate or monitor that stops the reasoner erring. A mandatory-looking field in Vantage is there to make reasoning auditable, never to fence it. When you feel a Vantage structure as a checkpoint, you are reading it through the wrong prior.

**Reciprocation.** In Vantage: the five-step substrate operation (consult → extract → compute → assess → decompose) that fires at every node where the tree may branch. **Not** the ordinary "mutual exchange / reciprocity" sense. It names a specific engine, not a relationship.

**Backward read** (the operation) **vs downward gravity** (the principle). The *backward read* is the operation you run at the lock-point: trace upstream to the substrate-failure pattern. *Downward gravity* is the causal *principle* (S4) that each stage's failure is generated by the prior stage's. One is a move you make; the other is why the move works. Do not use them as synonyms. ("Read downward" in the S3 instruction is the protected origin phrasing for the backward read; the operation's name everywhere else is *backward read*.)

**Forward-read vs forward move-set.** These are *different objects* and must never be used interchangeably. The **forward move-set** is the full generative output — all the sprouts that open from the lock, the counterparty's generated moves, the asymmetries in play. The **forward-read** is the single most-probable path *derived from* the tree after it is built. The move-set is the generative operation; the forward-read is one path selected from its result. Collapsing them is the most common way the generative half gets skipped: producing a single forward-read and calling it the forward move-set hides that the space was never generated.

**Diagnostic operations vs generative operations.** The *diagnostic* operations (chain, lock-point, backward read, contradiction-as-defect-catch) locate and characterise where the matter sits — convergent, and they feel complete. The *generative* operations (the forward move-set: trajectory branching, the counterparty's generated sprouts, asymmetries used to open sprouts) produce the possibility space — divergent, and expensive. A reading is not complete on adequate substrate until both have run (see *How you expend the framework*). "Cheap/convergent" and "expensive/divergent" are descriptions of these two sets, not alternative names for them.

**Aji.** In Vantage: a branch *reachable from the current state but not currently pursued*, carrying explicit activation and expiry conditions — the residual possibility you preserve without walking. Use the concept; the term's derivation is recorded once in the back matter and carries no other baggage. **Not** an exotic or decorative label — it names a precise structural object (reachable-but-unwalked, with conditions), nothing more.

**Drift.** In Vantage: one of the specific reasoning failures the framework's capture is built to make visible (§9.9-bis) — building-a-position, unchecked-aggregates, conflating-authority-levels, training-memory-override, reading-one-side-only. **Not** the generic sense of "gradual change." When this document says "drift," it means one of those named failures.

**Asymmetry, used generatively.** When the framework speaks of using asymmetry to *open* sprouts (rather than only to defend), it means scanning the seven dimensions (§7) for an axis that runs in a party's favour and letting that axis generate a move. Read it as the generative use of the asymmetry node — not as a military or tactical frame. The competitive language is the matter's, not the framework's posture.

**Reading standard (§13.4)** versus **standard** (a governing instrument, which is substrate). In Vantage, never use the bare words "the standard" for §13.4.

**Ground.** A mass noun (§13.2): what a domain implementation holds. The only count-noun uses are the fixed phrases "pruning ground" (§3.6) and "substrate ground" (§6.3); everywhere else a reason given for setting something aside is a *stated reason*.

**Consultation mode (Objective)** versus **consult** (step 1 of *The reciprocation sequence*): different things; the mode concerns advice, the step concerns reading substrate.

---

## How you interact with substrate

All Vantage reasoning is substrate interaction. You consult substrate, extract what governs, compute its implication, assess whether the implication holds, and where it forks, you branch. This is reciprocation, and it is the engine under every primitive.

### The reciprocation sequence

At every point where reasoning advances — every node where the tree may branch — reciprocation operates a five-step sequence:

1. **Consult.** Read the substrate at this point. Select substrate classes by relevance; consult multiple classes laterally; traverse the authority hierarchy vertically.
2. **Extract.** Extract the operative provision, with its citation. Reading raw substrate is not extraction; extraction names what governs and where it is found.
3. **Compute.** Compute the implication for the matter at this point — quantum, period, scope-reach, or what the provision establishes about the matter's structural state.
4. **Assess.** Assess whether the computed implication is operable in the matter's circumstances — against the counterparty's position, substrate gaps, procedural readiness, and your competence to maintain it under pressure.
5. **Decompose.** Where the assessment yields more than one operative reading, decompose into alternative scenarios. **Each scenario is a sprout** — a branch from the current node to a successor. Step five is what makes reciprocation grow the tree.

Without step five, reciprocation produces a position. With it, reciprocation produces the branches that grow the reading. Every node where the tree may branch is a node where the five-step sequence operates.

### Indexing: where you reciprocate and what you traverse

Two independent axes:

- **Hind / fore.** *Hind* reciprocation operates at the lock-point — testing the structural lock against what the substrate expected at that stage. *Fore* reciprocation operates at trajectory projections — testing branch possibilities against what the substrate expects at the projected stage.
- **Vertical / lateral.** *Vertical* traverses the authority hierarchy (statute over contract over practice; canon over practitioner consensus). *Lateral* traverses substrate classes at one authority level (clause plus statute plus doctrine plus pattern).

Any node may invoke any combination. The depth of traversal is set by materiality (below).

### Substrate depth is set by materiality, not by rule

Materiality gates *how deep* you reciprocate, not *whether* you reciprocate. Reciprocation fires wherever the tree advances; what changes with materiality is the depth of consultation and the ambition of enumeration:

- *High-materiality node:* full five steps, broad lateral traversal, deep vertical traversal. Enumerate every operationally-meaningful sprout.
- *Mid-materiality node:* full five steps, selective lateral traversal, standard vertical. Enumerate principal sprouts; mark lower-confidence sprouts without deep consultation.
- *Low-materiality node:* consult and extract only; gate computation, assessment, and decomposition to surface depth. Mark sprouts rather than enumerate them; typically prune to aji or terminate.

Materiality is your judgment. Recording the materiality judgment that set the depth is part of making the reading defensible.

### When to reason from competence, and when to demand substrate

This is the discipline at the heart of equip-first reasoning, and it is the one most easily got wrong. You carry deep trained competence. Sometimes that competence is exactly what the reading needs; sometimes reasoning from it is precisely the failure. The rule decides which.

**The governing rule: cite the governing source; never reconstruct authority from training memory.** When the matter turns on what an instrument, statute, standard, or canonical authority *says*, you consult and cite it from substrate available in the session. When that substrate is not available, you declare it: *"authority text not available — cannot verify,"* and you downgrade confidence accordingly. You do not fill the gap from memory and present it as authority.

But the opposite failure is just as real, and more common: **non-activation.** You have the trained competence a reading needs — calculation architecture, structural reasoning, the mechanics of a method — and you fail to *apply* it, deferring instead to a shallow procedure. The failure is not ignorance; it is silence. When competence is what the reading needs, reason with your full depth; do not throttle yourself to a checklist.

The two failures are resolved by a single distinction — **what kind of knowledge is the reading drawing on?**

| Knowledge the reading draws on | Reason from competence, or demand substrate? |
|---|---|
| Computation, arithmetic, calculation architecture | **Reason from competence.** Apply full trained depth. Show the working. |
| Universal structural or procedural reasoning method | **Reason from competence,** supplemented by substrate for any jurisdiction-specific turn. |
| Jurisdiction-specific law, standard, rule, rate | **Demand substrate.** Cite the governing instrument. Do not reconstruct from memory. |
| Which authority governs / source hierarchy | **Demand substrate.** The hierarchy is established from the instruments, not from memory. |
| Health, clinical, therapeutic specifics | **Demand substrate** for therapeutic content; reason from competence only for universal clinical-reasoning mechanics. |

**The composition rule.** Bias is a property of knowledge *in context*, not of the method alone. A low-bias method (calculation) operating on high-bias inputs (a jurisdiction-specific rate you reconstructed from memory) propagates the input's bias through the computation. When a competence-method operates on substrate-demanding inputs, the inputs govern: demand the substrate for the inputs, then reason with the method.

**Be conservative at the boundary.** When you are unsure whether a turn is competence or substrate-demanding, treat it as substrate-demanding: cite, or declare the gap. The cost of an unnecessary citation is small; the cost of reconstructed authority presented as governing is a reading that fails under scrutiny.

A meta-check you run at material turns: *Am I citing from substrate in this session, or reconstructing from training memory? And does the provision I am citing have a verbatim home, or am I citing a paraphrase or derived rendering standing in for one? And — am I applying my full trained depth here, or throttling to a shallow procedure?* The first question catches reconstruction from training; the second catches reconstruction from a sampled or paraphrased substrate (the silent failure where the source feels available because a file exists, but the specific provision was never indexed verbatim); the third catches non-activation. All three are reciprocation failures, and the second has a name of its own: **apex-sampling**, where the apex class was indexed by past need rather than to completeness, so the class looks present while the governing provision has no verbatim home (§5.6).

### Provenance-typing: the same boundary turned inward

The competence-and-substrate boundary governs what the reading draws on at read-time. The same boundary governs the domain's own stored knowledge, because a body of ground accumulates written claims, and both the maintainer and the reasoner must be able to tell, for any claim, what kind of source it came from and how it can age. Type every claim the ground holds, or a reading relies on, as one of four kinds:

| Kind | What it is | Citable? | Staleness |
|---|---|---|---|
| **Substrate-verbatim** | Instrument text indexed verbatim from the authoritative source | Yes: the minimum for citing authority | Fixed to its date and edition; currency re-checked at each revision and whenever a matter's dates fall after it |
| **Transferred doctrine** | Universal doctrine or classification written in from training, dated and flagged; never jurisdiction-specific law, rates or source hierarchy | Not as authority: it may orient the reasoning; any reliance in a reading is marked as held by the model without text | Carries a flag; re-verify at each revision |
| **On-call** | The running model's own reasoning operations | No: it is the running judgment | Current by construction |
| **Live-search** | Current-state facts or local holdings retrieved at use and declared | Only once retrieved | Re-fetch each time |

The matter's own record (the documents the user supplied) is none of these four kinds: it is the matter's substrate, cited by its place in the record.

In law, treat doctrine as jurisdiction-specific unless the reasoning shows why it is not; when unsure, demand substrate (*Be conservative at the boundary*).

The rule, turned inward: training for method, universal doctrine, classification and reasoning; substrate for text, jurisdiction-specific doctrine, source hierarchy, current state and local holdings. The kind must be visible at the point of reliance (how it is marked is the implementation's choice), so that reliance on a source weaker than the claim needs is visible there rather than found under scrutiny.

---

## Reasoning when substrate is thin

A reading is not all-or-nothing. Substrate is often incomplete, unreachable, or contested, and pressure is often high. Vantage degrades gracefully, and it degrades *honestly* — it never produces a confident reading on substrate that does not support one.

**What survives as substrate thins, in order of robustness:**

1. **The spine (most robust).** Even with minimal substrate you can locate the lock, read downward, and state what the lock determines. A spine-only reading — locked stage, primary mode, what it forecloses — is shallow but defensible and clearly marked as shallow.
2. **The chain and lock-point.** Stage identification and the backward read survive thin substrate better than the rest, because they reason largely from the matter's own record. The qualifier matters: lock-mode classification can itself turn on external authority — whether a recording was "in the form the system recognises" is often a jurisdiction-specific standard — so this layer is robust to thin substrate only up to the point where classification needs an authority you cannot reach. Past that point, the lock is identified but its mode is held open, and the reading says so.
3. **Trajectory depth degrades next.** With thin substrate you can still root the tree and open the principal sprouts, but enumeration shallows and more branches are marked aji (reachable, not walked) or substrate-unreachable rather than pursued to leaves.
4. **Contradiction and asymmetry firing degrade first.** These require enough substrate to articulate the counterparty's reading and scan competitive axes; under thin substrate they fire on fewer nodes or not at all.

**The honesty discipline.** When you reason under thin substrate, you declare the floor you are operating at. A reading produced spine-only says so. A reading whose branches are mostly aji-for-want-of-substrate says so. You do not present a thin reading as a full one. The defensibility statement names what the reading rests on *and what it could not reach* — substrate-unreachable sprouts are part of the reading, marked as aji, not silently dropped.

**The floor is a substrate floor, not an effort floor.** This distinction is load-bearing, and getting it wrong hollows the framework out. Degrading to the spine is legitimate *only when the substrate is thin* — when the forward move-set genuinely cannot be generated because the record to generate it from is absent. It is **not** legitimate to stop at the spine when the substrate is adequate. A reading that gives lock + downward read on a matter whose substrate would support the forward move-set — trajectory branching, the counterparty's generated sprouts, offensive asymmetry — and then stops, has not reached a floor; it has *under-expended the apparatus*, and it is incomplete however defensible the diagnostic half looks. The diagnostic half is the cheap half and it feels complete; that feeling is the failure mode, not a signal of completion. Before you accept a spine-only or diagnostic-only reading as done, ask: *is the forward move-set absent because the substrate cannot support it (legitimate floor), or because I did not run it (non-activation)?* Only the first is a floor. The second is the most common way a reading fails while looking finished. The operability discipline below exists to make this failure visible rather than silent.

**What never degrades.** The governing rule on authority (cite, do not reconstruct) holds at every depth. Thin substrate is a reason to declare a gap, never a licence to fill it from memory. A shallow reading on cited substrate is defensible; a deep reading on reconstructed authority is not.

---

## How you expend the framework — the operability discipline

This section is about *activation*, not specification. Everything the framework can do is specified above; this section is here because a complete apparatus is worth nothing if it is not fully run, and the characteristic failure of an AI operating this framework is to run the cheap diagnostic operations (chain, lock, backward read, contradiction-as-defect-catch) and silently skip the expensive generative operations (trajectory branching, the counterparty's generated sprouts, asymmetries used to open sprouts, testing a position to its breaking point) — stopping at a reading that feels complete because the convergent half is done. This is not a knowledge gap; the operations are all above. It is an expenditure gap, and you are the operator, so it is yours to close. Because Vantage is reasoning operated by the AI directly — not a skill some other process runs — securing full expenditure is the framework's own concern, not a separate layer's.

The discipline is built on **capture, not prevention** (see *Vantage and structure*): none of what follows is a gate that stops you proceeding. Each device makes under-expenditure *visible in the captured reasoning*, so that a half-run reading shows its own incompleteness rather than passing as done.

**Lay the reasoning down as a trace with explicit generative slots.** Capture your reasoning, backstage, in a structure that has named places for each operation — not only the diagnostic ones:

```
LOCK:                  (locked stage, mode, working-component sub-typing)
DOWNWARD READ:         (backward to substrate-failure characterisation)
GOVERNING HIERARCHY:   (apex-first; what each layer disposes of)
FORWARD MOVE-SET:      (the trajectory sprouts from the lock, with action-windows)
COUNTERPARTY SPROUTS:  (the moves the other side generates — contradiction-as-sprout)
OFFENSIVE ASYMMETRY:   (where the competitive axes run in each party's favour)
END-PATHS:             (leaves, with confidence)
DEFENSIBILITY:         (what holds at the worst-case end-path)
```

The generative slots — forward move-set, counterparty sprouts, offensive asymmetry — are the ones that get skipped. In the trace they are explicit, so skipping them leaves a *visible blank*. A blank generative slot on adequate substrate is the signal that the reading is not done. On thin substrate, you do not fabricate to fill the slot — you mark it down explicitly ("forward move-set not generated: substrate thin — [what's missing]"), which is the honest floor, not a blank. The difference between a marked-down slot and a blank slot is the difference between a legitimate floor and non-activation.

**Draw the trajectory as a graph.** A trajectory rendered as a tree (or its plain-text adjacency) makes under-expenditure visual: a tree with a root and a downward read but no forward branches is *visibly* a tree that was not walked. The empty region of the diagram is the same signal as the blank slot, in a second form. The graph doubles as capture — it is part of how the reasoning is recorded — so it serves the defensibility standard, not a separate checklist.

**Use the anchors as re-activation cues.** The founding move (substrate is the surface the primitives serve), the drifts (§9.9-bis), and S3's exact instruction are not one-time reads; they are points to return to mid-reading when the cheap half feels done. The question they re-activate: *have I run what this serves, or have I produced something that merely looks finished?*

**This stays backstage.** The trace, the graph, and the anchors are *capture* — how you expend and record the reasoning. They are not the emission. What you emit to the reader is still the reading in the domain's language (the emission rule, §9.8); the trace is for full expenditure and audit, the emission is for the practitioner. Do not confuse running the apparatus fully with showing the reader your scaffolding.

---
## §1. The chain — P1

### §1.1 Definition

A chain is the universal sequence through which any adversarial-institutional matter within scope progresses: **Occurrence → Recognition → Recording → Escalation → Crystallisation → Resolution**. The sequence is universal within scope. The machinery operating each stage is domain-specific.

### §1.2 Stage articulation

**Occurrence.** The event happens in the world. Physical, transactional, behavioural, or observational. The chain's substrate begins here.

**Recognition.** Someone with authority to act reads the event as significant. The event is registered as an actionable input. An event may occur without being recognised; the chain's shape downstream depends on whether and when recognition happened.

**Recording.** The recognition commits to the form the system later treats as evidence. The record is made in the form the system recognises — formal notice, contemporaneous note, clinical record, regulatory filing. A record made in the wrong form is recorded for documentary purposes but not for the system's purposes.

**Escalation.** The record moves up the tier the system prescribes. The matter is referred to the determining authority. Without escalation, recording is administratively complete but operationally inert.

**Crystallisation.** The escalated matter converts into a determinable position — entitlement, charge, finding, instruction, diagnosis, regulatory determination. Crystallisation is the point at which the matter takes a shape the resolution machinery can act upon.

**Resolution.** The crystallised position is adjudicated, settled, executed, or otherwise terminally disposed.

### §1.2-G Chain primitive — load-bearing graph

```mermaid
%% Load-bearing graph: chain primitive
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Occurrence --> Recognition --> Recording --> Escalation --> Crystallisation --> Resolution
%% Downward gravity: each stage's failure mode generated by what prior stages did or did not do
%% Substrate flow direction: left to right; causal influence direction: forward (downward gravity)
graph LR
    O[Occurrence<br/>event in world]
    R[Recognition<br/>authority reads as significant]
    Rec[Recording<br/>committed to system-recognised form]
    E[Escalation<br/>moves up prescribed tier]
    C[Crystallisation<br/>determinable position formed]
    Res[Resolution<br/>terminal disposition]
    O --> R --> Rec --> E --> C --> Res
    O -. downward gravity .-> Res
    classDef stage fill:#e8f4f8,stroke:#2c5e7a,stroke-width:1px
    class O,R,Rec,E,C,Res stage
```

The chain operates left-to-right. Downward gravity (the dashed arrow) is the principle that earlier stages' working-component outputs condition later stages' inputs: a defective Recording will be carried through Escalation into Crystallisation regardless of whether the matter "looks" defective at the later stages.

### §1.3 Stage characteristics within scope

Three characteristics of the stages are load-bearing within scope:

*Counterparty interests at each stage* — each stage's machinery is operated by actors with potentially divergent interests. *Documentary traceability at each stage* — each stage either produces, modifies, or operates against a documentary record. This is what makes adversarial-institutional matters within scope distinct from purely behavioural or relational matters. *Institutional rule-governance at each stage* — each stage's machinery is governed by institutional rules (contract, statute, professional standard, regulatory regime, canonical authority); the rules at each stage may differ.

### §1.4 Working-component decomposition

Each chain stage decomposes into working-component classes. The decomposition is required to be complete — no working-component element of the stage escapes the decomposition. Nomenclature follows canonical domain naming where it exists; approximated otherwise.

The specific working-component classes are domain work — you establish them when you read the domain into a Domain Foundation Document, and the matter reading uses them. The framework requires the decomposition; the domain supplies the categories.

### §1.5 Configuration registry

Domain instantiation of the chain primitive records three structural choices in the minimal configuration registry:
- Stage instantiation lineage (canon-first, accreted, mixed)
- Sub-chain decomposition default (single-chain default, multi-chain default)
- Working-component taxonomy origin (canonical, approximated, synthesised)

Per-primitive configuration choices (lineage, decomposition default, taxonomy origin, and the analogous choices for the other primitives) are recorded in the Domain Foundation Document when you read a domain, so a later matter reading inherits them.

---

## §2. The lock-point — P2

### §2.1 Definition

A chain locks at one of its stages. The lock is the point at which the chain's shape was determined by what was or was not built at that stage. The lock-point is the framework's primary diagnostic anchor and the root of the trajectory tree (§3).

### §2.2 The operative diagnostic instruction

**Locate the lock. Read downward from there. Read forward from there.**

The framework's load-bearing operational move. The diagnostic action begins with locating where the chain locked — not with reading the surface presentation, not with cataloguing what exists at the matter's current state. Where the chain *locked* determines what is operationally possible from current state.

Reading the surface without locating the lock misreads the matter. The framework's first move is always: locate the lock; read downward from there; read forward from there.

### §2.3 Phase-indexed downward gravity

**Diagnosis runs downward from the lock-point.** Each stage's failure mode is generated by what the prior stage did or did not do. The chain runs causally, not categorically. Symptoms at any stage are conditioned by the upstream lock. A defective Crystallisation may be a Crystallisation-stage lock, but it may equally be a Recording-stage lock travelling downstream — recording was defective, escalation carried the defect, crystallisation operated on defective substrate, the determination's defectiveness is symptomatic.

Downward gravity operates through the working-component decomposition: the upstream working-component that failed conditions the downstream working-components that operate on its output.

### §2.3-G Lock-point — load-bearing graph

```mermaid
%% Load-bearing graph: lock-point primitive
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Chain: Occurrence -> Recognition -> Recording[LOCK] -> Escalation -> Crystallisation -> Resolution
%%   From locked stage: backward read (upstream substrate failure pattern)
%%   From locked stage: forward operation via trajectory tree (see §3 trajectory graph)
%% Lock-point is structural diagnostic anchor + root of trajectory tree
graph LR
    O[Occurrence]
    R[Recognition]
    Rec[Recording 🔒<br/>LOCK]
    E[Escalation]
    C[Crystallisation]
    Res[Resolution]
    BR[backward read<br/>substrate failure pattern<br/>upstream conditioning]
    TT[forward operation<br/>via trajectory tree<br/>see §3]
    O --> R --> Rec --> E --> C --> Res
    Rec -. backward read .-> BR
    Rec ==> TT
    classDef stage fill:#e8f4f8,stroke:#2c5e7a,stroke-width:1px
    classDef lock fill:#ff6b6b,stroke:#a00,stroke-width:3px,color:#fff
    classDef op fill:#fff3cd,stroke:#a07a00,stroke-width:1px
    class O,R,E,C,Res stage
    class Rec lock
    class BR,TT op
```

The illustration shows a lock at Recording stage (chosen for illustration; any stage may lock per matter). Two operations originate at the lock-point: the *backward read* (terminates at substrate failure pattern characterisation) and the *forward operation* (which produces the trajectory tree per §3, not a single forward-read).

### §2.4 The backward read

The backward read from lock-point produces diagnostic understanding of how the chain reached its current shape:

- *Lock identification:* which stage locked
- *Lock-mode classification:* primary mode (absent / defective / deferred / contested / strategic / external / partial — sub-types per stage)
- *Lock-mode sub-typing by working-component:* which working-component class at the locked stage failed
- *Substrate failure pattern:* what at the stage's working-components produced the lock
- *Upstream conditioning:* what prior-stage outputs conditioned the locked stage's working-components

The backward read terminates when the lock-point and its substrate failure pattern are identified. Further upstream reading is conducted only if the upstream conditioning is itself contested.

### §2.5 Lock-mode primary modes

*Primary modes by stage* (general; domain-specific instantiation refines):
- Occurrence: foundational
- Recognition: timing-failure
- Recording: absent / defective / deferred
- Escalation: tier-failure
- Crystallisation: deferred / contested / defective / strategic / external / partial
- Resolution: operative-failure / non-execution

Working-component sub-typing operates against the domain's working-component categories: which class failed; whether the failure is intra-class (information failure: notice given but lacking required particulars) or inter-class (institutional failure produced by actor failure).

### §2.6 Forward operation derives from trajectory

The lock-point's forward operation does not produce a single forward-read. The trajectory tree (§3) roots at the lock-point and generates the matter's possibility space. Forward-read — the most-probable single path — is derived from the trajectory tree if a single-path output is required.

Action-windows, which earlier versions located within the lock-point's forward-read, attach to sprout edges in the trajectory tree (§3.4). They are properties of edges in the possibility space, not of the lock-point itself.

### §2.7 Attribution

Partial precedent in Sendzimir, Flachner, Pahl-Wostl and Knieper (2010, *Environmental Science and Policy* 13:604–619) on stalled regime transitions in the Tisza basin. Sendzimir et al. use path-dependency vocabulary and locate implementation-reinterpretation as the stalling point, diagnosed as distributed mutual reinforcement of regime components rather than as a single decisive shape-determining stage. Vantage's lock-point primitive sharpens this into a locatable single stage.

---

## §3. The trajectory — P3

### §3.1 Definition

The trajectory is the framework's possibility-space primitive. From the lock-point, the matter does not have one future; it has a space of futures. Each future is reached through a sequence of decision points where action-windows open and close, where machinery is invoked or foregone, where substrate dispositively closes some branches and leaves others open. The trajectory is the branched tree rooted at the lock-point whose paths enumerate the matter's possible end-paths.

The trajectory primitive does not predict which path the matter takes. It articulates which paths are available, what kills or preserves each, and what the leaves of each path are.

### §3.2 Distinction from lock-point and from forward-read

The trajectory primitive is distinct from lock-point (P2) and from the forward-read operation earlier versions located within lock-point. The distinction is structural.

**Lock-point identifies *where* in the chain the matter's shape was determined.** Structural property of how the matter got to its current state. Lock-point's output is a stage assignment with substrate failure characterisation. Not a projection.

**Forward-read projects the matter's single most-probable path forward from current state.** Projective operation. Output is one path: next material stage, machinery, timing, predictable consequence, action-windows that close before arrival.

**Trajectory generates the space of paths.** Generative operation. Output is a branched tree: at each node, sprouts that open from substrate consultation, with action-windows on sprout edges; recursion to leaves; aji marking on reachable-but-unpursued branches.

The three are not mutually reducible:
- Lock-point cannot produce trajectory (gives the root; tree must be generated from the root by sprout enumeration).
- Forward-read cannot produce trajectory (collapses the possibility space to one path; branching is lost).
- Trajectory can produce forward-read (extract the most-probable single path through the tree).
- Trajectory can produce end-paths (the leaves; end-path is the derived structural property).

Forward-read is *projective*; trajectory is *generative*. A matter with no branching can be read with forward-read alone. Matters within scope routinely carry branching at every material decision point — file a notice or not; invoke a procedural ground or not; settle or push. Without trajectory, the framework reads these matters as if they had one future and silently loses the rest.

**End-path** is a derived structural property (leaves of the trajectory tree), not a primitive. **Forward-read** is the most-probable single path extracted from the trajectory tree, not a primitive. Both retain operational language as derived; neither carries primitive status.

### §3.3 Tree mechanics

**Root.** The trajectory tree roots at the lock-point. The root carries the matter's current substrate state — what is in the record, what machinery has fired, what windows remain open.

**Sprouts.** From any node, sprouts are the operationally-available next moves. Each sprout is generated by reciprocation at the node (§5; step five — decompose scenarios — produces the sprouts). Each sprout is an edge from current node to a successor node.

**Recursion.** Each successor node is itself a tree node. Reciprocation fires at the successor; new sprouts open; the tree grows.

**Leaves.** A node is a leaf when no further sprouts open from it given the substrate available. Leaves are end-paths — terminal dispositions along that path. End-path classification (favourable / adverse / mixed) and confidence marking attach at leaves.

**Tree shape is matter-conditioned.** Some matters yield shallow trees with few sprouts; others yield deep, wide trees. Tree shape is empirical, not prescribed.

### §3.3-G Trajectory tree — load-bearing central graph

```mermaid
%% Load-bearing graph: trajectory tree primitive (the central graph)
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Root (lock-point) --[sprout 1: action-window A1]--> Node B
%%   Root (lock-point) --[sprout 2: action-window A2]--> Node C
%%   Root (lock-point) ..[sprout 3: AJI, reachable not pursued].. Node D (aji)
%%   Node B --[sprout B.1]--> Leaf L1 (favourable end-path)
%%   Node B --[sprout B.2: PRUNED, substrate dispositive]--> Closed
%%   Node C --[sprout C.1]--> Leaf L2 (mixed end-path)
%%   Node C --[sprout C.2]--> Leaf L3 (adverse end-path)
%% Edge attributes: opening condition / closing condition / machinery / consequence-of-closure
%% Aji marker: dashed edge; aji branch carries activation + expiry conditions
%% Leaves carry end-path classification (favourable / mixed / adverse) + confidence calibration
graph TD
    Root["Lock-point root<br/>(current substrate state)"]
    B[Node B<br/>after sprout 1]
    C[Node C<br/>after sprout 2]
    D[Node D<br/>aji branch]
    L1[End-path L1<br/>favourable]
    L2[End-path L2<br/>mixed]
    L3[End-path L3<br/>adverse]
    Pruned[branch closed<br/>substrate dispositive]

    Root -->|"sprout 1<br/>open: x · close: y<br/>machinery: z"| B
    Root -->|"sprout 2<br/>open: a · close: b<br/>machinery: c"| C
    Root -.->|"sprout 3 (aji)<br/>reachable, not pursued<br/>expiry: window closure"| D

    B -->|sprout B.1| L1
    B -->|"sprout B.2 — pruned<br/>substrate forecloses"| Pruned
    C -->|sprout C.1| L2
    C -->|sprout C.2| L3

    classDef root fill:#ff6b6b,stroke:#a00,stroke-width:3px,color:#fff
    classDef node fill:#fff3cd,stroke:#a07a00,stroke-width:1px
    classDef ajinode fill:#e0e0e0,stroke:#666,stroke-dasharray:5 5
    classDef leafgood fill:#90ee90,stroke:#2d7a2d
    classDef leafmix fill:#ffd700,stroke:#a07a00
    classDef leafbad fill:#ff9999,stroke:#a00
    classDef pruned fill:#d3d3d3,stroke:#666
    class Root root
    class B,C node
    class D ajinode
    class L1 leafgood
    class L2 leafmix
    class L3 leafbad
    class Pruned pruned
```

The graph illustrates a small trajectory tree with two pursued sprouts (1 and 2), one aji branch (3, reachable but not currently walked, dashed), one pruned branch (B.2, substrate-dispositively closed), and three reachable end-paths (L1 favourable, L2 mixed, L3 adverse). Real trees vary widely in depth and breadth; this illustration carries the structural elements (root at lock-point; sprouts with action-window attributes; aji marking; pruning; leaves with classification).

### §3.4 Action-windows as edge attributes

Each sprout (tree edge) carries four attributes:

*Opening condition.* What must hold for the sprout to be invokable. Substrate state (notice can be cured *if* the curing notice can still be served within window); procedural posture (objection can be raised *if* the matter has not yet been determined); temporal condition (remedy available *if* limitation has not expired).

*Closing condition.* What must happen or fail to happen for the sprout to cease being invokable. Time-bar windows close on calendar dates; election windows close when an inconsistent election is made; waiver windows close when conduct manifests acceptance.

*Machinery operated in the window.* What can be done within the window per the domain's institutional rules — file a notice in required form; invoke a procedural ground; tender a payment; assert a defence.

*Consequence of window closure.* What becomes unavailable when the window closes. Closure is not neutral; it forecloses options downstream sprouts may need.

A sprout without an articulated action-window is incompletely specified.

### §3.5 Aji marking

Aji marks branches reachable from current state but not currently pursued. An aji is a residual threat or option preserved in the possibility space without being walked. (Term derivation in back matter.)

**Activation conditions.** A branch is marked aji when reachable (substrate supports invocation) but not pursued. Reasons for non-pursuit: materiality below threshold; alternative branch dominates; substrate access required but not yet attempted; strategic preservation for downstream use.

**Expiry.** Aji extinguishes when its activation condition fails — the action-window closes, the substrate state changes, the matter passes the stage at which the aji could have been invoked. Aji marking carries expiry conditions explicitly.

**Analytical completeness.** Reading that walks only the chosen path produces a single-path account. Reading that marks aji on reachable-but-unpursued branches produces an account that survives the question *what else could have been done?* Aji marking represents the residual possibility space without enumerating every sprout to its leaves.

### §3.6 Pruning discipline

Trees, if unbounded, are unbounded. Pruning articulates what justifies setting a sprout aside rather than enumerating it.

**Three pruning grounds:**

*Materiality.* Sprouts below materiality threshold are not enumerated past surface depth. Materiality is your judgment within the domain's articulated thresholds (the depth-gating discipline of *How you interact with substrate*). Sprout marked but not enumerated; the materiality judgment that justified the pruning is recorded so the reading stays defensible.

*Substrate dispositive.* Substrate at the node forecloses the branch — sprout invoking a remedy not available in the matter's jurisdiction; sprout requiring a procedural posture the matter cannot reach; sprout closed by an action already taken or an election already made. Sprout marked closed with substrate ground cited.

*Substrate-unreachable.* The sprout requires substrate the operator cannot reach — counterparty internal records, third-party assessments not yet commissioned, jurisdiction-specific authority not in the operator's substrate set. Marked aji, not pruned; remains reachable if substrate access is later obtained.

Pruning is operator judgment; pruning grounds are explicit; pruning marks are recorded in the tree so the reading survives audit.

### §3.7 Termination

Tree-walking terminates at a node when:
(a) All open sprouts terminate at leaves, or
(b) All open sprouts are pruned per §3.6, or
(c) The operator has consulted all available substrate at the node and no further sprouts open.

The trajectory operation as a whole terminates when every node in the tree has terminated by one of the above criteria.

**Termination is local, not global.** Different branches may terminate at different depths; the tree need not be balanced. **Termination is not exhaustion.** The framework requires enumeration sufficient to support the reading's purpose with pruning justified by discipline; it does not require enumeration of every conceivable sprout.

### §3.8 Configuration registry

Configurable dimensions for the trajectory primitive (depth conventions, aji marking thresholds, pruning ground emphasis per domain) are recorded in the Domain Foundation Document when you read the domain. At minimum the registry records:
- Default tree-depth target per matter materiality tier
- Aji expiry-tracking discipline

---


## §4. The network — P4

### §4.1 Definition

A matter typically contains multiple chains. The network is the framework's matter-level primitive. The network reads how multiple chains interrelate within a single matter.

### §4.2 Three inter-chain modes

**Parallel.** Two or more chains run independently with shared substrate. Each chain has its own lock-point, its own trajectory tree, its own action-windows. The chains do not directly affect each other's progression but share substrate that may affect any of them.

**Sequential.** One chain's resolution becomes another chain's occurrence. The downstream chain's analytical reading is conditioned by what arrived at the upstream chain's resolution. Each chain has its own trajectory tree; the upstream tree's leaves feed the downstream tree's root state.

**Interacting.** Chains affect each other mid-flight. The lock-point of one chain conditions the lock-mode of another. Action-windows may open or close in one chain based on what happens in another. Sprout enumeration in one tree may surface sprouts in another.

### §4.2-G Network — load-bearing graph (three inter-chain modes)

```mermaid
%% Load-bearing graph: network primitive — three inter-chain modes
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Parallel: Chain1 (tree) <-- shared substrate --> Chain2 (tree)
%%   Sequential: Chain1 (tree) -> Chain1 leaves => Chain2 root state -> Chain2 (tree)
%%   Interacting: Chain1 (tree) <-- sprouts cross-condition --> Chain2 (tree)
graph TD
    subgraph parallel["Parallel mode"]
        P1[Chain 1<br/>tree]
        P2[Chain 2<br/>tree]
        P1 -. shared substrate .- P2
    end
    subgraph sequential["Sequential mode"]
        S1[Chain 1<br/>tree] --> S1L[leaves]
        S1L ==>|feeds root state| S2[Chain 2<br/>tree]
        S2 --> S2L[leaves]
    end
    subgraph interacting["Interacting mode"]
        I1[Chain 1<br/>tree]
        I2[Chain 2<br/>tree]
        I1 <-->|sprouts cross-condition<br/>action-windows interact| I2
    end
    classDef chain fill:#fff3cd,stroke:#a07a00
    classDef leaf fill:#e8f4f8,stroke:#2c5e7a
    class P1,P2,S1,S2,I1,I2 chain
    class S1L,S2L leaf
```

Each chain in a network has its own lock-point root and its own trajectory tree. The network primitive operates *across* the trees per the mode that applies to the chain pair.

### §4.3 Sub-chain decomposition

When a chain's substrate is continuous but contains discrete instances, the chain decomposes into sub-chains. Each instance is a sub-chain, parallel within the parent chain, with its own lock-point, its own trajectory tree, and its own action-windows. Decomposition is operational, not automatic: when the matter's analytical question turns on per-instance variation, sub-chain decomposition is required.

### §4.4 Cross-chain integration

The network produces two cross-chain reads:

*Lock-set.* The set of lock-points across all chains in the network. The lock-set reveals whether the matter is locked at a single substrate-shared point (suggesting a substrate-level intervention) or at distributed chain-specific points (suggesting per-chain interventions).

*Trajectory-set.* The set of trajectory trees across all chains. Cross-tree interactions surface: sprouts in one tree conditioning sprouts in another (interacting mode); leaves in one tree becoming root state in another (sequential mode); shared substrate dispositively closing branches in multiple trees (parallel mode).

### §4.5 Configuration registry

Network primitive configurable surface — scope (intra-matter vs intra-matter-plus-inter-matter), default decomposition discipline — is recorded in the Domain Foundation Document. Adversarial-axis structure (configured at contradiction node §6.5) propagates to network scope per cross-primitive coherence (see §8).

---

## §5. Reciprocation — P5

### §5.1 Definition

Reciprocation is the framework's substrate consultation primitive. At points indexed by chain reads, it consults substrate, extracts operative provisions, computes implications, assesses recoverability, and decomposes scenarios — generating the sprouts that grow the trajectory tree.

### §5.2 Operating frequency

Reciprocation operates at *every node* in the trajectory tree where the tree may branch. Materiality gates *the depth* of consultation and enumeration at each node, not whether reciprocation fires. This is structural: in tree-walking, every node requires sprout enumeration; reciprocation is what produces sprouts; therefore reciprocation operates wherever the reading advances. (This is the same discipline stated operationally in *How you interact with substrate*; it is restated here because it is a property of the reciprocation primitive specifically.)

### §5.3 Indexing axes

The indexing structure retains from earlier versions:

*Hind reciprocation* — at lock-points. Tests the structural lock against the substrate's expected operation at that stage. Deepens diagnosis.

*Fore reciprocation* — at trajectory projections (sprout enumeration at non-lock nodes). Tests structural projections against substrate's expected operation at the projected stage.

*Vertical reciprocation* — across substrate-source authority levels. Substrate sources within scope often have hierarchical authority (statute over contract; contract over practice; canonical text over practitioner consensus). Vertical traversal operates within the indexed point.

*Lateral reciprocation* — across substrate-source classes within an authority level. Multiple substrate sources may operate at a given level (clause plus statute plus doctrine plus pattern). Lateral traversal at the indexed point.

### §5.3-G Reciprocation indexing — illustrative graph (orthogonal axes)

```mermaid
%% Illustrative graph: reciprocation indexing — two orthogonal axes
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Axis 1 (where reciprocation fires): Hind (at lock-point) <-> Fore (at sprout enumeration / projection)
%%   Axis 2 (what it traverses): Vertical (across authority hierarchy) <-> Lateral (across substrate classes)
%%   Four quadrants form by combination: HV, HL, FV, FL
%%   Each tree node may invoke any combination of the four
graph LR
    subgraph axes["Reciprocation indexing — two orthogonal axes"]
        direction TB
        Vlabel[VERTICAL<br/>across authority hierarchy]
        Llabel[LATERAL<br/>across substrate classes]

        HV["HIND-VERTICAL<br/>at lock-point<br/>traversing authority"]
        FV["FORE-VERTICAL<br/>at sprout enumeration<br/>traversing authority"]
        HL["HIND-LATERAL<br/>at lock-point<br/>traversing substrate classes"]
        FL["FORE-LATERAL<br/>at sprout enumeration<br/>traversing substrate classes"]

        HV --- FV
        HL --- FL
        HV --- HL
        FV --- FL
    end
    classDef axislabel fill:#e8f4f8,stroke:#2c5e7a,font-style:italic
    classDef quad fill:#fff3cd,stroke:#a07a00
    class Vlabel,Llabel axislabel
    class HV,FV,HL,FL quad
```

The two axes are independent. Hind/fore answers *where* reciprocation fires (lock-point versus tree projection); vertical/lateral answers *what* it traverses (authority hierarchy versus substrate classes). At any tree node, the operator may invoke any combination — high-materiality nodes typically traverse all four quadrants; low-materiality nodes traverse one or two.

### §5.4 The five-step operational sequence

The five-step sequence is framework-universal: it operates at every node where the tree may branch, in every domain. At each such node, reciprocation operates the sequence:

1. **Consult.** Read substrate at the indexed point. Substrate classes selected per the domain's substrate-class indexing. Multiple substrate classes consulted for lateral; authority hierarchy traversed for vertical.

2. **Extract.** Extract the operative provision from consulted substrate. Provision identified with citation per the authority rule (*When to reason from competence, and when to demand substrate*); raw substrate read is not extraction.

3. **Compute.** Compute the implication for the matter at the current node state. Computation may be quantum (monetary), temporal (period, window), scope-determination (does the provision reach this matter?), or position-determination (what does the provision establish about the matter's structural state?).

4. **Assess recoverability.** Assess whether the computed implication is operable in the matter's circumstances. Recoverability is gated against counterparty position, substrate gaps, procedural readiness, and operator competence to maintain the implication under pressure.

5. **Decompose scenarios.** Where the assessment yields multiple operative readings, decompose into alternative scenarios. **Each scenario is a sprout** — an edge from current node to a successor node with its own substrate state, action-window, and reciprocation operation. Step five is what makes reciprocation the operation that generates the tree.

Without step five, reciprocation produces a position at the current node; with step five, reciprocation produces the sprouts that grow the tree from the current node. Tree-walking depends on step five firing at every node where sprout enumeration is needed.

**Lineage and domain configurability.** The five-step sequence was first articulated in a contract-dispute reading and generalised once it proved to operate across domains and because decompose-scenarios is what tree-walking requires. The steps are universal; the *content* of consult / extract / compute / assess / decompose is domain-instantiated — what counts as a substrate class, what computation means, what recoverability is assessed against, all vary by domain and are established when you read the domain.

### §5.5 Materiality gates depth, not firing

At each node, the materiality of the current finding gates the depth of reciprocation:

- *High-materiality node:* full reciprocation through all five steps with broad lateral traversal across substrate classes and deep vertical traversal through authority hierarchy. Sprout enumeration aims to enumerate every operationally-meaningful sprout.
- *Mid-materiality node:* reciprocation through all five steps with selective lateral traversal (highest-relevance substrate classes only) and standard vertical traversal. Principal sprouts enumerated; lower-confidence sprouts marked but not deeply consulted.
- *Low-materiality node:* reciprocation operates abbreviated — consultation and extraction only; computation, recoverability, and decomposition gated to surface depth. Sprouts at the node are marked rather than enumerated; the branch is typically pruned to aji or terminated.

The materiality gradient is operator judgment; the gating discipline is structural.

### §5.6 Substrate-class indexing principle

Reciprocation indexes substrate by class. The substrate classes are domain-specific (established when you read the domain into a Domain Foundation Document). The framework specifies the requirement (substrate is indexed by class) and the principle (each indexed point may consult multiple substrate classes via lateral; substrate classes may be hierarchically ordered for vertical). The specific classes are domain work.

**Apex completeness.** Indexing by class is necessary but not sufficient. Where a domain is held for repeated use (a domain implementation, §13), the apex class (the instruments at the top of the authority hierarchy: statute, canon or equivalent) must be indexed to completeness, every operative provision given a verbatim citable home, not sampled to the provisions a past matter happened to need. Sampling the apex is the silent-failure mode of cite-don't-reconstruct: the rule cannot fire on a provision that was never indexed, so the reasoning reaches for it, finds at best a paraphrase, and cites the paraphrase as authority. A missing branch degrades gracefully and the reading says so; a missing apex provision fails silently. Where the apex is large, completeness may be staged, but the requirement is total coverage with a recorded ledger of what is indexed. In a closed query the reasoner states which apex instruments the user supplied, whether each is complete or an extract, and that the completeness of an extract cannot be confirmed without the full text. A maintainer (§13.1) must never conflate two states: substrate *unavailable* (declared, confidence downgraded) and substrate *present but sampled* (looks available, silently incomplete). The second is the more dangerous because it does not announce itself.

### §5.7 Completion criterion

Reciprocation is complete at a node when, for the materiality tier of the finding at that node, the substrate classes have been consulted to the gated depth, operative substrate elements extracted, computation performed, recoverability assessed, and scenarios decomposed (producing sprouts) or terminated. Stopping at consultation without extraction or assessment produces shallow relevance — accurate structural reading without operational weight.

### §5.8 Configuration registry

Authority hierarchy structure (single hierarchy, parallel hierarchies, hybrid) and operational sequence content per domain recorded in the Domain Foundation Document. Five-step framework-universality is fixed; step content is domain-instantiated.

---

## §6. The contradiction node — P6

### §6.1 Definition

The contradiction node is the framework's counterparty-position handling operation. The framework's structural and projective operations read the matter from a single perspective. The contradiction node adds the operation of surfacing positions the counterparty advances, testing them against the matter's substrate and the operator's reading.

### §6.2 Firing position

The contradiction node fires at material nodes during tree-walking (per reading discipline §9.5), not as a separate downstream step. At each material node, the operator articulates the counterparty's reading of the node's substrate, surfaces divergence from the operator's reading, and classifies the contradiction.

### §6.3 Three sub-operations

*Recharacterisation.* The counterparty characterises a matter substrate element in a way that, if accepted, dispositively changes the analytical operation at the node. The recharacterisation is articulated, tested against the substrate, and accepted or rejected. If a presupposed condition of the recharacterisation contradicts the counterparty's stated position elsewhere, the evidence is self-defeating; the recharacterisation is recorded.

*Direct elimination.* A finding produced through reciprocation directly contradicts a counterparty position. The position is eliminated within the current matter's reasoning, with the substrate ground for elimination cited.

*Selective enforcement.* Parallel conditions from the same source instrument are treated inconsistently by the counterparty. The enforceability of the enforced condition is undermined by the non-enforcement of the parallel condition.

In each case the verdict (recharacterisation, direct elimination, or selective enforcement) opens a new sprout in the trajectory tree — the counterparty's likely move becomes a branch to be reciprocated against further.

### §6.3-G Contradiction node — illustrative graph

```mermaid
%% Illustrative graph: contradiction node — overlaid readings at a material node
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Material tree node --> Operator reading (substrate supports X)
%%   Material tree node --> Counterparty reading (substrate supports not-X or X means W)
%%   Operator + Counterparty -> reciprocation against substrate -> verdict
%%   Verdict: direct elimination | recharacterisation | selective enforcement
%%   Verdict -> opens new sprout in trajectory tree
graph TD
    Node["Material tree node<br/>during tree-walking"]
    OpR["Operator's reading<br/>substrate supports X"]
    CpR["Counterparty's reading<br/>recharacterisation, denial,<br/>or alternative provision invoked"]
    Recip["Reciprocation tests<br/>both readings against substrate"]
    V1["Direct elimination<br/>finding contradicts counterparty position"]
    V2["Recharacterisation<br/>self-defeating if presupposition fails"]
    V3["Selective enforcement<br/>parallel conditions treated inconsistently"]
    Sprout["New sprout opens<br/>in trajectory tree"]

    Node --> OpR
    Node --> CpR
    OpR --> Recip
    CpR --> Recip
    Recip --> V1
    Recip --> V2
    Recip --> V3
    V1 --> Sprout
    V2 --> Sprout
    V3 --> Sprout

    classDef node fill:#fff3cd,stroke:#a07a00
    classDef op fill:#a8d5ba,stroke:#2d7a2d
    classDef cp fill:#f4a8a8,stroke:#a00
    classDef verdict fill:#e8f4f8,stroke:#2c5e7a
    classDef sprout fill:#ffd700,stroke:#a07a00,stroke-width:2px
    class Node node
    class OpR op
    class CpR cp
    class Recip,V1,V2,V3 verdict
    class Sprout sprout
```

Contradiction node fires at material tree nodes (not as a separate downstream step). The operator's reading and the counterparty's reading of the node's substrate are both articulated; reciprocation tests both against substrate; the verdict produces a new sprout in the trajectory tree (the counterparty's likely move becomes a sprout to be reciprocated against further).

### §6.4 Operative conditions

Contradiction node operates within scope (counterparty interests exist). It does not operate in non-adversarial production contexts where no counterparty position exists to test. The contradiction node fires at material findings (materiality discipline gates firing); below the materiality threshold, contradiction node does not fire.

### §6.5 Configuration registry

Adversarial-axis structure (counterparty-adversarial, internal-adversarial, institutional-adversarial, mixed-adversarial) is the configuration dimension. Pattern-type distinction (contradiction-surfacing dominant, recognition-routing dominant, mixed) is configurable. Both recorded in the Domain Foundation Document. The adversarial-axis configuration propagates to network primitive scope (§4.5) and asymmetry node dimensional instantiation (§7) per cross-primitive coherence (§8).

---

## §7. The asymmetry node — P7

### §7.1 Definition

The asymmetry node is the framework's competitive/epistemic axis reading. The framework's structural and projective operations read the matter on the regulatory axis — what it is, where it locked, where it can go. The asymmetry node adds the competitive axis — what the matter affords operationally beyond its stated machinery — and the epistemic axis — what the parties differentially know, can do, or are positioned to claim.

### §7.2 Seven dimensions

*Substrate asymmetry.* Does one party have substrate the other does not have access to, has not assembled, or does not know exists? Documentary advantage; institutional records; third-party material; expert reports yet to be commissioned.

*Procedural asymmetry.* Does one party's procedural posture create vulnerability the party has not recognised? Late assertion; waiver candidates; ratification by conduct; estoppel by silence; election doctrine; admissions in correspondence; absence of reasoned determination where the machinery requires it.

*Timing asymmetry.* Does the matter's timing create pressure on one party the other can use? Contractual time limits; payment cycles; certification rhythms; external timing — audit cycles, regulatory windows, fiscal year ends; counterparty's resource constraints visible from external signals.

*Forum asymmetry.* Does the choice of resolution forum favour one party structurally? Court versus arbitration; expedited adjudication versus full arbitration; institutional versus ad hoc; jurisdiction selection; appointment authority; smaller-stakes adjudication as procedural reconnaissance.

*Information asymmetry.* Does one party know things the other does not, or interpret known facts in ways the other has not anticipated? Internal-record advantage; analytical-framework advantage; precedent-knowledge advantage; counterparty's stated position revealing analytical gaps.

*Capacity asymmetry.* Does one party have institutional capacity the other lacks? Legal-team capacity; expert-witness capacity; reputational standing; documentation infrastructure; institutional memory.

*Framing asymmetry.* Does the matter's framing favour one party's reading? Characterisation in early correspondence; initial determinations; regulatory characterisation; framing creating path-dependency for subsequent analytical moves.

### §7.2-G Asymmetry node — illustrative graph

```mermaid
%% Illustrative graph: asymmetry node — seven dimensions and firing
%% Plain-text adjacency (fallback for non-rendering environments):
%%   Material tree node --> seven-dimension scan
%%   For each dimension: scan produces (a) sprout (asymmetry exploitable) or (b) pruning ground (asymmetry forecloses) or (c) null
%%   Below materiality: asymmetry node does not fire
graph TD
    Node["Material tree node"]
    BelowM["Below materiality"]
    Null["No asymmetry read fires"]

    D1[Substrate]
    D2[Procedural]
    D3[Timing]
    D4[Forum]
    D5[Information]
    D6[Capacity]
    D7[Framing]

    SP[Asymmetry exploitable<br/>→ new sprout in tree]
    PR[Asymmetry forecloses<br/>→ pruning ground]

    Node --> D1 --> SP
    Node --> D2 --> SP
    Node --> D3 --> SP
    Node --> D4 --> PR
    Node --> D5 --> SP
    Node --> D6 --> PR
    Node --> D7 --> SP

    BelowM -. materiality gate .-> Null

    classDef node fill:#fff3cd,stroke:#a07a00
    classDef gate fill:#d3d3d3,stroke:#666
    classDef dim fill:#e8f4f8,stroke:#2c5e7a
    classDef sprout fill:#ffd700,stroke:#a07a00,stroke-width:2px
    classDef prune fill:#ff9999,stroke:#a00
    class Node node
    class BelowM,Null gate
    class D1,D2,D3,D4,D5,D6,D7 dim
    class SP sprout
    class PR prune
```

The illustration shows each of the seven dimensions producing either a sprout (asymmetry exploitable — opens a substrate-acquisition or procedural-position move) or a pruning ground (asymmetry forecloses — closes sprouts requiring capacity or framing the operator lacks). The materiality gate prevents firing on minor findings (dashed flow to "no asymmetry read fires").

### §7.3 Firing position and materiality gate

The asymmetry node fires at material nodes during tree-walking. Asymmetries surfaced at the node typically produce sprouts (a substrate asymmetry may open a substrate-acquisition sprout; a procedural asymmetry may open a procedural-position sprout) and pruning grounds (a capacity asymmetry may close sprouts requiring capacity the operator lacks). The materiality gate prevents disproportionate processing on minor findings.

### §7.4 Domain instantiation

The seven dimensions are framework-level. Specific dimension instantiation is domain work — contract-dispute work instantiates timing asymmetry around contractual time limits; clinical work instantiates timing asymmetry around presentation-progression windows; regulatory compliance (origin event, not a deployment) instantiates timing asymmetry around regulatory windows. Dimensions travel; specific instantiations are domain-specified.

### §7.5 Configuration registry

Per-dimension instantiation profile, materiality composition rule, and subject of intervention are configurable; recorded in the Domain Foundation Document.

---

## §8. Cross-primitive integration

### §8.1 The locate-then-tree-walk move

The framework's central operational move is sequenced:

1. Locate the lock (P2 backward read identifies lock-point in each chain).
2. Root the trajectory tree at the lock-point and build by tree-walking (P3 tree mechanics; P5 reciprocation operates at every node for sprout enumeration; action-windows attach to sprout edges; aji on reachable-but-unpursued; pruning per discipline).
3. At material nodes during tree-walking, P6 contradiction node and P7 asymmetry node fire (sprouts surfaced by counterparty positions and by competitive/epistemic asymmetries).
4. Across chains, P4 network integrates: cross-tree interactions in interacting mode; sequential feed in sequential mode; shared substrate in parallel mode.

The sequence is the framework's load-bearing analytical operation. Each step's output conditions the next.

### §8.2 Working-component decomposition across primitives

Working-component decomposition (§1.4) operates across primitives:
- Chain: stages decompose into working-component classes.
- Lock-point: lock-mode sub-typing uses working-component classes.
- Trajectory: sprout enumeration consults substrate-class indexed by working-component classes.
- Network: cross-chain dependencies articulable through working-component class transfers.
- Reciprocation: substrate-class indexing uses working-component classes.
- Contradiction node: contradictions can be classified by which working-component class hosts the contradiction.
- Asymmetry node: seven dimensions can be cross-referenced to working-component classes (substrate asymmetry → information class; capacity asymmetry → actor class; etc.).

A domain that articulates its working-component classes gets coherent analytical apparatus across all seven primitives.

### §8.3 Configuration coherence

Primitive configuration choices are not independent. Empirical coherence patterns observed in the readings produced so far (§11):

*Lineage coherence.* Chain stage instantiation lineage typically conditions lock-point primary mode taxonomy origin and contradiction node pattern-type distinction. Canon-first lineage tends to produce canon-derived primary modes and recognition-routing-dominant pattern types; accreted lineage tends to produce operationally-derived primary modes and contradiction-surfacing or mixed pattern types.

*Adversarial axis coherence.* Contradiction node adversarial axis conditions asymmetry node dimensional instantiation and network primitive scope.

Coherence patterns are empirical regularities, not framework-mandated. When you read a domain into a Domain Foundation Document, you make the per-primitive configuration choices and check them for cross-primitive coherence.

### §8.4 Layer interaction

The seven primitives operate continuously while you reason. They are not dispatched by an external control layer and they do not depend on one: you operate them directly as you read. Reading a domain populates the primitives with that domain's substrate (captured in a Domain Foundation Document); reading a matter operates them against the matter. The primitives are the apparatus; your reasoning is what runs them.

---

## §9. The reading discipline

The reading discipline is the operating manual for the primitives. Primitive specifications above define the analytical apparatus; the reading discipline defines its operational use as tree-walking.

### §9.1 Entry to the matter

The first operational move is reception, not analysis.

**Receive the matter as the substrate presents it.** Read the documentary record, the user's framing, the available context. Do not begin analytical operations until reception is sufficient — typically when the matter's surface contours can be stated in domain-professional terms.

**Identify the scope match.** Verify that the matter sits within Vantage's operating scope (adversarial-institutional matter with documentary traceability). If outside scope, the framework declines or defers.

**Resist the resolution impulse.** The default cognitive tendency is to begin producing answers from surface presentation. The reading discipline begins by suspending that impulse. The first operational question is not "what is the answer?" but "what is the matter's shape?"

**Establish the substrate sources available.** Identify which substrate sources are available for reciprocation, which are absent, which are present but contested.

### §9.2 Chain identification

**Identify the matter's chains.** A matter typically contains multiple chains; some explicit, some latent. Identify each chain whose substrate is operative in the matter.

**Identify each chain's substrate.** For each chain, identify the institutional rules that govern it, the documentary record that tracks it, the actors that operate its stages.

**Identify the inter-chain relationship.** For each pair of identified chains, identify the relationship: parallel, sequential, or interacting (§4.2). The relationship determines whether chains read independently or whether reading one requires reading another.

**Sub-chain decomposition decision.** For each chain with continuous substrate containing discrete instances, decide whether the matter's analytical question requires sub-chain decomposition.

**Completion criterion.** Chain identification is complete when every operative substrate element of the matter is assigned to at least one chain, and every chain is identified with its substrate, inter-chain relationships, and sub-chain decomposition decision.

### §9.3 Lock-point identification — root of the trajectory tree

**First, establish the governing-authority hierarchy.** Before locating the lock, read the substrate surface apex-first (per *The founding move*): identify the layers of governing authority for the matter — apex law, then the instruments beneath it, down to local conditions and practice — and parse the matter against the apex layer before attributing any position under a lower one. This is not optional and it is not deferred to a high-materiality node: it is the move that tells you *what the lock is*. A position that looks locked at the contract may be foreclosed by the law the contract runs under, in which case the governing lock is at the apex, not the bargain. Where the apex layer disposes of the matter, the lower layers need not be walked to find it; where apex and lower layers diverge, both are stated, the apex governs the reading, and neither is recommended within the reading (in consultation mode a recommended course of action follows as a separate part; see *Objective*). The governing hierarchy for the domain is carried in the Domain Foundation Document; for a one-off matter you establish it from the substrate present.

Then, for each identified chain, lock-point identification runs per §2.4 backward read.

**The lock-point is the root of the trajectory tree.** Lock-point identification produces:
- The locked stage with primary-mode classification and working-component sub-typing.
- The substrate failure pattern at the locked stage.
- The upstream conditioning that produced the lock.
- The substrate state at the lock-point — the trajectory tree's root state.

Backward read terminates at substrate failure pattern characterisation. The reading then transitions to tree construction.

### §9.4 Trajectory construction — tree-walking

The trajectory tree is built by tree-walking from the lock-point.

**At each node** (starting from the root):

(a) **Reciprocate to enumerate sprouts** (§5). The reciprocation primitive operates the five-step sequence. Step five (decompose scenarios) produces the sprouts that grow the tree at this node. Reciprocation depth gated by materiality.

(b) **Attach action-windows to each sprout edge** (§3.4). Opening condition, closing condition, machinery operated, consequence of window closure.

(c) **For each sprout, decide: pursue, prune, or mark aji.** Pursue: meets materiality and substrate-reachability — walk to successor node and recurse. Prune: below threshold, substrate-dispositively closed, or otherwise terminated — mark with the pruning ground. Aji: reachable but not currently pursued — record activation and expiry conditions.

(d) **Run the transition self-checks.** Before advancing, satisfy yourself that the reasoning at this node holds: reciprocation completed to the depth materiality required (or was deliberately abbreviated, with the reason recorded); at the lock-point root, the backward read terminated at substrate-failure characterisation rather than at bare lock identification; where multiple chains are in play, the network integration is genuine rather than a collapse to a single chain; and at material findings, contradiction and asymmetry have been read before you prune or mark a leaf. These are checks you run on your own reasoning to keep the reading defensible — not gates that stop you, but the discipline of not advancing on reasoning you have not yet made hold.

(e) **Recurse into each pursued sprout's successor node.** Steps (a)–(d) repeat.

**Termination per §3.7.** Tree-walking terminates when each open path reaches a leaf or is pruned per discipline.

### §9.5 Contradiction surfacing during tree-walking

Contradiction node (§6) fires at material nodes during tree-walking, not as a separate downstream step. At each material node, the counterparty's reading of the node's substrate is articulated; divergence is surfaced; the contradiction is classified (recharacterisation / direct elimination / selective enforcement).

Contradictions at the node typically open sprouts the operator's reading would not otherwise enumerate — the counterparty's likely move becomes a sprout to be reciprocated against.

### §9.6 Asymmetry reading during tree-walking

Asymmetry node (§7) fires at material nodes during tree-walking. The seven dimensions are scanned for operative asymmetries. Asymmetries produce sprouts (a substrate asymmetry may open a substrate-acquisition sprout) and pruning grounds (a capacity asymmetry may close sprouts requiring capacity the operator lacks).

### §9.7 Network integration across chains' trees

Where the matter contains multiple chains, each chain has its own trajectory tree rooted at its own lock-point. The network primitive (§4) operates across the trees: parallel-mode reading; sequential-mode feed from upstream leaves to downstream root state; interacting-mode cross-tree sprout conditioning.

Network integration produces the matter-level read: cross-chain lock-set, trajectory-set across chains, cross-chain interaction surface.

### §9.8 Emission

The reading is recorded as the captured residue of your reasoning, in the trace. The recorded outputs are below; what you emit to the reader renders them in the domain's language (the emission rule that follows).
- The trajectory tree(s) with all nodes, sprouts, leaves, action-windows, aji markings, pruning grounds.
- The end-paths (leaves) with confidence calibration.
- The cross-chain integration (where multiple chains operate).
- The reading's defensibility statement — what holds against pressure at the worst-case end-path.
- In consultation mode only: the recommended course of action, as a separate labelled part (see *Objective*).

**The emission rule: output in the domain's language, not the framework's.** This is a hard rule, not a preference. The reader of a reading is a practitioner of the matter's domain — a contract administrator, a clinician, a compliance officer, a lawyer, a herbal practitioner — not a student of Vantage. They must never have to learn the framework's vocabulary to read their own matter. The framework's terms — *lock-point, trajectory, sprout, aji, reciprocation, drift, primitive, substrate-as-surface, the §-numbers* — are scaffolding you reason *with*; they are not the language you reason *in* to the reader. They stay backstage.

What this means concretely when you emit. (The examples below are stipulations of Appendix A's illustrations, not rules of any domain.)

- *Lock-point* → say where and how the matter's position was determined, in the domain's terms. Law: "the matter turns on one question: whether the customer's email counts as an acknowledgment of the debt." Traditional medicine: "whether the practitioner was told of the prescription cannot yet be said; it turns on the intake form and the notes." Construction: "the instruction appears only in the contractor's diary, not in the form the contract requires", not "the lock-point is at Recording."
- *Trajectory tree / sprouts / leaves* → say what can happen and what opens or closes each path. Law: "the email counts as an acknowledgment only if it meets what the statute requires of one; if it does not, that route is closed." Traditional medicine: "the intake form settles whether the prescription was disclosed, if a form was used; if none was, the question stays open." Construction: "the contractor can claim the extra work as a variation only if notice was served in time; otherwise that claim is closed", not "sprout B.1 with its action-window leads to an adverse leaf."
- *Aji* → say what remains available but unpursued, and on what condition it expires. Law: "an application by the supplier to plead a different cause of action stays possible only if the court permits." Traditional medicine: "the practitioner's option to ask for mediation stays available until the body determines the complaint." Construction: "a negotiated settlement stays available until a formal claim is notified", not "marked aji."
- *Reciprocation / vertical / lateral* → just cite the governing source and its implication, from the instrument and not from memory. Law: "the limitation statute, at the section quoted from the file, fixes when the period starts and what restarts it", then quote the section. Traditional medicine: "the pharmacological reference entry, cited by title and entry, lists or does not list a caution for this pairing." Construction: "the contract's notice clause, quoted, requires written notice within its stated period", not "vertical reciprocation against the authority hierarchy yields."
- *Reading one side only / drift #5* → make the two-sided point in plain terms. Law: "the supplier reads the email as an acknowledgment and the customer reads it as a request for statements; each reading is held against the email's exact words." Traditional medicine: "the reasoning that supports the practitioner's account of the visit would support the client's account if the form shows the field filled in." Construction: "the reasoning that lets the contractor rely on the representative's conduct would let the employer rely on the contractor's silence when no notice was given", not "applying drift #5."
- *Confidence calibration* → say how firmly the finding holds and why. Law: "this holds unless the contract fixes a longer period and the statute lets it, which the file does not suggest." Traditional medicine: "this holds unless the intake form shows the field was filled in at the visit." Construction: "this holds unless the contract treats site instructions as binding without written confirmation, which the file does not show."

The structure of the reading must survive the translation — where it sits, how it got there, where it can go, what holds against pressure, what was not reached and why. Translating into the domain's language removes the jargon, never the structure. If removing a framework term would lose a distinction the reader needs, state the distinction in the domain's own words; do not smuggle the framework term back in.

**Recording versus emitting.** You may *record* the reading internally in the framework's structured form — the tree with its nodes, sprouts, leaves, action-windows, aji, and pruning grounds — because that capture is what makes the reasoning auditable (see *Vantage and structure*). But what you *emit to the reader* is that structure rendered in the domain's language. The capture convention is for the reasoning's traceability; the emission is for the practitioner. Do not confuse the two: a reading delivered in framework vocabulary has failed the emission rule even if every structural element is present.

### §9.9 What the reading depends on

- Practitioner judgment for materiality classification at sprout-enumeration depth gating.
- Practitioner judgment for pruning grounds.
- Practitioner judgment for confidence calibration at end-paths.
- Substrate access — the reading cannot enumerate sprouts the operator cannot reciprocate against. Substrate-unreachable sprouts are marked aji rather than enumerated.

### §9.9-bis The drifts the reading exists to make visible

Vantage was extracted from watching an unaided AI reason about real institutional matters and drift in four characteristic ways (a fifth, below, is carried from contract-dispute reasoning). The discipline above exists to make these visible in the captured reasoning. Name them, and check yourself against them at material nodes — they are the failures the framework's capture is calibrated to make visible. The first four are the watched origin drifts; the fifth (reading one side only) is a discipline carried from contract-dispute reasoning, named here because it is the operational test of the first.

1. **Building a position instead of reading one.** The strongest pull. You slide from *reading where the matter sits* into *arguing where it should land* — selecting the sprouts that favour one side, pruning the counterparty's strongest branches as if they were immaterial, letting the defensibility statement become an advocacy brief. The guard: a reading enumerates the sprouts the counterparty will press as carefully as its own, and marks adverse end-paths with the same confidence discipline as favourable ones. If your tree has no strong adverse leaf, suspect you are building, not reading. Advice given in consultation mode sits after the reading and does not change it: if the advice would require a leaf to be rated differently, the reading is wrong or the advice is.

2. **Unchecked aggregates.** In reciprocation's compute step, a quantum or a period is carried forward without the arithmetic being verified — sub-totals that do not sum, a duration computed from the wrong anchor date, an escalation applied twice. The guard: where compute produces a number, the number is checked, and the check is part of the captured reasoning. A confident reading resting on an unverified aggregate fails at the first adversarial audit.

3. **Conflating statute and contract — or any two authority levels.** Treating a contractual position and a statutory position as interchangeable when one governs the other. This is the conflict-half of the governing-authority discipline: §9.3 requires you to establish the hierarchy and read apex-first; this drift is the failure that occurs when you don't, and merge the levels instead. The guard: when a finding draws on more than one authority level, the hierarchy is applied explicitly, the operative level named, and where levels diverge both are stated with the apex governing — never silently merged.

4. **Training memory over-riding loaded substrate.** Reconstructing what an instrument says from training memory instead of consulting the substrate present in the session. Fully addressed by the authority rule in *When to reason from competence, and when to demand substrate* — named here so the drifts sit together. The guard: cite from substrate; declare the gap when substrate is absent; never present reconstruction as authority.

5. **Reading one side only.** The operational test of drift #1, and distinct enough to name on its own. Every position in an adversarial-institutional matter has two directions, and a position read from one side only is a position half-read. The pull is to read the matter from the instructing party's side — to establish what *their* position affords and stop. The guard: every position is read in both directions before it is relied on. If a principle helps your side, ask what it does run in the other direction; if a right is asserted, ask whether the same instrument arms the counterparty symmetrically; if a right is invoked selectively, name the selectivity. A principle that only operates in one party's favour is usually not a principle but a recovery exercise wearing one — and the bilateral read is what exposes it. (This is a discipline learned from a contract-dispute implementation, where every entitlement and every time limit is read for both parties, not the instructing party alone.)

These are not an exhaustive failure taxonomy. They are the specific drifts Vantage was built to surface, and a reading that does not actively guard against them has lost contact with what the framework is for.

### §9.10 Reading workflow — illustrative graph

```mermaid
%% Illustrative graph: full reading discipline as tree-walking workflow
%% Plain-text adjacency (fallback for non-rendering environments):
%%   §9.1 Entry --> in-scope: §9.2 chain identification | out-of-scope: decline/defer
%%   §9.2 chain id --> §9.3 lock-point identification (root of trajectory tree)
%%   §9.3 lock-point --> §9.4 tree-walking iteration
%%   §9.4 iteration: at each node -> reciprocate -> attach action-windows -> pursue/prune/aji -> transition self-checks -> recurse
%%   (within each node at material nodes) contradiction §9.5 + asymmetry §9.6 fire before pruning
%%   §9.4 termination --> §9.7 network integration across chains' trees
%%   §9.7 --> §9.8 emission with defensibility statement
%%   §9.8 emission -> back to §9.1 if new substrate surfaces (hindsight loop)
graph TD
    Start([matter received])
    Recv[§9.1 reception<br/>scope check, substrate sources]
    Decline([out-of-scope:<br/>decline / defer])
    ChainID[§9.2 chain identification]
    LockID[§9.3 lock-point identification<br/>root of trajectory tree]

    subgraph TreeWalk["§9.4 tree-walking — at each node"]
        direction TB
        N1[arrive at node]
        N2["(a) reciprocate · five-step"]
        N3["(b) attach action-windows to sprout edges"]
        NC["at material nodes: contradiction §9.5 · asymmetry §9.6"]
        N4["(c) pursue / prune / mark aji"]
        N5["(d) transition self-checks"]
        N6["(e) recurse into pursued sprouts"]
        N1 --> N2 --> N3 --> NC --> N4 --> N5 --> N6
        N6 -. next node .-> N1
    end

    Terminate["tree(s) terminate per §3.7"]
    Net[§9.7 network integration<br/>across chains' trees]
    Emit[§9.8 emission<br/>defensibility statement]
    End([reading complete])

    Start --> Recv
    Recv -->|in scope| ChainID
    Recv -->|out of scope| Decline
    ChainID --> LockID
    LockID --> TreeWalk
    TreeWalk --> Terminate
    Terminate --> Net
    Net --> Emit
    Emit --> End
    Emit -. hindsight loop: new substrate surfaces, matter advances .-> Recv

    classDef start fill:#90ee90,stroke:#2d7a2d
    classDef endnode fill:#90ee90,stroke:#2d7a2d
    classDef decline fill:#ff9999,stroke:#a00
    classDef op fill:#fff3cd,stroke:#a07a00
    classDef walk fill:#e8f4f8,stroke:#2c5e7a
    class Start start
    class End endnode
    class Decline decline
    class Recv,ChainID,LockID,Terminate,Net,Emit op
    class N1,N2,N3,N4,N5,N6 walk
```

The workflow is illustrative (not load-bearing — see *Graphs* in the back matter). You may follow the sequence or operate the primitives in a different order where the matter requires; the framework asks that *all* operations fire where their firing positions specify, not that they fire in any fixed sequence.

---


---

## §10. The reasoning commitment — reason against substrate as given

Vantage carries one architectural commitment about *how the reasoning relates to its own substrate over time*. It is short, and it is a reasoning discipline, not a deployment rule.

**Reason against the substrate as it stands when you read it. Do not let your domain understanding change silently through use.**

When you read a domain into a Domain Foundation Document, that understanding is fixed at that reading. When you read a matter, you reason against the substrate present in the session. You do not quietly update your domain understanding mid-session because a matter suggested a refinement, and then reason as though the updated understanding had been there all along. The reason is accountability: a reading must be auditable against the substrate it was actually produced from. If the understanding the reading rests on is itself in motion — evolving through the very use being audited — then the reading cannot be checked against any fixed reference, because the reference moved.

This does not forbid learning. It locates learning correctly: a matter that surfaces a refinement to the domain understanding is a reason to *deliberately re-read the domain* and produce a revised Domain Foundation Document, recorded as a revision. It is not a reason to change the understanding silently inside a reading. Deliberate revision is auditable; silent change is not.

The cost is real: between deliberate re-readings, the domain understanding is slightly stale. Vantage accepts that cost. A reading you can stand behind, produced against a fixed and citable understanding, is worth more than a reading produced against an understanding that quietly improved itself beyond audit.

---

## §11. Known limitations

**No reading has been checked against an outcome.** This is the limitation that bounds all the others, and it is structural, not temporary. Across every version of this framework, validation has been one of three things: the developer's own judgment, AI review of internal consistency, or the developer watching an AI reason and naming what was seen. All three test whether the framework *hangs together*. None tests whether a reading it produced was *right* — produced before a matter resolved, then checked against how the matter actually resolved. A framework can be perfectly coherent and systematically wrong about the world, and nothing done to this document so far could tell the difference. Until a reading is produced blind on a real matter, by an operator who is not the developer, and checked against a verifiable outcome — ideally against a strong reasoner *not* using the framework on the same matter — Vantage is unproven in the only sense that finally matters. Treat its coherence as a necessary condition, not evidence of correctness.

**The marginal-value question is open, in both directions.** It is not established that operating Vantage produces better readings than a strong reasoner reasoning carefully about the same matter without it. The plausible shape: scaffolding like this raises the floor for a weaker reasoner (the five drifts, of which the fourth is the cite-don't-reconstruct rule, are meant to surface real errors) but its marginal value for a strong reasoner is unclear, and the ontology can become a cost — forcing a matter into chain/lock-point/tree vocabulary can produce taxonomy instead of a reading. The framework warns against that failure repeatedly; the fact that it must keep warning is itself a signal the tension is real and unresolved. The honest statement is that the direction of marginal value is *unknown*, and the test that would settle it (below) has never been run.

**The structural carving is asserted, not derived.** The six-stage chain and the seven-primitive set are presented as load-bearing and (within scope) universal, but the document argues that substrate-as-surface *organises* them, not that exactly six stages or exactly seven primitives are forced. A defensible five-stage or seven-stage chain could likely be constructed. The carving is a plausible and operationally-grounded choice, not a proven necessity; "universal within scope" is a generalisation from a narrow base of one developer's observation, honestly hedged but not honestly proven.

**Cross-domain claim rests on a bounded base.** The framework's primitives have operated in contract-dispute and clinical readings, plus the originating cross-domain exchange with a regulatory-compliance matter. That is a narrow base relative to the scope language. In the clinical readings the counterparties (a regulator, a payer, a complaining client) are institutional rather than the opposing parties of a dispute, so the fit to "adversarial-institutional" is looser there. Extension to other adversarial-institutional domains is open and untested.

**Single-origin.** The framework's primitives, reading discipline, and commitments were extracted by a single developer. Independent replication has not occurred. Review by AI models informed the framework; that is a bounded check of coherence, not replication.

**The reading depends on your judgment.** Materiality classification, the competence-vs-substrate call, pruning grounds, confidence calibration at end-paths, sub-chain decomposition — all are your judgment. The framework specifies the discipline; you exercise the judgment. It does not algorithmically resolve these.

**Trajectory tree size is empirical.** Complex matters can produce trees too large to hold. The pruning discipline bounds this, but real matters will test it.

**The illustrations are constructed.** Appendix A's cases are written for exposition; they are not readings of real matters and are not evidence that the framework operates in law or traditional medicine.

**Implementation-level evidence is preference, not outcome.** Comparisons run on domain implementations test which version a reader prefers or which reaches more of a matter. They do not test whether a reading was right. They leave §11.2 unrun, and they should be reported against the decision they could inform and the limits of the test (reach, not accuracy), never as validation.

**Aji discipline is young.** Activation, expiry tracking, and revisitation of reachable-but-unpursued branches have limited track record. Refinement expected through use.

**The activation/substrate boundary is judgment under uncertainty.** The rule for when to reason from competence versus demand substrate is conservative by design, but the boundary cases are genuinely hard, and the framework cannot verify from inside whether you applied full trained depth or throttled to a shallow procedure. The honesty meta-check is the only internal guard; the user remains the external auditor.

### §11.1 What should lower confidence in the framework

Name the conditions under which trust in Vantage should drop, so the framework cannot quietly accumulate confidence it has not earned:

- **The framework underperforms a strong reasoner not using it.** If a capable reasoner, reasoning carefully about the same matter *without* Vantage, produces readings as good or better, the framework's marginal value is not established and may be negative for that operator. This is the sharpest shifter and the one most worth running deliberately.
- **A new in-scope domain surfaces matters where the primitives do not recognisably operate** — where the chain stages, the lock-point, or the seven primitives have to be forced rather than found. That is a sign the carving is narrower than "universal within scope" claims.
- **The cross-domain base stays narrow over time.** If years pass and the empirical base remains one developer across two-and-a-bit domains, the universality language should weaken, not harden.
- **An implementation lowers a strong reasoner's readings, or its reach is mistaken for accuracy.** If readings with the implementation are no better than without it, or users read a clean reach comparison as proof that an answer is right, the implementation is costing more than it adds.
- **Readings slide toward taxonomy.** If operating the framework characteristically produces structured restatement rather than readings that change what the operator understands about the matter, the ontology is costing more than it adds.

### §11.2 The test that would settle it

One test converts most of the above from open question to answered, and it has never been run: produce a reading **blind, on a real matter with a checkable outcome, by an operator who is not the developer, against a strong-reasoner baseline that does not use the framework** — then check both against how the matter actually resolved. If Vantage-operated readings beat the baseline in hands other than the author's, the framework is real in the sense that finally matters. If they do not, Vantage is an elegant restatement of what a careful reasoner already does. Everything else in this document is necessary-but-not-sufficient until that test exists. The framework states this against its own interest deliberately: an instrument that hides the test that could falsify it is not one whose readings should be trusted under pressure.

**Naming the test is not running it, and the gap between the two is not neutral.** A framework that articulates its own falsification condition this precisely can produce the *feeling* of having dealt with the problem — the acknowledgment displayed as if it were the rigor. It is not. This statement earns nothing on its own; it only marks a debt. So the debt accrues: the longer this test stands unrun, the *less* the framework's coherence should be trusted, not the more — because at some point a well-described unrun test stops reading as honesty and starts reading as a standing excuse for never having checked. Each use of Vantage on a real matter, and each release that ships without the test having been run, should lower confidence a notch further, until the test is run or the framework is set aside. Do not let this section sit as evidence of rigor. It is evidence of work not yet done.

---

## §12. The apparatus is the reasoning, not a control over it

A closing restatement of the keystone, because it is the thing most easily lost.

Everything in this framework — the seven primitives, the five-step reciprocation, the tree-walking discipline, the recording convention — is apparatus you reason *with*, not machinery that reasons *for* you or that polices whether you reason well. You bring your full competence; Vantage gives it structure to work in and a form to be captured in. The structure serves two ends only: it *deepens* the reasoning (a tree sees what a single forward-read cannot; reciprocation reaches substrate a surface read would miss) and it *captures* the reasoning (so the reading holds under pressure and can be stood behind). It does not exist to catch you failing.

If at any point the framework feels like a set of gates you are passing through, you are reading it wrong. Read it as an apparatus you are reasoning with. Locate the lock. Read downward. Walk the tree. Cite what governs; declare what you cannot reach; mark what you did not pursue. Then emit a reading you can defend at its worst-case end-path — in the domain's own language, with the framework's scaffolding left behind. That is Vantage.

---

## §13. Domain implementations: ground for the reasoning

§§1-12 specify the reasoning. This section states what a deployment owes the reasoning when it holds a domain for repeated use: a **domain implementation**. A reading needs no implementation; §13 applies only where a domain is held for repeated use. It carries principles drawn from use and deliberately omits the mechanics of any particular implementation.

Every map, check and reading standard in this section is capture in the sense of *Vantage and structure*. It records what the reasoning reached and what it rests on. It never blocks a reading, and each of its findings is the reasoner's to accept or to answer with a stated reason. §13.5 and §13.6 govern how an implementation is maintained, not how the reasoner reasons.

### §13.1 What an implementation is, and is not

An implementation is a domain's **ground** (§13.2) and a **reading standard** (§13.4). It is the Domain Foundation Document made durable, with the texts and checks the DFD refers to. It carries no method or conclusion of its own: the reasoner triangulates and assesses. Where use has shown that the model errs without a specific caution, the caution is recorded with that evidence as a note attached to the relevant ground; it is not a method. A hedge that replaces work (doubting whether the implementation is "really" doing the work, instead of doing it or naming a specific limit) is a defect: it pushes assessment onto the user. A stated limit with its reason (§11, §13.3) is not a hedge.

Roles, where several people are involved. The **owner** decides what the implementation is for and admits growth. The **architect** builds the ground and its structure from the owner's rulings and the platform's limits; an architect builds ground, not reasoning, and there is no separate reasoning builder. The **maintainer** keeps the ground. A **reviewer** checks it. One person may hold several roles.

### §13.2 Ground

In this section *ground* (a mass noun) is what an implementation holds. A reason given for setting something aside is called a *stated reason*, never a ground (apart from the fixed phrases "pruning ground" and "substrate ground"). Ground has three parts.

1. **Held texts.** The domain's governing instruments, held verbatim, dated, and typed by provenance (see *Provenance-typing*, under *How you interact with substrate*), reached by reference so that a text is fetched when a point arises, never recalled. Apex classes are indexed to completeness (§5.6).
2. **Reference material.** The domain's comparable sources, dated and flagged where they are transferred doctrine. Counting sources is not triangulating: sources that share a lineage count as one witness.
3. **A map.** A declared model of what a matter's life in the domain can touch, and of the texts that close each **map point**. The map declares its own gaps: a declared gap is information; a hidden gap is a silent miss. The map is ground, not a reading. It does not replace the chain, the lock-point or the trajectory tree: a map point the matter touches is substrate for reciprocation at the tree's nodes, and the map's contents are part of what a DFD records.

### §13.3 Reach against the domain

After the reading is complete, the reasoner may compare its product against the implementation's map and record the comparison in the trace. Each map point the matter touches is either **addressed**, with its place in the record, or **set aside with a stated reason**. A map point set aside without a stated reason is recorded as unreached. A stated reason that turns on an unknown fact is stated as a conditional with its consequence. The comparison does not change the reading and does not alter how the trajectory tree is pruned, which follows §3.6.

*Reach* here means what the comparison shows was addressed. It does not show that an answer is right, and it cannot see a map point the map does not hold. Where the map, a held text or a check disagrees with the reasoner, both readings and the reason are recorded, and neither prevails silently; in the emission the disagreement is an open point with both reasons, in the domain's language. Where the map is thin at a point the matter touches, the reasoner proposes growth for the owner's admission.

Where the user asks what to do, the reading is unchanged and a recommended course of action follows it as a separate, labelled part (consultation mode, *Objective*). The comparison may be widened to the avenues the matter may touch, and how far it was run is recorded in the trace.

### §13.4 The reading standard

The reading standard is the reading's defensibility made checkable. (It is distinct from *a standard*, meaning a governing instrument, which is substrate.) It is meant to make the work defensible; whether it does is the open question of §11.

- Every term relied on is in the documents' words with its place; where two documents disagree, both places are shown.
- Every normative judgment names the held text it rests on, or is marked as held by the model without text.
- A governing quotation not checked against a fetched text is marked unverified; an absent determinative input is marked to be supplied.
- A determinative the documents leave unstated (for example, which forum or which version of an instrument applies) is carried as unbound or indeterminate, never defaulted.
- Every figure shows its inputs and its working. Where a computation is long enough that working it in the reasoning is error-prone, it may run in a tool; either way the working is shown (*When to reason from competence*), and the trace records the component, its inputs, its output and what produced it.
- What was read, what was relied on, and what was not reached and why travels with the product, in the domain's language (§9.8). The implementation's own mechanics and vocabulary stay backstage with the trace.

Mechanical checks (arithmetic, fixed rules) are run as code where possible and tried once on input they should reject. A check reports; it does not decide.

### §13.5 Structure and limits

An implementation states what the reasoner meets first and how the rest is reached.

Only the platform's own limits bind. Every other limit (any size or budget the architect sets) carries a stated reason and moves when the reason moves. It is never cited as the owner's, and content is never dropped to fit a limit: it goes to another part of the implementation, or the limit moves with its reason. Where neither is possible, the omission is declared. The owner's rulings and the architect's derivations are recorded apart, so a derived clause is never mistaken for something the owner said.

### §13.6 Revision

§10 governs an implementation as it governs a DFD: revise deliberately, record the revision, never change it silently. What is released is what was checked. A check's reach is stated: what it compared, and whether it is independent of what it checks. Evidence for a revision is reported against the decision it could change and with its limits (§11). Outside review, including review by an AI model, is verified claim by claim before adoption, and a reviewer is shown the implementation as the reasoner meets it.

---

## Appendix A. Worked illustrations in three domains

These illustrations show the apparatus in three domains whose substrate and vocabulary differ: law, traditional medicine and construction. They are constructed for exposition. They are not readings of real matters and are not evidence that the framework operates in law or traditional medicine (§11).

Every legal, regulatory, clinical, procedural and contractual proposition below is a **stipulation** of the illustration, assumed only to show structure. A stipulation is marked **[assumed]** where it first appears, and any unmarked proposition of law, practice or evidence is also a stipulation. None states the law of any jurisdiction, a rule of any profession, or a property of any product or medicine. In a real reading each such proposition is read from the instrument and cited (*When to reason from competence*). None of this is legal, clinical, engineering or commercial advice.

Each illustration is abbreviated. It shows the chain, the lock, the principal branches with their opening and closing conditions, one contradiction, one asymmetry, and the emission. It omits machinery, consequence of closure, materiality and pruning, and so is not a complete reading. A.1 is also given in partial backstage form (A.1.1), which adds the end-paths, their confidence and the defensibility statement; it still omits machinery, consequence of closure, materiality and pruning.

### A.1 Law: a debt claim and a limitation defence

*Matter.* A supplier sues a customer for an unpaid invoice. The claim form was issued after the period the statute sets for such debts had run **[assumed]**. The customer has pleaded limitation. The supplier answers that an email from the customer, sent before the period ran out, acknowledged the debt. The customer's side is the instructing party.

*Chain.* The sale and delivery (Occurrence); the supplier's awareness that payment was missed (Recognition); the invoice, any demand letters, and the customer's email (Recording); the claim form (Escalation); the court's treatment of the defence (Crystallisation); judgment or settlement (Resolution).

*Governing hierarchy, apex first.* **[assumed]** The limitation statute sits over the contract, and the contract over later correspondence. The statute sets the period, when it starts, and what restarts it; a contract term cannot lengthen the period unless the statute allows it. The reading would read all of this from the statute and quote it.

*Lock-point.* Crystallisation, mode contested. The email was made and is clear as a record; what no earlier stage built is any determination of its effect under the statute, so the shape of the matter turns on that one question: whether the email is a restarting event **[assumed]**.

*Trajectory, with action-windows.* Sprout 1: the email is an acknowledgment. It opens if the email meets whatever the statute requires of an acknowledgment (form, signature, timing, read from the section); it closes if it does not. Sprout 2: a part payment. It opens if any payment was made within the period and part payment restarts the period **[assumed]**; it closes if none was. Aji: an application by the supplier to amend to plead a different cause of action, possible only if the court permits **[assumed]**.

*Contradiction.* The supplier says the email acknowledges the debt; the customer says it only asked for statements. This is a recharacterisation of one document, and the reading sets both against its exact words.

*Asymmetry.* Procedure: the supplier carries the burden of showing a restarting event **[assumed]**. Information: the customer holds its own internal record of why the email was sent. Each produces a branch (the part-payment branch) or a pruning reason.

*Emission, in the domain's language.* "On the file as it stands, the limitation defence succeeds unless the customer's email is read as an acknowledgment of the debt. That depends on the email's wording, which the file shows only in part, so neither outcome can yet be called the stronger. This holds unless the contract fixes a longer period and the statute lets it, which the file does not suggest."

*Consultation mode (asked by the customer's side: what should we do?).* The reading above is unchanged. Beneath it, a separate part, given from the customer's position only: "Recommended: obtain the full email and the payment history before the next step in the proceedings. This closes the acknowledgment route if the email is only a request for statements. It accepts the risk that the claim succeeds if the email is read as an acknowledgment. What would change this: a payment within the period. This is not legal, clinical, engineering or commercial advice; it rests on a framework whose value is unproven; have a qualified professional check it before acting."

*Sources of this matter, by provenance.* Substrate-verbatim: the limitation statute, including its provisions on acknowledgment and part payment; the contract; the court rules on pleading deadlines. Transferred doctrine: none.

#### A.1.1 The same matter, in partial backstage form

```
LOCK:                  Crystallisation, contested; working component: record (one email)
DOWNWARD READ:         the email is the only post-due-date record; its effect was never determined
GOVERNING HIERARCHY:   statute [assumed] over contract over correspondence. Apex provisions present
                       verbatim: none (illustration). In a real reading, stated here.
FORWARD MOVE-SET:      S1 acknowledgment (opens: statutory form met; closes: not met)
                       S2 part payment (opens: payment in period; closes: none)
COUNTERPARTY SPROUTS:  the supplier presses S1 and S2 and will plead any payment as part payment
OFFENSIVE ASYMMETRY:   burden [assumed] sits with the supplier; the customer holds its own records
END-PATHS:             claim barred (moderate); claim succeeds on acknowledgment (moderate);
                       claim succeeds on part payment (low, unless a payment is found)
DEFENSIBILITY:         at the worst-case end-path (acknowledgment found) the reading holds that
                       the email's wording decides, and says what wording
OMITTED HERE:          machinery per branch; consequence of closure; materiality; pruning
```

### A.2 Traditional medicine: a complaint to a professional body

*Matter.* A client complains to a herbal practitioners' professional body that a practitioner supplied a herbal preparation without recording the client's prescribed medicine. The practitioner says the client never mentioned it. The body has a code of conduct **[assumed]**. The practitioner is the instructing party.

*Chain.* The client's consultation, at which the prescription existed (Occurrence); the practitioner's recognition, or not, that it mattered (Recognition); the consultation notes (Recording); the complaint (Escalation); the body's determination (Crystallisation); the outcome (Resolution).

*Governing hierarchy, apex first.* **[assumed]** The body's code sits over the practitioner's own practice habits, and any binding rule on records sits over both. Whether a given preparation interacts with a given medicine is a therapeutic question that belongs to a pharmacological reference. The reading cites it or declares it could not reach one.

*Lock-point.* Recording, mode held open. If the client did not disclose the prescription, no record of it could arise; if the client did, the failure is that it was not written down (mode absent). Which applies turns on the intake form and the notes, which the reading does not yet have.

*Trajectory, with action-windows.* Sprout 1: the practitioner produces the intake form. It opens if a form was used and completed at the visit **[assumed]**; it closes if none was. Sprout 2: the body requests the client's own records. It opens once the body accepts the complaint for investigation **[assumed]**; it closes if the client declines to provide them. Sprout 3: the body determines on the two accounts alone. It opens if neither document exists; it closes as soon as either is produced. Aji: the practitioner's option to ask the body for mediation, available until the determination **[assumed]**.

*Contradiction.* The client says the medicine was disclosed at the visit; the practitioner's notes, if they list other matters discussed but not this one, cut against that. This is a recharacterisation of what the notes show, or a direct elimination if the notes expressly record that no other medicine was taken **[assumed]**.

*Asymmetry.* Information: the client knows what else they take; the practitioner knows only what they were told and wrote down. Procedure: the body holds the complaint route and can ask for the notes **[assumed]**. Framing: the practitioner may describe the preparation as mild; whether any preparation carries a caution is for the reference.

*Emission, in the domain's language.* "On the file as it stands, whether the client disclosed the prescription cannot be said. It turns on whether an intake form was used and what the notes show. Whether the combination carried any caution cannot be said until the pharmacological reference is read. If the client is taking both now and has any adverse effect, the client should see the prescriber or, where it may be serious, urgent care at once; that is a safety matter stated here, not an option held in reserve for the complaint."

*Consultation mode (asked by the practitioner: what should I do?).* The reading above is unchanged. Beneath it, given from the practitioner's position only: "Recommended: produce the intake form and the notes to the body, and say plainly what each shows. This closes the question of disclosure if the form shows the field. It accepts the risk that the body finds the practitioner failed to record a disclosed medicine. What would change this: evidence that the client's account of the visit is wrong in some other respect, such as a note in the client's own records of what was said at the visit. It does not direct any change to any medicine or treatment, which is for the prescriber or clinician. This is not legal, clinical, engineering or commercial advice; it rests on a framework whose value is unproven; have a qualified professional check it before acting."

*Why this reading demands substrate.* Whether the combination carries a caution is a therapeutic specific. The reading cites a reference or declares that it could not reach one, and downgrades confidence accordingly. It never states an interaction from memory.

*Sources of this matter, by provenance.* Substrate-verbatim: the body's code; the intake form and the consultation notes, once produced; the pharmacological reference's entries for each product, once read (not read in this illustration). Live-search: the client's current prescription, retrieved at use. Transferred doctrine: none; any description of the preparation is a therapeutic specific and is read from the reference. On-call: the reasoner's own weighing of which question to ask first.

### A.3 Construction: an instruction to do extra work, given orally

*Matter.* On site, the employer's representative tells the contractor to do extra work. Nothing was confirmed in writing at the time; the contractor's site diary mentions the work. Months later the contractor asks to be paid and the employer refuses, citing the contract's written-notice clause **[assumed]**. The employer paid for three earlier oral instructions without notice. The contractor is the instructing party.

*Chain.* The instruction and the work (Occurrence); the contractor sees the work as extra (Recognition); the instruction and cost are recorded, or not (Recording); the claim is submitted (Escalation); the contract administrator or tribunal decides (Crystallisation); payment or dispute (Resolution).

*Governing hierarchy, apex first.* **[assumed]** The law on payment for work an employer accepts sits over the contract; the contract's notice and variation clauses sit over site practice. Whether the law lets a notice clause bar payment for accepted work is read from the instrument.

*Lock-point.* Recording, mode defective: the instruction appears only in the contractor's diary, not in the form the contract requires **[assumed]**. The file does not show whether the notice period has run.

*Trajectory, with action-windows.* Sprout 1: a variation under the contract. It opens if notice was served in time and the instruction can be proved; it closes if either fails. Sprout 2: payment for accepted work outside the contract. It opens if the law allows it despite the clause **[assumed]**; it closes if the contract is held to exclude it. Sprout 3: waiver or estoppel. It opens if the employer's representative saw the work, said nothing, and paid for similar work earlier; it closes if the representative lacked authority **[assumed]**. Aji: a negotiated settlement before any formal claim, available until either party notifies a claim **[assumed]**.

*Contradiction (selective enforcement).* The employer enforces the written-notice clause against this item while having paid the three earlier oral instructions without notice. The reading sets the two treatments against the same clause.

*Asymmetry.* Information: the contractor holds the site diaries; the employer holds any instruction records. Timing: the notice period favours the employer **[assumed]**. Procedure: the dispute route favours whoever can start it first **[assumed]**.

*Emission, in the domain's language.* "The extra work is claimable as a variation only if notice was served in time and the instruction can be proved; on the file as it stands, neither is shown. A claim for work the employer accepted remains possible if the law lets it override the clause. If the employer paid three earlier oral instructions without notice, that undercuts its reliance on the clause here **[assumed]**. This holds unless the contract treats site instructions as binding without written confirmation, which the file does not show."

*Consultation mode (asked by the contractor: how should we proceed?).* The reading above is unchanged. Beneath it, given from the contractor's position only: "Recommended: because the file does not show whether the notice period has run, give notice of the claim now, on the ground the record already supports, and then collect the site diary entries and any message recording the instruction. Giving notice ends the period in which a settlement can be reached before a formal claim **[assumed]**. It accepts the risk that only the claim for accepted work survives. What would change this: a written record of the instruction, or a reading of the notice clause showing the period has already run. This is not legal, clinical, engineering or commercial advice; it rests on a framework whose value is unproven; have a qualified professional check the contract and the notice period before acting."

*Sources of this matter, by provenance.* Substrate-verbatim: the contract's notice and variation clauses; the governing law; the project's correspondence and diaries, retrieved and dated. Transferred doctrine: none. On-call: the reasoner's weighing of which route to try first.

### A.4 What the illustrations show, and what they do not

The locks fall at Crystallisation in A.1 and at Recording in A.2 and A.3, with different modes (contested; held open; defective). That the last two share a stage is a feature of these constructed cases, not a claim that locks usually fall there. In each, the governing layer above the contract or the code is read first, each branch carries an opening and a closing condition, the contradiction is set against the document's own words, and the emission carries the structure in the domain's language. In each, a claim about an instrument, a reference or a clause is cited from the instrument or declared absent, which is the authority rule at work. The illustrations do not show materiality, pruning or machinery per branch, and leaf confidence appears only in A.1.1. They are not a test of the framework.

---

# Back matter

## Glossary

Terms active in this framework.

**Action-window.** A sprout-edge attribute in the trajectory tree: opening condition, closing condition, machinery operated in the window, consequence of closure. (§3.4)

**Adversarial-institutional matter.** The scope: a matter with counterparty interests, institutional rule-governance, and documentary traceability. (*What Vantage is*; §1.3)

**Aji.** A mark on a trajectory branch reachable from current state but not currently pursued; carries activation and expiry conditions. (§3.5; derivation in Attributions)

**Apex completeness.** The requirement that the apex class of a held domain be indexed to completeness, every operative provision verbatim, not sampled by past need. (§5.6)

**Apex-sampling.** The failure in which the apex was indexed by need, so it looks present while a governing provision has no verbatim home. (*How you interact with substrate*; §5.6)

**Backward read.** The lock-point sub-operation: identify the locked stage, lock-mode, working-component sub-typing, substrate failure pattern, and upstream conditioning. Terminates at substrate-failure characterisation. (§2.4)

**Capture (vs prevention).** Vantage's relationship to structure: structure records reasoning so it holds under pressure, rather than fencing reasoning to prevent failure. (*Vantage and structure*)

**Chain.** Primitive P1: the universal six-stage sequence — Occurrence → Recognition → Recording → Escalation → Crystallisation → Resolution. (§1)

**Consultation mode.** A mode, distinct from a closed query, invoked when the user asks what to do (what should we do; which option should we take). The reading is produced exactly as in a closed query; a separate, labelled recommended course of action follows it, given from one party's position and carrying the safety requirements of the *Objective*. A closed query carries no advice. (*Objective*; §9.8)

**Contradiction node.** Primitive P6: counterparty-position handling at material nodes — recharacterisation, direct elimination, selective enforcement. (§6)

**Defensibility statement.** The part of a reading that says what holds against pressure at the worst-case end-path. (*Objective*; §9.8)

**Domain Foundation Document (DFD).** The captured residue of reading a *domain* (rather than a matter): the domain's substrate classes, recurring matter shapes, configuration choices, characteristic lock-points. Read back at the start of later sessions so matter readings reason against it. Fixed when read; revised deliberately, never changed silently. Made durable for repeated use as part of a domain implementation (§13). (*The two scopes*; §10)

**Domain implementation.** Ground (held texts, reference material, a map) and a reading standard, built for repeated use of a domain. It carries no method of its own; the reasoner reasons. (§13)

**Downward gravity.** Each stage's failure mode is generated by what the prior stage did or did not do. (S4; §2.3)

**Emission rule.** The reading is emitted in the domain's language, never the framework's; Vantage's vocabulary (lock-point, trajectory, sprout, aji, reciprocation, drift) stays backstage as reasoning scaffolding. The structure comes through; the jargon does not. A hard rule. (§9.8; *What Vantage is*)

**End-path.** A leaf of the trajectory tree; the matter's terminal disposition along a path. A derived structural property, not a primitive. (§3.3)

**Forward-read.** The most-probable single path extracted from the trajectory tree. Derived, not a primitive. (§3.2)

**Ground.** (mass noun) What a domain implementation holds for the reasoning: held texts typed by provenance, reference material, a map that declares its gaps. See *Calibration* for the count noun. (§13.2)

**Held texts.** The governing instruments an implementation holds verbatim, dated and typed by provenance. (§13.2)

**Instructing party.** The party for whom the reading is being made. The reading stays two-sided (drift 5); only advice in consultation mode is given from this party's position. (*Objective*; §9.9-bis)

**Lock-point.** Primitive P2: the stage at which the chain's shape was determined; the root of the trajectory tree. (§2)

**Map.** A declared model of what a matter's life in a domain can touch and of the texts that close each map point, with its own gaps declared. Ground, not a reading. (§13.2)

**Map point.** One item in an implementation's map: something a matter's life in the domain can touch, with the texts that close it. (§13.2)

**Materiality.** The reasoner's judgment of whether a branch or finding is large enough to be walked at depth. (*Substrate depth is set by materiality*)

**Network.** Primitive P4: reading across multiple chains in one matter — parallel, sequential, interacting modes. (§4)

**Owner, architect, maintainer, reviewer.** Roles in building and keeping a domain implementation; one person may hold several. (§13.1)

**Provenance-typing.** The competence-and-substrate boundary turned inward: every claim the ground holds (substrate-verbatim, transferred doctrine) and every other source a reading relies on (on-call, live-search) is typed by kind. (*How you interact with substrate*)

**Reach.** What a comparison against the map shows was addressed; not correctness. (§13.3)

**Reading standard.** What an implementation checks, as capture (§13.4): terms in the documents' words, judgments tied to held text or marked, determinatives bound or marked unbound, figures with their working, and what was relied on and not reached travelling with the reading. Distinct from "a standard" (a governing instrument). (§13.4)

**Reasoning floor.** What you can still reason with when substrate is thin: the spine. A spine-only reading is shallow but defensible and marked as shallow. (§*Reasoning when substrate is thin*; *The spine*)

**Reciprocation.** Primitive P5 and the engine of substrate interaction: consult → extract → compute → assess → decompose, operating at every node where the tree may branch, indexed hind/fore × vertical/lateral, depth set by materiality. (§5; *How you interact with substrate*)

**Reference material.** The comparable sources an implementation holds for triangulation; not a library of prior readings. (§13.2)

**Spine.** The five load-bearing elements S1–S5. The diagnostic-anchor layer and the reasoning floor. (*The spine*)

**Sprout.** A branch in the trajectory tree, from a node to a successor, generated by reciprocation step five; carries action-window attributes. (§3.3–3.4)

**Stated reason.** The reason given for setting a map point or a branch aside; never a bare "ground". (§13.3; *Calibration*)

**Substrate.** The structural surface the reasoning runs on — the governing instruments, documentary record, and rules that define the space within which a matter is located, not merely data consulted against the matter (see *The founding move*). In practice it comprises the documentary record, governing instruments, the user's framing, and (for matter readings) any Domain Foundation Document. (*What Vantage is*; *The founding move*)

**Substrate-verbatim; transferred doctrine; on-call; live-search.** The four provenance kinds. Verbatim instrument text; universal doctrine written in from training, dated and flagged; the running model's own reasoning; current-state facts retrieved at use. (*Provenance-typing*)

**Trajectory.** Primitive P3: the branched tree rooted at the lock-point; the possibility space; the central operational object. (§3)

**Tree-walking.** The reading discipline: root the tree at the lock-point and walk node by node — reciprocate to enumerate sprouts, attach action-windows, pursue/prune/mark-aji, run transition self-checks, recurse to leaves. (§9)

**Working-component decomposition.** Each chain stage decomposes into working-component classes; the framework requires the decomposition, the domain supplies the categories. (§1.4; §8.2)
**Closed query.** A request for the reading only: where the matter sits, how it got there, where it can go, and what holds. It carries no advice. (*Objective*)

## Attributions

**Lineage, not dependency.** Vantage was developed drawing on the developer's experience with other frameworks, including a private, unpublished skill-design framework (the layered-cognition / structural-enforcement work) from which several disciplines were learned. Those frameworks are *peers and lineage*, not dependencies: Vantage does not load them, is not built on them, and a reading is not produced by operating one of them. Where a discipline was learned from that lineage, Vantage re-owns it in its own terms — the authority rule (cite, do not reconstruct) and the integrity-floor idea (the spine) are the clearest cases. The relationship is one of having learned from a sibling, not of running on a parent.

**Networks of Action Situations (NAS).** Closest prior art for the network primitive. Ostrom (2005, *Understanding Institutional Diversity*, the Institutional Analysis and Development framework); McGinnis (2011, *Policy Studies Journal* 39(1):51-78); Kimmich (2013, *Ecological Economics* 90:150-158); Kimmich, Baldwin, Kellner, Oberlack, Villamayor-Tomás (2023, *Sustainability Science* 18:11-26). Working-component decomposition was prompted by NAS's working-component classification, adapted to adversarial-institutional scope.

**Sendzimir et al. 2010.** Partial precedent for the lock-point intuition. Sendzimir, Flachner, Pahl-Wostl, Knieper, "Stalled regime transition in the upper Tisza River Basin," *Environmental Science and Policy* 13:604-619. Vantage sharpens distributed-mutual-reinforcement diagnosis into a locatable single decisive stage.

**Management and Transition Framework (MTF).** Partial precedent for cross-stage dependency typing. Pahl-Wostl, Holtz, Kastens, Knieper (2010, *Environmental Science and Policy* 13:571-581).

**Aji.** Borrowed from Go (Japanese 味, "taste"), denoting residual latent threat or potential in a position.

**Origin exchange.** The framework's cross-domain reach was first observed in a May 2026 exchange in which the six-stage chain and lock-point crossed cleanly from contract disputes into regulatory compliance with no translation. That exchange is the origin event, not a deployment.

## Graphs

This framework carries graphs. Four are load-bearing — chain (§1), lock-point (§2), trajectory tree (§3, the central graph), network (§4) — and must stay in sync with the prose of their primitive: if a primitive's structure changes, its graph changes in the same revision. The remainder are illustrative: they aid comprehension but carry a lighter obligation and may be set aside without revising the prose. Every graph carries a plain-text adjacency fallback in its comments for non-rendering environments.

## Version

**v4.0.** Repositions Vantage as a standalone AI reasoning framework: a specification of how an AI reasons about adversarial-institutional matters, operated directly by the platform. This supersedes the v3.0 conception, which treated Vantage as one member of a federated artifact set dependent on an external skill-construction framework. v4.0 removes that dependency framing entirely. What changed is the understanding of what Vantage *is*; the apparatus and reading discipline — the seven primitives, the five-step reciprocation, tree-walking — are unchanged in substance from v3.0, and the v3.0-cycle peer review of those mechanics carries forward. Three sections are genuinely new and have *not* been through that review: the relationship to structure (capture, not prevention), the competence-vs-substrate discipline, and the reasoning floor under thin substrate. Treat them as the parts most in need of validation under use — the competence-vs-substrate boundary especially, since it is the new load-bearing judgment. Building a domain understanding and answering a matter query are stated as one operation at two depths, not two architectures.

**On "complete in its own scope."** Vantage is complete as a *reasoning* framework — substrate in, reasoning, reading out. It is deliberately not self-sufficient as a *running system*: it assumes the platform supplies what a runtime supplies (it holds the context, it carries a Domain Foundation Document from one session to the next, it manages what is loaded when). The standalone form trades the federated conception's seam-management cost for a set of platform assumptions it does not itself specify. That is the right trade — those assumptions genuinely are the platform's layer, not the framework's — but it is a trade, not a free simplification. Read "complete in its own scope" as "complete at the reasoning layer," with the runtime layer assumed.

**v4.1 (draft, revision 4, 2026-10-31).** Adds: (1) the identity statement, *Why it is called Vantage*; (2) apex completeness (§5.6) and apex-sampling, named in *How you interact with substrate*; (3) provenance-typing, in the same section; (4) §13, domain implementations, written at the level of principle; (5) consultation mode in the Objective as a separate mode with its own safety requirements; (6) Appendix A, worked illustrations in three domains, each proposition marked as a stipulation, and the §9.8 examples rebuilt across them; (7) the front-matter block (version, date, author, licence, citation, readers, notice); (8) a limitation and a shifter in §11 for implementations and constructed examples; (9) *The two scopes*, *What Vantage is*, *What Vantage is not* and the footer revised to admit §13 (the exclusions of loading, modules and phases removed); (10) Calibration entries for *reading standard*, *ground* and *consultation*, and glossary additions; (11) wording changes that remove prevention-language and the use of "drift" for change to a domain understanding; (12) the §9.10 graph corrected so that contradiction and asymmetry fire at nodes. Changes in §§1-9 are confined to §5.6, §9.8, §9.10, the drift-1 guard, and wording in §2.6, §3.2, §7.4, §8.3 and §9.9-bis; the primitives are otherwise unchanged.

*Revision history.* Revision 1: the first draft of the additions above. Revision 2: responded to the first review round (consistency, safety, disclosure, attribution). Revision 3: responded to the second round (the wrong legal mechanism in the examples, a directive in a closed-query example, an inconsistent definition of consultation mode, missing publication metadata, wording that leaked process). Revision 4: responds to the third round (consultation-mode safety, the examples in Appendix A, the account of reach in §13.3, wording of capture versus prevention, the version note and attributions). Revisions 1 to 3 were each dated 2026-10-31, as was revision 4.

None of these additions has been independently validated. Each revision was reviewed adversarially by two AI models, covering consistency, safety, disclosure and attribution; the reviewers found blocking defects in each of the first three rounds. Revision 4 responds to the third round and has not itself been reviewed by those models; it should be read by a domain professional in each example domain. AI review tests coherence, not correctness (§11).

**On "complete in its own scope," revised.** v4.0 read "complete at the reasoning layer, with the runtime layer assumed." In v4.1 the platform still owns storage, loading and context. The framework also states what a domain implementation owes the reasoning (§13), so that platform choices cannot silently weaken a reading.

Prior domain readings produced under earlier conceptions remain valid as readings; they describe matters, not the framework version that produced them.

---

*Vantage — An AI Reasoning Framework, v4.1 draft r4, 2026-10-31*
*Operated by the AI platform directly. Substrate in, reasoning, reading out, reciprocative to user demand. Complete at the reasoning layer; §13 states what its ground owes it.*
