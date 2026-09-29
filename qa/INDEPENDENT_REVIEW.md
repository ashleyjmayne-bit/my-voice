# My Voice — independent technical review

Date: 29 September 2026  
Role: independent senior engineer and sceptical hackathon judge  
Source of truth: `current-source/index.html`

## A. Verdict

**FAIL for final hackathon submission readiness; PASS for the remediated technical prototype.**

The browser prototype and corrected judge-facing claims are technically ready. The overall submission is not yet ready because the supplied package does not contain the mandatory final GitHub repository setup or demo video. The official rules permit this simulated Alexa+ path, and the official FAQ says hosting is not required, but a locally runnable GitHub repository and a video clearly showing the simulation are still required.

## B. Exact defects found

1. High-contrast mode rendered white text on bright cyan or near-white backgrounds. Measured contrast was 1.09:1 to 1.26:1.
2. Saved accessibility preferences were overwritten with default control values on every reload.
3. End users could see “Technical details for judges” and internal scoring language.
4. Keyboard navigation had no skip-to-content target, and active navigation did not expose `aria-current`.
5. Microphone status was inside the Home section, so listening/error feedback was off-screen and hidden in the other workflows.
6. “Nothing is sent anywhere” was too strong when optional browser speech recognition may use a browser/vendor speech service. Local browser storage was not described as unencrypted demo storage.
7. The safety rule for `pin` matched words such as “spinning”. A password/PIN request without an organisation keyword was only medium risk. Urgency-only cases could be labelled low despite showing an urgency warning.
8. The intent router gave the word “bank” enough weight to misroute “help me understand my bank statement” to the safety flow.
9. Repeating “Show this step” in the guided demo could create duplicate reminders and timeline events.
10. Trusted contacts could be removed with one action and no confirmation.
11. Corrupt or partial version-matching local state could replace expected arrays/settings and break rendering.
12. At desktop width, the Hackathon Demo control wrapped onto an isolated second header row.
13. Submission claims overstated or misstated the implementation: TypeScript, browser speech synthesis, editable machine interpretations, persistence “across sessions” without a same-browser qualifier, comprehensive audit logging, full simplified-language support, and an implemented Alexa+ production path.

## C. Exact changes made

### Prototype

- Fixed the high-contrast palette for primary controls, notices, banners, warning/success panels, risk badges, destructive controls and activity records.
- Restored saved text size, contrast, motion and simple-language settings before applying them at startup.
- Added state-shape normalization for arrays and settings.
- Added a first-focus skip link and `aria-current="page"` navigation state.
- Moved the speech-status live region outside individual sections so it remains visible and announced everywhere.
- Replaced judge/debug labels with plain-language explanations.
- Reworded local privacy and speech-browser boundaries; changed “Keep this private” to “Keep only in this browser”.
- Added word boundaries and safer weights to the risk rules; made a credential, unusual-payment or remote-access request independently high risk.
- Reduced organisation-name routing weight and added “statement” to explanation routing.
- Prevented repeat demo actions from duplicating state while still allowing the consent review to be reopened.
- Added confirmation before removing a trusted contact.
- Clarified the consent step in Demo Step 5.
- Widened only the desktop header container to stop the demo button wrapping.

### Submission materials

- Changed “TypeScript / JavaScript” to the actual HTML/CSS/JavaScript stack.
- Removed the nonexistent browser speech-synthesis claim.
- Qualified persistence as same-browser persistence across refreshes.
- Replaced the false “correct the interpretation” claim with the actual behavior: revise original words and rerun before choosing an action.
- Narrowed audit and simple-language claims to what the prototype implements.
- Changed “voice-first” to “voice-capable” where needed.
- Marked the Alexa+ add-on/backend path as unimplemented future work that requires access, certification and device testing.
- Updated repository/video packaging instructions to match the current official rules.

## D. Build and test results

The project has no package manifest, dependency installation, compiler or build command. It is a static single-file application. Inventing a build command would misrepresent the project.

Build-equivalent static gate: **PASS**

- inline JavaScript syntax: PASS;
- 63 DOM IDs, 0 duplicates;
- 51 statically referenced IDs, 0 missing;
- 0 external script or stylesheet dependencies;
- 0 application network-call implementations;
- 0 speech-synthesis/automatic robot-voice implementations.

Automated Chromium review: **39/39 PASS**

- every requested flow completed end to end;
- exact words preserved through interpretation and consent review;
- final sharing confirmation required; no external message sent;
- reminders, timeline, contacts and accessibility settings persisted after reload;
- safety high/low cases, a `spinning` false-positive regression case, standalone PIN request and bank-statement routing passed;
- repeated demo action did not duplicate state;
- desktop 1440×900, tablet 820×1180 and mobile 390×844 had no horizontal overflow;
- mobile navigation was available;
- labels, live regions, visible focus, skip link and current-page state passed;
- high-contrast primary/notice/banner ratios measured 16.69:1 / 15.19:1 / 15.19:1;
- console errors: 0;
- outbound application requests: 0.

Visual screenshots were also reviewed at all three target sizes. A browser accessibility-tree pass confirmed names, roles and dynamic content exposure. This was not a full NVDA/JAWS/VoiceOver user session.

## E. Remaining limitations

- Deterministic English-language rules are deliberately narrow and can still miss or misclassify unfamiliar wording.
- This is a browser simulation, not an Alexa+ Agent Skill, add-on or MCP server.
- The guided demo uses preset examples, although it invokes the same live workflow functions used for arbitrary typed input.
- Speech recognition depends on browser support, permissions and possibly a browser/vendor service; real microphone audio was not validated across browsers.
- Data is stored unencrypted in same-browser `localStorage`; there is no authentication, secure backend, cross-device sync, retention policy or multi-user isolation.
- Sharing is only a local simulation.
- No real identity verification, financial integration, medical/legal decision-making or emergency escalation exists.
- Testing used Chromium; Firefox, Safari, NVDA, JAWS and VoiceOver remain untested.
- The prototype has no versioned package/build system because it is a single static file.

## F. Judge-facing claims that changed

The Devpost copy, judge pitch and architecture notes now use the defensible claims below:

- simulated Alexa+ browser experience, not a live Alexa+ integration;
- deterministic local workflow engine, not a production LLM;
- HTML/CSS/JavaScript, not TypeScript;
- browser speech recognition only, with full text fallback and browser-dependent processing;
- same-browser persistence across refreshes, not secure cross-device persistence;
- selected simpler home-screen wording, not whole-product plain-language transformation;
- a local decision record for key workflow checks/consent/list status, not a complete audit of all actions;
- revise original wording and rerun, not directly edit the machine interpretation;
- simulated share after explicit confirmation, not external messaging.

Any spoken pitch, captions, screenshots or earlier deck outside this package must use the same wording.

## G. Do not submit until these are fixed

1. Create the required GitHub repository from the clean reviewed package and include the run instructions. If public, add a visible open-source licence; if private, share it with the reviewers named in the official rules.
2. Record and check the final demo video using the reviewed source. It must clearly show that this is the permitted simulated Alexa+ experience and show the working consent step.
3. Put the final repository URL and video into the Devpost entry, then do one clean-machine run from the repository instructions before submission.

No remaining code defect found in this review is on the do-not-submit list.

## Authoritative rule checks

- [Official hackathon rules](https://amazonappdev2026.devpost.com/rules)
- [Official hackathon FAQ](https://amazonappdev2026.devpost.com/details/faqs)
- [Amazon Alexa+ add-on documentation](https://developer.amazon.com/docs/alexaplus/add-ons/home.html)
