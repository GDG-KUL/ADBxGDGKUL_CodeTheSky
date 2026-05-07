# Case Study 2: LED Degradation

## Case Introduction
ADB Safegate equips airports worldwide with airfield lighting systems. Axon EQ — the company's connected LED fixture platform — already streams operational telemetry from thousands of installed lights into the CORTEX Service platform.
 
Today, lights are largely replaced reactively: when a fixture fails, a service call is dispatched. The company wants to move toward **preventive maintenance** — replacing lights *before* they fail, based on a per-fixture estimate of how degraded each one is.
 
The catch is the data. Axon EQ fixtures transmit electrical and alarm telemetry — boostVoltage, inputCurrent, LED temperature alarms, over-current alarms, board faults, brownouts, output-below-75% alarms, lastSeen, responseRate, and stale flags. However:
 
* There is no photometric output measurement — optical degradation cannot be observed directly
* There is no hours-run counter — uptime must be inferred from connection-state signals
* There are no labeled failure events or maintenance histories suitable for supervised learning
* Environmental coverage (humidity, ambient temperature) is incomplete and varies by site ➤ Simply put: the thing we want to measure (LED degradation) is not directly observable in the data, and there is no historical ground truth of failures to train or validate against.
## The Challenge
Your mission: Build a credible LED degradation indicator from existing telemetry — and defend it using physics, not labels.
 
You will work with telemetry from Axon EQ fixtures and must build a solution that can:
 
✅ Produce a per-fixture degradation indicator (score, signal, or model) from the available telemetry
✅ Justify the indicator from first principles — grounded in established LED and driver physics about how aging manifests in electrical and thermal behavior
✅ Demonstrate the indicator behaves consistently with theoretical degradation trends — responding as physics predicts under stress, and remaining stable when no stress has occurred
✅ Deliver a clear gap analysis — what the indicator *cannot* tell, and what additional data (photometric, runtime, failure labels, environmental) would be needed to make it production-ready
 
**Validation approach:** Because no failure-labeled data is available, validate your indicator against **theoretical degradation trends derived from LED physics**. If physics predicts a particular drift, shift, or variance pattern in a given signal as a fixture ages, your indicator should reflect that. Articulate the physics you are relying on, then show your signals behave accordingly.
 
**Out of scope:** Predicting absolute remaining useful life in hours, calibrating to actual lumen output, or claiming specific failure-prediction accuracy. No ground truth exists for those claims, and they are not what is being asked for.
 
## Why It Matters
A reactive replacement strategy at airport scale carries real cost:
 
* **Safety risk** — a failed runway or taxiway light is an immediate operational hazard
* **Unplanned downtime** — emergency dispatches and service calls are far more expensive than scheduled maintenance
* **Operational disruption** — fault response can require runway closures or restricted operations during peak traffic
* **Wasted spend** — replacing healthy fixtures too early is just as costly as replacing failed ones too late
Even an early, physics-grounded degradation indicator — one that does not yet predict exact failure dates — gives ADB Safegate two things of real value: a defensible foundation for preventive maintenance scoring on CORTEX Service, and a concrete specification of which additional data streams would actually be worth the cost of collecting.
 
## Judging Focus
* **Rigour of physics reasoning** — is the link between telemetry and degradation defensible from first principles, or hand-waved? Are the equations and relationships invoked applied correctly to the available signals?
* **Depth of data exploration** — how thoroughly is the telemetry investigated? Distributions, time dynamics, fixture-to-fixture variation, and inter-signal correlations should reflect genuine curiosity, not just convenience.
* **Quality of hypothesis formation** — does the team form clear, testable hypotheses that connect physical theory to observable signals, rather than fitting first and explaining afterwards?
* **Methodological soundness without ground truth** — given no labels exist, what does the team do to make their analysis credible? Sensitivity checks, controlled comparisons across fixtures, and sanity tests all count here.
* **Intellectual honesty and depth of gap analysis** — does the team clearly communicate what their indicator *cannot* tell, and does the gap analysis surface genuinely interesting limitations of the existing data rather than only the obvious ones?
