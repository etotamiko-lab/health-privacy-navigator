# Health Privacy Navigator
 
**Which rules protect health data, in every U.S. state, based on who holds it.**
 
[Open the tool](https://etotamiko-lab.github.io/health-privacy-navigator/) · [TechInHSR](https://techinhsr.com) · [Substack](https://techinhsr.substack.com)
 
HIPAA covers who holds health data, not what the data is. A lab result in a hospital's records is protected by HIPAA. The same result is not, once a patient downloads it and uploads it to an AI chatbot. Cash-pay telehealth, fitness apps, wearables, and symptom searches may fall outside HIPAA entirely. Some states have closed part of this gap, and many have not.
 
The Health Privacy Navigator shows, for all 50 states and DC, which federal and state rules apply, where AI-specific laws add duties, and where protection runs thin.
 
## Who it is for
 
- Patients, care partners, and patient advocates
- IRB, HRPP, privacy, and compliance professionals
- Researchers working with health data or AI
- Health systems, vendors, and developers deploying AI
## How to use it
 
1. **Pick a state** on the map or from the list. Map colors show how much protection the state offers outside HIPAA.
2. **Pick who holds the data:**
   - Hospital, clinic, or health plan (HIPAA covered entity)
   - Vendor or AI tool working for one (business associate)
   - Cash-pay or direct-to-consumer care
   - Consumer app, wearable, or AI chatbot
   - A patient's own records shared with an AI tool
3. **Flag sensitive data:** mental health, substance use, reproductive and sexual health, HIV and STI, genetic, biometric, minors, location, or neural data.
Results show three layers (federal rules, the state's privacy laws, and AI-specific laws), each marked **Applies**, **Depends**, **Does not apply**, or **Not yet in effect**. A short summary, notes on sensitive data, and a list of gaps to watch follow.
 
Two more tabs:
- **Compare states** lines up all 51 jurisdictions. Select a row to open that state.
- **Key concepts** covers how protection drops away once data leaves the health system, de-identification, opt-in versus opt-out consent, ghost AI, where IRBs fit, recent federal changes, and questions patients can ask about AI in their care.
## What it covers
 
**Federal:** HIPAA Privacy, Security, and Breach Notification Rules; HIPAA de-identification; 42 CFR Part 2; FTC Act Section 5; FTC Health Breach Notification Rule; GINA; 21st Century Cures Act information blocking; COPPA.
 
**State:** general medical confidentiality laws, including those that reach beyond HIPAA (California CMIA, Texas HB 300); comprehensive consumer privacy laws, with effective dates, HIPAA exemption type, and consent model; consumer health data laws (Washington, Nevada, Connecticut); shield laws; and rules for sensitive data types.
 
**AI:** state health AI laws on clinical use and disclosure, payer and utilization review, chatbots and companions, AI in mental health care, and AI governance.
 
## Background
 
This tool grew out of the Alliance for Health Policy Capitol Hill briefing on health data privacy in the AI era (October 2026). At that briefing, a patient advocate asked for a public tool that shows, in one place, what is protected and what is not. It also draws on the TechInHSR Substack series on state AI laws and their implications for research compliance.
 
## Accuracy and updates
 
**Current as of October 29, 2026.**
 
This is an educational reference, not legal advice. Laws in this area change quickly, several listed laws are not yet in effect, and some dates and bill numbers come from secondary trackers. Check the original law before relying on any entry. Sensitive data rules are summarized, not complete.
 
Corrections are welcome. Please open an issue with the state, the entry, and a link to the primary source.
 
## Technical notes
 
- Single self-contained file (`index.html`). No build step and no dependencies other than Google Fonts.
- Works on desktop and mobile, with light and dark modes.
- Remembers the viewer's last selection in their browser only. No data is collected or sent anywhere.
### Updating the data
 
All data sits in the first `<script>` block of `index.html`:
 
| Object | Holds |
|---|---|
| `AS_OF` | The "current as of" date. It also decides whether a law shows as in effect or upcoming. |
| `FED` | Federal rules and how each applies to the five holder types |
| `FED_CHANGES` | Federal timeline on the Key concepts tab |
| `SHIELD` | States with reproductive health shield laws |
| `ST` | One entry per state (see fields below) |
| `DEF` | Default notes for sensitive data types when a state has no specific note |
| `SOURCES` | Footer source list |
 
State entry fields:
 
- `cp`: comprehensive privacy law, with `law`, `eff` (YYYY-MM-DD), `st` (`effect`, `enacted`, or `narrow`), `hx` (`entity`, `data`, or `both`), `sens` (`opt-in` or `opt-out`), and `note`
- `chd`: consumer health data law, with `law`, `eff`, and `t`
- `med`: medical confidentiality law, with `law` and `t`; add `beyond: true` if it reaches entities HIPAA does not
- `ai`: list of AI laws, each with `c` (`clinical`, `payer`, `chatbot`, `mh`, or `gov`), `law`, `eff`, and `t`
- `s`: sensitive data notes keyed by `mh`, `sud`, `repro`, `hiv`, `gen`, `bio`, `minors`, `loc`, or `neural`
- `pend`: pending items shown in a "Watch" box
When you change `AS_OF`, also update the date in the page footer.
 
## Author
 
**Tamiko Eto, MA, CIP**
Founder and Principal Consultant, TechInHSR LLC
 
© 2026 TechInHSR LLC
 
Claude finished the response
