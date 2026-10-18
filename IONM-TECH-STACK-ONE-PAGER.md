# IONM TECH STACK — ONE-PAGER
**MediHomeCare Inc · Pennsylvania LLC · Internal Technical Briefing**
*Audience: 30-person tech + hardware team · Design principle: minimal human input, everything as a tech stack*
*Revisit: Tuesday Oct 20, 2026 · Calendar event: "IONM Tech Stack — Revisit One-Pager"*

---

## 1. WHAT WE'RE BUILDING
A four-layer software stack that turns an in-house group of CNIM technologists + existing IONM hardware into a billable, low-touch operation. No new training program. No in-house DABNM physician. Interpretation is subcontracted per case (IntraNerve Neuroscience is the first partner — they explicitly sell remote professional interpretation to IONM companies). We supply the technical component; they supply the reading layer.

## 2. LAYER 1 — REMOTE SUPERVISION + HIPAA AUDIT (Phase 1, highest priority)
**Problem:** Payers (Premera, EmblemHealth, Blue Cross Illinois) now require, for remote billing under CPT 95941, a continuous HIPAA-compliant live data feed with defined max interruption tolerance + documented fallback, bi-directional audio, live video of the exact waveforms the tech sees, timestamped records of every reader↔surgeon communication, and start/stop times matching across 95940/95941. Most shops meet this with Zoom + hope.
**Build:** Signal streaming service (Cadwell Cascade SDK first — published SDK, mature third-party ecosystem), secure screenshare relay, bi-directional audio bridge, cryptographic timestamp log of every interaction, auto-generated payer-ready audit trail export.
**Billable:** 95941 remote professional component. Subscription to other IONM companies: blended $10–20/case (ionm.ai charges $3–4/case for AI docs alone; remote supervision module $8–15/case).
**Why us:** Our techs generate ground-truth documentation as cases happen — billing starts from source, not reconstruction.

## 3. LAYER 2 — AI SIGNAL LAYER (Phase 2)
**Problem:** Remote readers covering 3–4 rooms waste physician minutes sorting real neurological change from technical noise (electrode pops, movement, anesthesia drift). Cadwell/Natus bolt AI onto their own hardware only.
**Build:** Standalone artifact-vs-event classifier + urgency ranking that runs on ANY OEM feed. Cadwell Cascade SDK for v1. Model trained on our techs' annotations (real vs noise + why) across thousands of cases — data no hardware vendor can replicate because theirs is locked to their machines.
**Pricing:** $25–50/reader-seat/month. Moat = proprietary labeled dataset from in-house ground truth.
**MVP cost:** Near-zero hardware (we already have it). ~$5k: CNIM annotation stipend for ~100 labeled cases + cloud storage bucket + GPU rental. Milestone = one external company asking to pilot.

## 4. LAYER 3 — SCHEDULING + MATCHING (Phase 3)
**Problem:** Every IONM company matches techs to cases via spreadsheets and phone calls — availability × travel radius × case type × hospital credentialing status. No dispatcher software exists for this niche.
**Build:** Auto-matching engine + real-time backfill when a tech calls out. Sellable to smaller IONM shops that can't afford a human dispatcher.

## 5. LAYER 4 — PAYER + DENIAL INTELLIGENCE (Phase 4, compounding)
**Problem:** IONM billing is uniquely brutal — 95940/95941 split, no-overlap rule, concurrency limits on rooms per physician. Denials + appeals eat 10–20% of collections.
**Build:** Track denial patterns by insurer × state × code; log which documentation wins appeals; feed results back into billing config and tech training in real time. Every denied case becomes training data.

## 6. COST STACK (cost-plus MSO model — flat fee or cost-plus, FMV-documented annually)
Technologist wages $40–50/hr + ~30% payroll burden · malpractice + workers' comp · equipment depreciation/lease · disposables ~$200–400/case · remote physician fee $150–300/case (IntraNerve subcontract) OR $0 if hospital already has a reader · RCM/billing software or outsourced partner · credentialing · travel. Assure's all-in delivery cost target: under $1,100/patient. Build the plus on top of that documented base.

## 7. MARKET SNAPSHOT
- US IONM volume: ~1–1.5M cases/year. Remote share: 32% now → ~48% by 2034.
- Global market: $3.6–4.5B (2025) → $5–7.5B early 2030s, 5–7% CAGR. North America ~half.
- Outsourced monitoring growing >7%/yr; in-house ~60% but concentrated in academic centers.
- Sweet spot: community hospitals + ASCs under 200 monitored cases/yr — outsourcing cuts per-case cost ~18% vs in-house.
- Competitors: SpecialtyCare (500+ surgical neurophysiologists, 42 states, Joint Commission), Assure/MPOWERHealth, Accurate Neuromonitoring (Fairfield NJ — 195 staff, 500+ surgeons, 11 states), IntraNerve, United Medical Monitoring (Melville NY), NW Monitoring.
- Our edge: regional density within 30 mi of Two Bala Plaza (Bucks/Philly), WBE + MBE certs for hospital supplier-diversity programs, existing PA DOH/PROMISE regulatory footprint, in-house hardware + software capability.

## 8. NEAR-TERM ACTIONS
1. Amend MediHomeCare LLC purpose (PA Dept of State) — home care → healthcare staffing.
2. Malpractice $1M/$3M with tail + workers' comp healthcare codes + dishonesty bond.
3. Recruit 2–3 CNIM techs in Bucks/Montgomery/Philly at $58–75/hr W-2 + mileage.
4. First equipment: one refurbished Cadwell Cascade (~$5–10k) + service contract + supplies → $30–50k all-in (not $100k+ new).
5. First design partner for Layer 2: one friendly CNIM at a local ASC annotating ~100 cases.
6. First external pilot conversation: IntraNerve (they post surgical neurophysiologist roles in Philadelphia at $75–100k — local demand, possibly stretched in-room coverage).
7. Tuesday Oct 20 revisit: finalize one-pager, assign owners per layer.

## 9. WHAT THIS IS NOT
- Not a training program (partner with IntraNerve/Axis-style programs; we cover trainee salary during 9–12 mo, they handle didactic/clinical structure).
- Not an in-house DABNM hire ($290–400k/yr scarce) — subcontract interpretation per case.
- Not a percentage-of-collections MSO — cost-plus or flat fee only, FMV memo on file.
- Not competing with Cadwell/Natus on hardware AI — standalone cross-OEM layer they structurally cannot build.