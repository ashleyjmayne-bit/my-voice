# My Voice — Optional Friction Log Entries

## Friction Log 1 — Alexa+ developer tooling access

**Task attempted:**  
Set up the Alexa+ developer environment for the hackathon.

**Steps taken:**  
Reviewed the Alexa+ developer documentation, hackathon rules, FAQ, and setup references for the Category SDK, MCP Toolkit, CLI, and Web Simulator.

**Expected result:**  
I expected hackathon participants to have a path to access the Alexa+ add-on development tools after joining the event.

**Actual result:**  
The add-on tools remain preview-only for selected partners and are not available to general hackathon participants.

**Severity:**  
Important

**Workaround used:**  
Used the rules-approved simulated Alexa+ experience path and built a browser-based simulation.

**Actionable suggestion:**  
Add a prominent hackathon-specific banner at the top of every Alexa+ setup page stating: “Hackathon participants do not receive access to the gated add-on tools. Use the self-hosted MCP / Agent Skill path or the simulated Alexa+ path described in the hackathon rules.”

---

## Friction Log 2 — Simulation requirements are spread across multiple places

**Task attempted:**  
Confirm exactly what a simulated Alexa+ submission must show.

**Steps taken:**  
Read the official rules, FAQs, Alexa+ documentation, and Devpost discussion responses.

**Expected result:**  
A single checklist covering what counts as a valid simulation, whether voice is required, whether the UI must resemble Alexa+, whether hosting is required, and what judges expect to see in the demo.

**Actual result:**  
The information exists, but it is distributed across the rules, FAQs, and discussion replies.

**Severity:**  
Important

**Workaround used:**  
Built a clearly labelled “Simulated Alexa+ experience,” kept the repo locally runnable, used a custom accessibility-first UI, and made the demo show the working interaction rather than claiming production integration.

**Actionable suggestion:**  
Publish one “Alexa+ Hackathon Compliance Checklist” with separate columns for Agent Skill, self-hosted MCP, and simulated Alexa+ submissions.

---

## Friction Log 3 — Runtime technology rule can look contradictory for simulations

**Task attempted:**  
Verify whether the repository had to import and call Alexa+ runtime technology.

**Steps taken:**  
Read the general repository requirement and then the Alexa+ alternate-path exemption.

**Expected result:**  
A clear statement near the general runtime-hook rule that simulated Alexa+ submissions are exempt.

**Actual result:**  
The general rule says the repository must demonstrate required track technology at runtime, while a later Alexa+ paragraph explains that simulated submissions are exempt.

**Severity:**  
Important

**Workaround used:**  
Followed the explicit Alexa+ simulation exemption and documented the architecture honestly in the repository.

**Actionable suggestion:**  
Move the exemption directly beside the general runtime-hook requirement or add a bold cross-reference so participants do not think the simulation path is non-compliant.

---

## Friction Log 4 — Browser speech recognition is not a dependable accessibility baseline

**Task attempted:**  
Provide optional voice input in the simulated Alexa+ experience.

**Steps taken:**  
Implemented browser speech-recognition feature detection and tested supported/unsupported behaviour.

**Expected result:**  
Consistent microphone support across modern browsers.

**Actual result:**  
Speech recognition availability and handling are browser/vendor dependent.

**Severity:**  
Moderate

**Workaround used:**  
Made speech optional, added a full text fallback, and exposed clear status messages when speech recognition is unavailable.

**Actionable suggestion:**  
For simulation-oriented accessibility projects, provide recommended browser guidance and a reference fallback pattern so participants do not accidentally make voice support a single point of failure.
