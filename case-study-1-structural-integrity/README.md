# Case Study 1: Structural Integrity Monitoring

## Case Introduction
ADB Safegate's airfield lighting fixtures operate in some of the harshest environments imaginable. They are routinely exposed to aircraft jet blast, ground vehicle impacts, thermal cycling, moisture ingress, and continuous vibration. Over time, these stresses produce structural fatigue, corrosion, mounting wear, and physical damage — any of which can render a fixture a safety hazard before it fails outright.

Today, structural condition is largely confirmed reactively — through physical inspection or after a failure occurs. The company wants to move toward **proactive structural monitoring**: surfacing early warning signs of mechanical compromise so they can be addressed before becoming operational risks.

The catch is that ADB Safegate does not yet stream dedicated structural sensor data (vibration, tilt, load) into the cloud. What is available is the operational telemetry already coming from Axon EQ fixtures — boostVoltage, inputCurrent, brownout alarms (alarmRemoteBrownout), board faults, lastSeen, responseRate, stale flags, and so on. These signals carry **indirect** information about physical state:

* Sudden changes in inputCurrent or boostVoltage following a weather or operational event may indicate a physical disturbance
* Spike patterns in brownout alarms could correlate with mounting or cable integrity issues
* Persistent stale or unresponsive fixtures may indicate physical disconnection rather than electronic failure
* Alarm clusters cross-referenced with geography or fixture type could surface structural hotspots ➤ Simply put: the telemetry you have was not designed to observe structural events — but signatures of those events may still be hiding inside it. Your job is to find them.

## The Challenge
Your mission: From existing operational telemetry alone, identify fixtures showing signs of structural degradation or impact events — before physical inspection confirms it.

You will work with telemetry from Axon EQ fixtures and must build a solution that can:

✅ Identify fixtures exhibiting telemetry patterns consistent with structural stress, damage, or impact — and articulate what a "structural event signature" looks like in the data
✅ Justify why your chosen signals are meaningful proxies for physical condition (engineering reasoning, not just statistical correlation)
✅ Provide a clear gap analysis — what existing telemetry is genuinely useful, what is unreliable, and what additional data (vibration, tilt, load, environmental) would be needed to lift detection to a more rigorous level, including a proposed minimum viable sensor dataset
✅ Demonstrate or sketch how detections would surface to a service engineer in a way they could act on

**Out of scope:** Confirming structural events with absolute certainty in the absence of dedicated sensors. Your detector will produce probabilistic indicators, not verified findings — and that is fine. What matters is that the indicators are defensible and useful as a triage signal.

## Bonus Track: From Algorithm to Product
*(Optional — additional points)*

Once you have built your algorithm, step back and ask: does it fit the kind of product CORTEX Service is, and does it deliver what an airport customer would actually pay for? Sketch a commercial roadmap for it — anchored in how you think customers would want to use this capability.

This case study (Structural Integrity) and Case Study 3 (EFD Localization) are intended to ship as part of the same algorithm package within CORTEX Service. You may consider this algorithm **together with** the other algorithm in the package, or treat it as a **standalone offering** — whichever framing produces a more credible commercial story.

Address the following dimensions:

* **Commercialization strategy** — Where does this product live? Inside CORTEX Service as a built-in capability, alongside CORTEX Service as a separate entity airports buy on its own terms, or as some hybrid? And within whichever choice you make, is it sold as one bundle with the other algorithm or as separate modules? Anchor both decisions in how you think airport customers would actually want to use this.
* **Pricing model & roadmap** — How do you charge for this: flat fee, per-fixture, per-airport, tiered, value-based per incident? And how does pricing evolve as the package matures from v1 (current data, current capability) through v2 and v3 (additional data streams, additional algorithms in the suite)?
* **Value articulation** — In concrete terms, what is the customer actually buying? Failures avoided, inspections deferred, safety incidents prevented, runway closures averted, fixtures replaced before they become hazards?
* **Algorithm-package lifecycle** — What ships at launch with the data and capability you have today? What improves as data quality and coverage grow? What additional algorithms (e.g. LED degradation, once production-ready) might join the package over time?

## Why It Matters
A reactive approach to structural integrity at airport scale carries real cost:

* **Safety risk** — a structurally compromised runway or taxiway light can fail without warning under jet blast or vehicle impact, creating an immediate operational hazard
* **Emergency response cost** — unscheduled structural repairs are dramatically more expensive than planned maintenance and frequently disrupt operations
* **Inspection burden** — without prioritisation, structural inspections are blanket and time-consuming; targeted inspection is far more efficient
* **Asset planning** — knowing which fixtures are degrading helps the company forecast replacement budgets across an airport's lifecycle

Even an imperfect, indirect indicator of structural risk gives ADB Safegate two valuable things: a triage tool that points engineers at the fixtures most worth inspecting first, and a concrete specification for the structural sensing investment that would make full monitoring possible.

## Judging Focus
* **Quality of detection logic** — is the link between telemetry patterns and structural events defensible from engineering reasoning, or speculative? Are the chosen signals meaningful proxies for physical condition?
* **Rigour given indirect data** — without ground truth from dedicated structural sensors, what does the team do to make their detector credible? Sensitivity checks, controlled comparisons across fixtures, sanity tests, and reasoning about false positives all count here.
* **Specificity of the gap analysis** — does the team clearly distinguish what their detector can and cannot tell from existing data, and articulate what additional sensing would lift its reliability — concretely, not generically?
* **Usefulness of the engineer-facing output** — would a service engineer be able to act on the result, or does it still require interpretation that hasn't been done?
* **Bonus — Commercial coherence** *(stretch)* — does the team's commercialization strategy, pricing, and value articulation hang together as a credible CORTEX Service offering, driven by how customers would actually want to use the product?
