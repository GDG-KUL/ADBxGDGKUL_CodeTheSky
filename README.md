# Code the Sky - ADB Safegate

ADB Safegate Introduction and use case available in powerpoint presentation. Also some training material ... any questions ? Come see us at the booth !

---

# **Who Are We – ADB Safegate**

ADB Safegate is one of the world's leading providers of integrated airport solutions, helping airports operate more safely, efficiently, and sustainably. Our portfolio spans airfield ground lighting, power and control systems, tower automation, intelligent docking guidance, and a growing set of data-driven services. With around 1,200 employees and a presence in more than 175 countries, we serve over 2,500 airports — from major hubs like Atlanta, Heathrow, Dubai, and Frankfurt to fast-growing airports across Asia and Africa.

We are a pioneer in LED airfield ground lighting and have been at the forefront of the transition from incandescent to LED airport infrastructure for more than two decades. Our **Airside 4.0** strategy connects every airside asset — lighting, gates, towers, regulators — to deliver real-time insight for better operational decisions.

**Smarter. Better. Now.**

---

# **Case Introduction**

Modern airfields are full of connected hardware — lighting fixtures, regulators, signs, sensors — already producing a constant stream of operational telemetry. **CORTEX Service**, our SaaS platform for predictive maintenance and operational insight, is where that data is turned into useful action: surfacing the fixtures that need attention, narrowing down where faults are happening, and getting maintenance teams to the right place at the right time.

There is more signal in the data we collect than we are currently using. This hackathon focuses on three open product questions we are working through — each grounded in real ADB Safegate data.

---

# **The Challenge**

**Your mission:** Use the data ADB Safegate is already collecting to build something that makes airport maintenance smarter — and tell us clearly what your solution can and cannot do today, and what additional data would unlock the next step.

Pick the case study that best matches your team's strengths:

* **Case Study 1 — Structural Integrity Monitoring** *(includes optional commercial bonus track)* — Distinguish healthy fixtures from two structural fault conditions using labeled 3-axis vibration data from a sensor board characterization rig. Best for teams drawn to signal processing, frequency-domain analysis, and supervised classification.
* **Case Study 2 — LED Degradation** *(pure exploration)* — Estimate cumulative LED degradation per fixture without any ground truth on light output, hours run, or labelled failures. Solutions must be defensible from LED physics. Best for teams drawn to scientific reasoning and working under uncertainty.
* **Case Study 3 — EFD Localization** *(includes optional commercial bonus track)* — Given powerline communication telemetry from a 90-fixture series circuit during an earth fault, narrow down where on the circuit the fault occurred, with honest confidence scoring. Best for teams drawn to spatial reasoning and uncertainty quantification.

Full scope, deliverables, and judging criteria for each case are in `Structural_Integrity_README.md`, `LED_Degradation_README.md`, and `EFD_Localization_README.md`.

---

# **Resources & Tools**

* **Case study datasets** — provided as CSV files in this repository, alongside metadata and schema references. Each case study has its own data folder; see the case-specific README for what's included and how it's structured.
* **Case-specific READMEs** — detailed scope, deliverables, and judging criteria for each case.
* **CORTEX Service** — our SaaS platform for predictive maintenance and the eventual deployment home for any algorithm coming out of this hackathon. Useful context when designing your solution, and essential for the optional commercial bonus track in Cases 1 and 3.
* **PowerPoint deck** — visual introduction to the three cases.

---

# **Judging Criteria**

| Category                        | Weight |
| ------------------------------- | :----: |
| Presentation                    |   30%  |
| Result (Accuracy & Performance) |   40%  |
| Solution Originality            |   30%  |
