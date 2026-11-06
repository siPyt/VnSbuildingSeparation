# S / V Emergency Power Separation: DRAFT Scope Narrative

**Site:** Cherokee plant, 3300 S. 2nd St., St. Louis MO
**Driver:** Divestiture. **NewCo** acquires **V** and **N** buildings. **RemainCo** keeps everything else, including **S**.
**Target end state:** Each building gets its **own generator and its own transfer equipment**. No emergency or standby conductors cross the S/V ownership line.
**Status:** DRAFT. The combined MSOL set and the E001 site plan now provide S/V normal-power feeder references and one emergency-source lead (3GEN-002N); the S/V emergency-power arrangement and as-built conditions are still unverified. Everything marked **TBD** must be confirmed from current prints or field survey.
**Companion workbook:** [SV_Emergency_Load_List_and_Sizing.xlsx](./SV_Emergency_Load_List_and_Sizing.xlsx) contains the load list, generator/ATS sizing, and circuit move list.

---

## 1. How it's tied together now

### 1a. S and V (reported emergency arrangement; normal feeder references and one emergency-source lead found)
- **One generator → one ATS → emergency distribution feeding both S and V.**
- **Drawing-based normal-power finding:** 15-039-E073 shows both S and V fed from 3XFMR-0021 / SWBD #6: a 200A branch to V (continuation E078) and a branch toward S (continuation E076) marked 800A, 3-pole, with 300A also shown at the protective device. Do not treat the 800A marking alone as available capacity. E078 identifies V panel 3PAN-V-0001 / DP-1. E077 identifies S panel 3PAN-XXX1; the referenced E076 feeder continuation is not in the supplied MSOL set. These are normal-power references and do not verify the reported shared emergency source.
- The supplied MSOL set does not establish an S/V shared generator or ATS on the S/V normal one-lines. Keep the reported emergency arrangement as unverified until its source and ATS sheets are identified.
- **Drawn emergency-source lead (3GEN-002N):** 15-039-E073 shows an 800A branch from SWBD #6 "TO 3GEN-002N-ATS08" (continuation E099), and 15-039-E028 shows a 60A branch from 3PAN-0378 (in the room labeled "BUILDING S MEZZANINE," fed from N's DP-5) "TO 3GEN-002N-ATS10" (continuation E101). Neither continuation sheet is in the set, and the 3GEN-002N generator sheets (E102, E103) are blank placeholders. On E001 (revision 4), a 3GEN-002N leader points to a generator-type unit in the yard beside the SWBD#6 and 3XFMR-0021 footprints, with CAM LOK BOX #1 and #2 leaders to the same unit. If one generator serves both ATSs (an inference from the tags), it would tie the SWBD #6 system (S/V) to N's DP-5 system. Its rating, fuel, location, and loads are **TBD**.
- **Where SWBD #6 sits:** 15-039-E078 says SWBD #6 is "within Bldg P," and E073 also shows a branch "TO BLDG P" (continuation E074, absent). E001 has SWBD#6 and 3XFMR-0021 callouts in the yard beside the generator-type unit above, but it does not letter its buildings or define what its leaders point to, so it cannot settle where SWBD #6 sits. A separate "3XFMR-0021 SWBD 6" callout on E001 has four leaders to unlabeled footprints (see 1c). The physical location of SWBD #6 and the ownership of Bldg P are **TBD**.
- **N-to-S normal-power ties as drawn:** 15-039-E028 shows N's DP-5 feeding 3PAN-0378 in the "BUILDING S MEZZANINE" room, and 15-039-E058 shows N's SWBD #5 feeding 3PAN-0055 with a breaker "TO FUTURE 125A PANEL S BLDG." The sheets do not define these labels. If they mean the S that stays with RemainCo, S has normal-power dependencies on distribution that goes to NewCo. No S-to-N tie was found.
- The generator carries life-safety egress lighting (NEC 700), fire alarm and/or fire pump, process loads, HVAC/AHUs/exhaust, cold storage/chillers, and IT/DeltaV/controls/UPS.
- Problems with the current arrangement (they matter for the separation, and RemainCo should know about them too):
  1. **Mixed loads on one ATS.** NEC 700.5(D) says transfer equipment serving emergency (700) loads may serve *only* emergency loads. If egress lighting really is on the same ATS as process and HVAC, that is a likely existing non-compliance. The new V design must split it.
  2. **One ATS senses one normal source.** If S and V have different normal feeds, losing the unsensed building's normal power will not start the generator for that building.
  3. **The feeder crosses buildings, and soon crosses owners.** After closing, one company's building would depend on equipment in the other company's building. That needs a transition services agreement (TSA) and access rights until it is cut.
- **TBD:** where the generator and ATS physically sit (at S or at V). Ownership usually follows the building. This plan assumes they stay with **S (RemainCo)** and NewCo builds new for V. If they are at V, the roles flip. The E001 site plan does not letter its buildings, so it cannot place them by itself, and it is unconfirmed whether the 3GEN-002N unit it draws is the S/V generator.

### 1b. Building N (from the prints in this folder; N also goes to NewCo)
| Item | What the prints show | Carve-out question |
|---|---|---|
| **3GEN-0015-ESG01** | 10-055-E100 is described as an 800A generator switchboard. MSOL 15-039-E062 shows a 750kW 3GEN-0015 standby generator feeding ESG01, labeled 1200A, 480/277V, 3-phase, 4-wire, 25kAIC. | The 800A / 1200A drawing discrepancy needs nameplate and field verification. The one-line does not establish ownership or spare capacity. |
| ATS04, ATS05, **ATS-N3-EB** | In the N3 electrical room. ATS-N3-EB normal source is **DP-7**; 15-039-E069 shows its emergency source as **3GEN-0015-ESG01**. | DP-5, DP-7, DP-8, and DP-10 trace upstream on the 15-039 plant one-lines to 3SW-0700 (E025) through SWBD #2 and SWBD #1, with no SWBD #6 dependency drawn. Verify ownership of that service and any other boundary dependencies. DP-5 also feeds panel 3PAN-0378 in the room labeled "BUILDING S MEZZANINE" (see 1a). |
| Standby panels | SPP-N3-EB, SPP-N3-EB-SUB (480V), SRP-N3-EB (208/120), SLP-N3-EB, 3GEN-0015-PAN01, PAN04 | None. These are internal to N. |
| **ATS07 / emergency loads** | MSOL 15-039-E068 shows normal from DP-10, emergency from 3GEN-0015-ESG01, and a 100A ATS. 18-2038-E-50 shows a 150A ATS supplied by an existing portable 480V generator provided by others. E062 marks the ATS07 feeder breaker 400AF / 150AT (identified by position), which matches E-50's 150A rather than E068's 100A. | The drawings conflict on ATS07's emergency source and ATS rating. Verify ATS identity, current revision, and field connection before assigning the source or ownership. |
| Egress lighting, N3 Area 3 | EM/NL fixtures plus EL1 battery units on lighting panel 3PAN-0706 (0001-E09). These are battery-backed. | Confirm that all of N uses battery egress lighting, or identify what is on generator. |
| DeltaV | UPS UP-01, power strip PP-N3039-01 PS1, controllers in N1046 (CC-502-02) and PP-N3035-01. Network ties to the "plant network" | OT/IT network separation is a parallel carve-out item. |

> **Note:** DeltaV_Device_Register.docx contains errors. Its "PST network" entry is actually **PS1 power-strip ports**, and its controller rooms (VT88/VTO2/A0365/DK2/DK3) don't match the drawings. Don't rely on it.

**Additional MSOL generator findings:** 15-039-E062 identifies 3GEN-0015 as a 750kW standby generator feeding 3GEN-0015-ESG01, shown as 1200A. Sheets 15-039-E068 and E069 show 3GEN-0015-ESG01 as the emergency source for ATS07 and ATS-N3-EB, respectively. This conflicts with 18-2038-E-50, which shows ATS07 as a 150A ATS supplied from an existing portable generator provided by others; E068 labels ATS07 100A (an earlier version of this draft said 1000A in error), while the E062 feeder breaker to ATS07 is marked 400AF / 150AT (identified by position), which matches E-50's 150A. The sheets must be reconciled; none of these ratings or source descriptions are field-verified. The earlier 10-055-E100 description of ESG01 as 800A also differs from the 1200A shown on 15-039-E062.

### 1c. Site-level items from the E001 site plan
15-039-E001 (Cherokee Plant Electrical Site Location Plan, revision 4, 06-16-26) is a site location plan. Its own general note 1 says it is not as-built, and it does not letter its buildings, so by itself it cannot show which footprint is S, V, or N. Building north is up the page and true north points toward the upper left, so this section describes places by page position, not compass direction. Details and sheet cross-references are in [DRAWING_ANSWERS.txt](./DRAWING_ANSWERS.txt) (answers 8, 9, 11, and 13).

| Item | What the prints show | Carve-out question |
|---|---|---|
| **3GEN-002N** | See 1a. E001 has two 3GEN-002N labels: one with a leader to a generator-type unit in the yard beside the SWBD#6 and 3XFMR-0021 callouts (with CAM LOK BOX #1 and #2 leaders to the same unit), and one at the left side of the plan with a long leader to an unidentified footprint. | Confirm which unit is 3GEN-002N, its rating, fuel, and location, what ATS08 and ATS10 serve, and who owns it. |
| **Docking station / 3GEN-0003** | E001 revision 4 draws, in the lower middle of the plan, an electrical platform with 3SWBD-0009 and 3GEN-0003-SWBD01 ("BOTTOM FED"), a cable tray to a 3GEN-0003 footprint, a splice box with Polaris lugs for a future cam lock box tie-in, and an ATS controls box. E058 and E107 show SWBD #9 (3000A, via 3XFMR-0034) fed from the same Ameren service entrance (3SWBD-0008) as N's SWBD #5, with breakers to 3GEN-0003-ATS01 to ATS04 (E108 to E111, absent). | What is installed, what it serves, and who owns it are not shown. A docking station is already drawn, so check it before designing a new one for V. The service entrance shared with N's SWBD #5 is a normal-power dependency to untangle. |
| **Fire pump house** | E001 shows a fire pump controller, a jockey pump controller, a main service disconnect, and a pole-mounted 3XFMR-FIRE. E096 shows 3XFMR-FIRE (112.5kVA) on its own Ameren service, with no generator or ATS. | The buildings it serves are not shown (see Q3 in Section 7). |
| **Unlettered areas** | The only area labels on E001 are BUILDING XY, TANK FARM, BLDG T VALVE HOUSE, and two GUARD SHACKs. The blank 3GEN-002N sheets (E102, E103) also show building "X/Y." | Get a building-lettered site plan or a leader legend before assigning any E001 footprint to S, V, or N. |
| **Multi-leader callouts** | E001's "3XFMR-0021 SWBD 6" callout has four leaders ending in four unlabeled footprints in the middle of the plan, and "3XFMR-0022 SWBD 2" has two. One leader from each ends inside the same large rectangular outline just right of the plan's center. | The sheet does not say whether these leaders mark equipment location or areas served. Check them on the site walk. If they mark areas served, one footprint would be reached from both SWBD #2 (N) and SWBD #6 (S/V). |

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

**Phase 2: Procurement.** Generators and switchgear are long-lead items, so get budget quotes early. If closing comes before delivery, plan a **rental generator on a docking station** as the bridge. E001 revision 4 already draws a generator docking station in the lower middle of the plan (3GEN-0003, see 1c). Find out what it is, what it serves, and who owns it before designing a new one for V.

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
- [ ] S/V emergency one-lines and any ATS/generator sheets. Normal feeder references are present on 15-039-E073/E077/E078, but the sheets they point to are not in the supplied set: E074 (Bldg P), E076 (S feeder), E099 (3GEN-002N-ATS08), and E101 (3GEN-002N-ATS10). E102/E103 (3GEN-002N) are blank placeholders, and E108 to E111 (3GEN-0003-ATS01 to ATS04) are also absent.
- [ ] 3GEN-002N: which unit on the site it is, its nameplate (kW/kVA, fuel, location), and what ATS08 and ATS10 serve
- [ ] 3GEN-0003 docking station (E001 revision 4): what is installed, what ATS01 to ATS04 serve, and who owns it
- [ ] A building-lettered site plan or leader legend for E001 (it is not as-built and does not letter its buildings)
- [ ] Generator nameplate: kW/kVA, voltage, fuel, tank size, location, age, NFPA 110 level, service records
- [ ] ATS nameplate: amps, poles, WCR, make/model, location, **which normal source it senses**, open or closed transition
- [ ] Every panel downstream of the ATS, with schedules, and which building each panel is in
- [ ] Routing and size of the S↔V emergency feeder(s)
- [ ] Fire pump (if any): HP, controller, current normal and alternate sources, and **whether it serves both S and V** (water supply is a carve-out issue on its own)
- [ ] Fire alarm panels serving V and their power sources. Is the fire alarm system site-wide or per building?
- [ ] Egress lighting type in V: generator-fed or battery units?
- [ ] 12 months of generator/ATS load data, or the 30-day logger results
- [ ] Available fault current at the proposed new ATS locations, and the existing short-circuit/arc flash study
- [ ] Site plan for the new generator pad. E001 is the current base plan, but it is not as-built.
- [ ] Building N: the generator feeding ESG01, ownership of the portable/exterior generator on 18-2038-E-50, and who owns the two Ameren services that feed N's boards (3SW-0700 on E025 for DP-5, DP-7, DP-8, and DP-10; 3SWBD-0008 on E058 for SWBD #5)
- [ ] N-to-S ties: what "BUILDING S MEZZANINE" (E028) and "S BLDG" (E058) mean in the field, and whether panel 3PAN-0378 and the future 125A panel exist and what they serve

## 7. Open questions
1. Where are the existing generator and ATS physically located, and who gets them under the deal? Is the 3GEN-002N unit that E001 draws beside SWBD #6 that generator?
2. Closing date versus the realistic generator delivery date? This decides whether a rental generator bridge is needed.
3. Does V have its own fire pump, or share the site fire pump? (E001 and E096 show a site fire pump house on its own 3XFMR-FIRE service with no generator or ATS drawn; the buildings it serves are not shown.)
4. Is V's egress lighting on the generator, or could it move to battery units (which removes the need for a 700 ATS)?
5. Does Building N's emergency system depend on anything RemainCo keeps?
6. Does S depend on anything NewCo gets? E028 and E058 draw normal-power feeds from N distribution to panels labeled for S (see 1a).
7. Who owns the Ameren service entrance 3SWBD-0008, which feeds both N's SWBD #5 and the 3GEN-0003 docking station's SWBD #9 (E058)?
