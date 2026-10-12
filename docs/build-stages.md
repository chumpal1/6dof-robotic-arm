# Build Stages — 6-DOF Robotic Arm

Stage-by-stage guide covering what to print, what to order, and what to do after each part comes off the build plate.

---

## Stage 1 — Base

### Print Settings
| Setting | Value |
|---------|-------|
| Printer | Bambu Lab P1S |
| Filament | PLA Basic (Orange) |
| Layer Height | 0.20mm |
| Initial Layer Height | 0.30mm |
| Infill | 50% Honeycomb |
| Supports | Auto (touching buildplate only) |
| Estimated Time | ~5h 20m |
| Estimated Weight | ~620g |

### Parts Needed for This Stage
| Part | Part Number | Source | Qty |
|------|-------------|--------|-----|
| M3 Brass Heat-Set Inserts (100-pack) | 94180A331 | McMaster-Carr | 4 per base |
| M3 × 8mm Socket Head Cap Screws | 91290A115 | McMaster-Carr | 4 per base |
| M3 × 6mm Socket Head Cap Screws | 91290A111 | McMaster-Carr | 4 per base |
| M3 Flat Washers | 91166A210 | McMaster-Carr | 8 per base |
| M3 Hex Nuts | 90695A033 | McMaster-Carr | 4 per base |
| 608-2RS Sealed Ball Bearing (8×22×7mm) | 5972K501 | McMaster-Carr | 1 |
| NEMA 17 Stepper Motor (17HS4401) | — | Amazon | 1 |
| Heat-Set Insert Tool (soldering iron tip) | — | Amazon | 1 (shared) |
| 4.2mm Drill Bit | — | Hardware store | 1 (shared) |

### Post-Print Checklist
- [ ] Remove support material from motor cavity
- [ ] Test-fit NEMA 17 motor body in cavity (should slide in with light friction)
- [ ] Verify pilot boss recess (23mm dia, 2.5mm deep) aligns with motor face boss
- [ ] Verify connector notch (25mm × 15mm × 10mm) clears 6-pin wire connector on motor side
- [ ] Drill bolt holes to 4.2mm if printed at 3.2mm (use 4.2mm drill bit — #19 numbered bit)
- [ ] Press heat-set inserts into 4.2mm holes using soldering iron at ~200°C
- [ ] Verify 608-2RS bearing seats flush in bearing recess
- [ ] Thread M3 screws through motor face into heat-set inserts — confirm snug fit

### Key Dimensions (at 0.55 scale)
| Feature | Dimension |
|---------|-----------|
| Base outer width | ~220mm |
| Motor cavity | 42 × 42 × 40mm deep |
| Pilot boss recess | 23mm dia × 2.5mm deep |
| Bolt pattern (center to center) | 22mm (11mm from shaft center to each bolt) |
| Counterbore entrance | 6mm dia × 3.5mm deep |
| Counterbore shaft | 4.2mm dia |
| Wire channel | 15mm dia minimum |
| Connector notch | 25mm × 15mm × 10mm deep |

---

## Stage 2 — Shoulder Joint

### Print Settings
| Setting | Value |
|---------|-------|
| Printer | Bambu Lab P1S |
| Filament | PLA Basic (Orange or Black) |
| Layer Height | 0.20mm |
| Infill | 50% Honeycomb |
| Supports | As needed |

### Parts Needed for This Stage
| Part | Part Number | Source | Qty |
|------|-------------|--------|-----|
| M3 Brass Heat-Set Inserts | 94180A331 | McMaster-Carr | 4 |
| M3 × 8mm Socket Head Cap Screws | 91290A115 | McMaster-Carr | 4 |
| 608-2RS Sealed Ball Bearing | 5972K501 | McMaster-Carr | 1 |
| NEMA 17 Stepper Motor | — | Amazon | 1 |

### Motor Mount Configuration — Shoulder
The shoulder uses a **side-mount** configuration rather than end-mount:
- Motor bolts to the **flat side face** of the shoulder link
- Recess: 42 × 42mm footprint, 3mm deep into the face
- Shaft hole: 6mm dia, all the way through
- Bolt holes: 4× at 11mm from shaft center, 4.2mm dia, 8mm deep with heat-set inserts
- Motor shaft protrudes through and connects directly to the upper arm link

### Post-Print Checklist
- [ ] Test-fit motor in side-face recess
- [ ] Verify 6mm shaft hole is clear and aligned
- [ ] Verify bearing seat at base connection point
- [ ] Install heat-set inserts into bolt holes
- [ ] Mount motor and confirm shaft protrudes cleanly to opposite side

---

## Stage 3 — Elbow, Forearm, Wrist, Gripper

> These stages follow the same general pattern as the shoulder. Specific dimensions and motor mount configurations will be added as each joint is designed and validated.

### Parts Needed (Per Joint)
| Part | Part Number | Source | Qty |
|------|-------------|--------|-----|
| M3 Brass Heat-Set Inserts | 94180A331 | McMaster-Carr | 4 |
| M3 × 8mm Socket Head Cap Screws | 91290A115 | McMaster-Carr | 4 
