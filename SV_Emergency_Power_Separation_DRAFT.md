# S / V Emergency Power Separation: DRAFT Scope Narrative

**Site:** Cherokee plant, 3300 S. 2nd St., St. Louis MO
**Driver:** Divestiture. **NewCo** acquires **V** and **N** buildings. **RemainCo** keeps everything else, including **S**.
**Target end state:** Each building gets its **own generator and its own transfer equipment**. No emergency or standby conductors cross the S/V ownership line.
**Status:** DRAFT. The S and V prints are not in hand yet. Everything marked **TBD** must be confirmed from prints or field survey.
**Companion workbook:** [SV_Emergency_Load_List_and_Sizing.xlsx](./SV_Emergency_Load_List_and_Sizing.xlsx) contains the load list, generator/ATS sizing, and circuit move list.

---

## 1. How it's tied together now

### 1a. S and V (as reported. No S or V prints are in this folder yet.)
- **One generator → one ATS → emergency distribution feeding both S and V.**
- The generator carries life-safety egress lighting (NEC 700), fire alarm and/or fire pump, process loads, HVAC/AHUs/exhaust, cold storage/chillers, and IT/DeltaV/controls/UPS.
- Problems with the current arrangement (they matter for the separation, and RemainCo should know about them too):
  1. **Mixed loads on one ATS.** NEC 700.5(D) says transfer equipment serving emergency (700) loads may serve *only* emergency loads. If egress lighting really is on the same ATS as process and HVAC, that is a likely existing non-compliance. The new V design must split it.
  2. **One ATS senses one normal source.** If S and V have different normal feeds, losing the unsensed building's normal power will not start the generator for that building.
  3. **The feeder crosses buildings, and soon crosses owners.** After closing, one company's building would depend on equipment in the other company's building. That needs a transition services agreement (TSA) and access rights until it is cut.
- **TBD:** where the generator and ATS physically sit (at S or at V). Ownership usually follows the building. This plan assumes they stay with **S (RemainCo)** and NewCo builds new for V. If they are at V, the roles flip.

### 1b. Building N (from the prints in this folder; N also goes to NewCo)
| Item | What the prints show | Carve-out question |
|---|---|---|
| **3GEN-0015-ESG01** | Cutler-Hammer Pow-R-Line 800A generator switchboard, N3 electrical room (east bay) (10-055-E100) | **Which generator feeds it, and where is that generator?** Not shown on these prints. Does it also feed any RemainCo building? |
| ATS04, ATS05, **ATS-N3-EB** | In the N3 electrical room. ATS-N3-EB normal comes from **DP-7** (3rd floor, column W/8) | Trace DP-7, DP-8, DP-10, and DP-5 upstream on the 15-039 plant one-lines. Do they pass through RemainCo switchgear or utility service? |
| Standby panels | SPP-N3-EB, SPP-N3-EB-SUB (480V), SRP-N3-EB (208/120), SLP-N3-EB, 3GEN-0015-PAN01, PAN04 | None. These are internal to N. |
| **ATS07 → PAN10 → XFMR06 → PAN11 → UPS 3PS-0002 → 3PAN-UP02** | 18-2038-E-50. Normal side from DP-10. **Emergency side is an "existing portable generator… provided by others… located by existing exterior generator."** | **Who owns that portable generator and that exterior generator?** If RemainCo owns them, 3AHU-0711, its exhaust fans, TCU-2011, and UPS 3PS-0002 lose their backup at closing. |
| Egress lighting, N3 Area 3 | EM/NL fixtures plus EL1 battery units on lighting panel 3PAN-0706 (0001-E09). These are battery-backed. | Confirm that all of N uses battery egress lighting, or identify what is on generator. |
| DeltaV | UPS UP-01, power strip PP-N3039-01 PS1, controllers in N1046 (CC-502-02) and PP-N3035-01. Network ties to the "plant network" | OT/IT network separation is a parallel carve-out item. |

> **Note:** DeltaV_Device_Register.docx contains errors. Its "PST network" entry is actually **PS1 power-strip ports**, and its controller rooms (VT88/VTO2/A0365/DK2/DK3) don't match the drawings. Don't rely on it.

---

## 2. Concept one-lines

**Today (as reported):**
```
            S BUILDING (RemainCo)                      V BUILDING (NewCo)
   Normal (S) ──┐                                Normal (V) ──► V normal dist.
                │ (ATS senses ONE normal source)
   EXISTING GEN ─► EXISTING ATS ─► EM distribution ─┬─► S: egress, FA, process, HVAC...
                                                    └──────── feeder crosses S/V line ───► V: egress, FA, fire pump?,
                                                                                            process, HVAC, cold storage, IT/UPS
```

**Target (separate generator and transfer equipment per building):**
```
   S BUILDING (RemainCo)                          V BUILDING (NewCo)
   Normal (S)                                     Normal (V, NewCo-owned source)
       │                                             │            │             │
   EXISTING GEN-S                                GEN-V (new) + portable-generator docking station (NEC 700.3(F))
       │                                             │
   ┌───┴──────────┐                       ┌──────────┼──────────────┐
 ATS-S-EM     ATS-S-SB                 ATS-V-EM    ATS-V-SB        FPTS-V
 (700)        (701/702)                (700 only)  (702 / 701)     (695, only if V has a fire pump)
   │            │                         │           │               │
 S life       S standby               V egress    V process, HVAC,  Fire pump
 safety       loads                   lighting,   cold storage,     controller
                                      FA (*)      IT/DeltaV/UPS

   (*) Option: put V egress lighting on battery units and the FACP on its own batteries.
       Then V may need no 700 ATS at all, and the generator becomes 702 (plus 701 if required). Big cost lever.
   No emergency or standby conductors cross the S/V line.
```

**Alternative to evaluate before buying a generator:** V and N are both NewCo. If V is close to N and N's generator system (ESG01, 800A) has spare capacity, feeding V's standby from N could be cheaper than a new generator. This only works if N's generator is itself NewCo-owned (see 1b).

---

## 3. Scope narrative (phased)

**Phase 0: Agreements and data (now)**
- Confirm from the purchase agreement asset schedule who owns the existing generator, ATS, fuel tank, and the portable generator referenced on 18-2038-E-50.
- Put the shared-generator period into the **TSA**. Cover access, testing (NFPA 110 monthly exercise), maintenance, fuel, lockout/tagout coordination, outage notice, and an end date.
- Collect the data in Section 6. Start a **30-day power logger** on V's feeder at the shared ATS load side, ideally in summer (NEC 220.87 method).
- Open an **MOC / change control** record (GMP site: product impact, validation, environmental monitoring).

**Phase 1: Design (engineer of record)**
- Load list and classification of every V load as 700, 701, 702, or 695. Use the workbook.
- Generator: size, fuel (diesel or natural gas), runtime and tank size, pad location, clearances, exhaust, noise, fuel delivery access. Run the manufacturer's sizing software for voltage dip and harmonics.
- Transfer equipment: ATS-V-EM (700 only), ATS-V-SB, and FPTS-V if there is a fire pump. Set withstand/close-on ratings against available fault current. Choose 3-pole or 4-pole based on the grounding scheme (NEC 250.30 vs. 250.35, plus ground-fault protection).
- **Normal-side sources for the new ATSs must come from distribution NewCo will own.** Coordinate with the normal-power/utility separation workstream so nothing has to be re-terminated later.
- Short-circuit, selective coordination (NEC 700.32 / 701.32), and arc flash study for V. RemainCo updates S's study after V's load comes off.
- Permits: City of St. Louis electrical and building, air permit for the generator (EPA NSPS Subpart IIII / NESHAP ZZZZ, state and city air program, coordinated by EHS), SPCC update if the fuel tank pushes aboveground oil storage over 1,320 gal, and insurer review.

**Phase 2: Procurement.** Generators and switchgear are long-lead items, so get budget quotes early. If closing comes before delivery, plan a **rental generator on a docking station** as the bridge.

**Phase 3: Install (existing system stays live).** Build the pad, generator, fuel system, and ATS(s), and pull new feeders. Energize the normal sides. Label everything.

**Phase 4: Test before cutover.** NFPA 110 acceptance testing (including full-load and load-bank tests), transfer and retransfer timing (700 loads ≤10 s, NEC 700.12), fire pump acceptance if applicable, and verification of controls and alarms.

**Phase 5: Cutover.** Detailed method of procedure (MOP) required. Outline:
1. Notify the AHJ, fire alarm monitoring company, insurer (impairment notice), RemainCo, production/QA, and IT/DeltaV.
2. Temporary measures: fire watch while fire protection or alarm is impaired, portable egress lighting, product protection and temperature monitoring for cold storage, and confirmation of DeltaV/UPS ride-through or a controlled shutdown.
3. Lock out V's feeder at the shared ATS load side and verify it is dead. Re-terminate V's emergency distribution to ATS-V-EM and ATS-V-SB.
4. Energize on normal, then do a pull-the-plug test: open normal and verify GEN-V picks up within the required times. Retransfer.
5. RemainCo removes or abandons V's feeder at the shared equipment. The shared ATS now serves S only.

**Phase 6: Closeout.** As-built one-lines and panel directories, arc flash labels, NEC 225.37 plaques updated or removed, NFPA 110 maintenance program and records set up under NewCo, and close the MOC.

---

## 4. Code and standards checklist (engineer to confirm against the adopted editions)
- **NEC 700** Emergency: separate transfer equipment (700.5(D)), separate wiring (700.10(B)), ≤10 s (700.12), selective coordination (700.32), temporary source connection for maintenance (700.3(F))
- **NEC 701 / 702** legally required and optional standby. **NEC 695 / NFPA 20** fire pump, listed fire pump transfer switch, ≤15% voltage drop while starting (695.7)
- **NEC 225.30 / 225.37** multiple feeders to a building and identification plaques (applies during the interim period)
- **NEC 250.30**, separately derived systems (affects 3-pole vs. 4-pole ATS). **NEC 110.16 / NFPA 70E** arc flash labeling after changes
- **NFPA 110** (Level 1 for life safety, Type 10), **NFPA 101** (egress lighting 90 min), **NFPA 72** (fire alarm secondary power)
- Environmental: generator air permit, SPCC. Insurer requirements.

---

## 5. Generator and ATS sizing method
See the **Sizing** sheet in the workbook. In short:
1. Enter every V emergency/standby load (or panel totals) with its NEC class, assigned ATS, type, HP or kW, and transfer step.
2. The sheet totals demand by ATS, gives the ATS amps (×1.25) and the next standard ATS size, and gives the generator kW at ≤80% loading and the next standard size.
3. The step-loading table shows the worst-case kVA during motor starts. Compare it to the genset's motor-starting kVA at the allowed voltage dip.
4. Replace the estimates with real data where possible: the 30-day logger, motor locked-rotor data, and UPS/VFD vendor data. Final selection goes through the genset manufacturer's software.

---

## 6. Data needed (S and V prints and field survey)
- [ ] S and V one-lines, both normal and emergency
- [ ] Generator nameplate: kW/kVA, voltage, fuel, tank size, location, age, NFPA 110 level, service records
- [ ] ATS nameplate: amps, poles, WCR, make/model, location, **which normal source it senses**, open or closed transition
- [ ] Every panel downstream of the ATS, with schedules, and which building each panel is in
- [ ] Routing and size of the S↔V emergency feeder(s)
- [ ] Fire pump (if any): HP, controller, current normal and alternate sources, and **whether it serves both S and V** (water supply is a carve-out issue on its own)
- [ ] Fire alarm panels serving V and their power sources. Is the fire alarm system site-wide or per building?
- [ ] Egress lighting type in V: generator-fed or battery units?
- [ ] 12 months of generator/ATS load data, or the 30-day logger results
- [ ] Available fault current at the proposed new ATS locations, and the existing short-circuit/arc flash study
- [ ] Site plan for the new generator pad
- [ ] Building N: the generator feeding ESG01, ownership of the portable/exterior generator on 18-2038-E-50, and the upstream sources for DP-5, DP-7, DP-8, and DP-10 (15-039 plant one-lines)

## 7. Open questions
1. Where are the existing generator and ATS physically located, and who gets them under the deal?
2. Closing date versus the realistic generator delivery date? This decides whether a rental generator bridge is needed.
3. Does V have its own fire pump, or share the site fire pump?
4. Is V's egress lighting on the generator, or could it move to battery units (which removes the need for a 700 ATS)?
5. Does Building N's emergency system depend on anything RemainCo keeps?
