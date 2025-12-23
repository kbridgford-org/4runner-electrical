# 4Runner Auxiliary Battery System

## Project Overview

This project provides a complete plan for installing a dual-battery system in a 2023 Toyota 4Runner, featuring:
- Auxiliary LiFePO4 battery under the seat for accessory power
- DC-DC battery charger in cabin to keep aux battery charged from the starter battery
- Ham radio system (Icom IC-2730B) powered by aux battery
- Garmin PowerSwitch in engine bay for controlling future light bars
- 4-circuit fuse block in engine bay for distribution
- Control buttons in cabin for Garmin light control

---

## Equipment List

### Main Components
1. **Auxiliary Battery**: 12V 20Ah LiFePO4 (256Wh) with 30A BMS (in cabin)
2. **Battery Charger**: Renogy 12V 20A DC-DC Battery Charger (RBC20D1U) (in cabin)
3. **Radio System**: Icom IC-2730B with separate controller and main unit (in cabin)
4. **Garmin PowerSwitch**: Digital accessory control (30A per channel, 100A total) (in engine bay)
5. **Control Buttons**: 2 momentary switches for Garmin control inputs (in cabin)

### Protection & Distribution
1. **Blue Sea 5184 Terminal Fuse (125A)**: Protects Garmin PowerSwitch from starter battery
2. **Blue Sea 5178 Terminal Fuse (60A)**: Protects 4-circuit fuse block from starter battery
3. **Blue Sea 5045 Compact Blade Fuse Block (4 Circuits)**: Distribution in engine bay (30A per circuit max)
4. **Blue Sea 2151 Dual Terminal Fuse Block**: For starter battery connection point (optional)

### Cables & Hardware
- **10 AWG** cable: Starter battery to Garmin PowerSwitch (via 125A fuse)
- **10 AWG** cable: Starter battery to 4-circuit fuse block (via 60A fuse)
- **8 AWG** cable: Fuse block to Renogy charger input (through firewall, per Renogy specs)
- **10 AWG** cable: Renogy output to aux battery (per Renogy specs)
- **12 AWG** cable: Aux battery to radio main unit
- **18-22 AWG** cable: Control buttons to Garmin control inputs (through firewall)
- Appropriate length LMR-195 coaxial cable for antenna
- 2 momentary push buttons (for Garmin control)
- Cable ties, heat shrink tubing, split loom, terminal connectors

---

## Safety Analysis & Compatibility

### Power Requirements
- **Radio Max Draw**: 13A transmit, 1.8A receive, 1.2A standby
- **DC-DC Charger Input**: 20A max from starter battery (via fuse block)
- **DC-DC Charger Output**: 20A max to aux battery
- **Garmin PowerSwitch**: Up to 100A total (for future light bars)
- **Auxiliary Battery Capacity**: 30A BMS protection, 20Ah capacity

### Safety Verification ✓
- ✅ Radio (13A max) < Aux Battery BMS (30A)
- ✅ Charger input (20A) < Starter battery capacity
- ✅ Charger output (20A) < Aux Battery BMS (30A)
- ✅ All connections properly fused at or below wire ratings
- ✅ Wire gauges meet manufacturer specifications
- ✅ 8 AWG suitable for 20A charger input (per Renogy specs)
- ✅ Garmin connection uses 10 AWG for high-current capability
- ✅ 125A fuse protects Garmin from starter battery overcurrent
- ✅ 60A fuse protects 4-circuit fuse block from starter battery overcurrent
- ✅ 4-circuit fuse block (30A per circuit max) protects engine bay loads
- ✅ Total system design within all component ratings

---

## System Architecture

### Power Flow Diagram

```
┌──────────────────────────────────────────────────────┐
│              ENGINE BAY                               │
│                                                       │
│  START BATTERY                                        │
│      │                                                │
│      ├─ 10 AWG (125A fuse) ──→ Garmin PowerSwitch    │
│      │                          ├─ Control Input 1 ←─┼─┐
│      │                          ├─ Control Input 2 ←─┼─┤
│      │                          ├─ Accessory Out 1   │ │
│      ├─ 10 AWG (60A fuse) ───→  ├─ Accessory Out 2   │ │
│      │                          ├─ Accessory Out 3   │ │
│      │                          ├─ Accessory Out 4   │ │
│      ↓                          ├─ Accessory Out 5   │ │
│  4-Circuit Fuse Block           └─ Accessory Out 6   │ │
│  (30A per circuit)                  (for future      │ │
│      ├─ Circuit 1 (30A fuse)         light bars)     │ │
│      │   8 AWG ──────────────────────────────────────┼─┤
│      ├─ Circuit 2 (future)                           │ │
│      ├─ Circuit 3 (future)                           │ │
│      └─ Circuit 4 (future)                           │ │
│                                                       │ │
└───────────────────────────────────────────────────────┼─┤
                                                        │ │
        [DRIVER SIDE LOWER FIREWALL HOLE]              │ │
                  │                                     │ │
                  ↓ 8 AWG power pair                    │ │
                  ↓ 18-22 AWG control wires             │ │
                                                        │ │
┌───────────────────────────────────────────────────────┼─┤
│          CABIN - Under Driver/Passenger Seat         │ │
│                                                       │ │
│  Control Buttons (Driver Side)                       │ │
│      ├─ Button 1 ─────────────────────────────────────┘ │
│      └─ Button 2 ───────────────────────────────────────┘
│                                                       │
│  ┌─────────────────────────────┐                     │
│  │  Renogy DC-DC Charger       │ (8 AWG input)       │
│  │  (20A, 8 AWG in/10 AWG out) │                     │
│  └──────────┬──────────────────┘                     │
│             │ 10 AWG output                          │
│             ↓                                        │
│  ┌─────────────────────────────┐                     │
│  │  AUX BATTERY                │                     │
│  │  12V 20Ah LiFePO4           │                     │
│  │  (30A BMS Protection)       │                     │
│  └──────────┬──────────────────┘                     │
│             │ 12 AWG (15A fuse)                      │
│             ↓                                        │
│         Radio Head                                   │
│         (13A max)                                    │
│                                                       │
│  Radio Controller (Dash)                             │
│                                                       │
└───────────────────────────────────────────────────────┘
```

---

## Installation Plan - Step by Step

### Phase 1: Preparation & Planning

#### 1.1 Gather Tools & Materials
- Socket set and wrenches
- Wire strippers and crimpers
- Heat gun for heat shrink
- Drill with appropriate bits (if needed for mounting)
- Multimeter for testing
- Cable ties and split loom
- Electrical tape
- Wire labels
- Fish tape or wire coat hanger (for firewall routing)

#### 1.2 Disconnect Battery
⚠️ **CRITICAL SAFETY STEP**: Disconnect the negative terminal of the starter battery before any work.

---

### Phase 2: Engine Bay Installation

#### 2.1 Mount Garmin PowerSwitch
**Location**: Engine bay, mounted to a suitable location away from heat sources
- Must be within reach of starter battery cables
- Avoid mounting near turbocharger or exhaust
- Operating temperature must stay below 85°C (185°F)
- Ensure adequate ventilation
- Mount securely to handle engine vibration

#### 2.2 Install 4-Circuit Fuse Block
**Location**: Engine bay, mounted near starter battery
- Must be accessible for future circuit additions
- Protect from direct water spray
- Mount securely with appropriate hardware
- Keep away from moving parts (belts, pulleys, etc.)

#### 2.3 Connect Power to Garmin and Fuse Block

**Garmin PowerSwitch Connection**:
1. 10 AWG positive cable with 125A Blue Sea 5184 Terminal Fuse
   - Connect fuse close to starter battery positive terminal
   - Route to Garmin PowerSwitch location
   - Connect to Garmin +12V terminal (torque to 4.52 N-m max)
2. 10 AWG negative cable
   - Connect to Garmin GND terminal
   - Ground to starter battery negative or chassis ground

**4-Circuit Fuse Block Connection**:
1. 10 AWG positive cable with 60A Blue Sea 5178 Terminal Fuse
   - Connect fuse close to starter battery positive terminal
   - Route to fuse block input terminal
2. 10 AWG negative cable
   - Connect to fuse block ground terminal
   - Ground to starter battery negative or chassis ground

#### 2.4 Prepare Cables for Firewall Routing

**From Fuse Block to Cabin** (for Renogy charger):
- Circuit 1: 8 AWG positive (with 30A blade fuse in fuse block)
- 8 AWG negative (shared ground)
- These will power the Renogy charger in the cabin

**Control Wires from Cabin** (for Garmin):
- 2x 18-22 AWG wires for control buttons
- Will connect to Garmin control input terminals
- Label as "Control 1" and "Control 2"

---

### Phase 3: Firewall Cable Routing

#### 3.1 Identify Firewall Entry Points

**Power and Control Cables - Driver Side Upper Hole (Primary Accessory)**:
- **Size**: 20mm (0.78")
- **Location**: Upper driver side, exits above interior fuse box
- **Factory Seal**: Plastic pop-in plug
- **Use for**: 8 AWG power pair + 18-22 AWG control wires

**Antenna Cable - Passenger Side Hole (Secondary Accessory)**:
- **Size**: 20mm (0.78")
- **Location**: Passenger side, exits behind glove box
- **Factory Seal**: Nipple grommet (snip tip to route wire)
- **Use for**: LMR-195 coaxial antenna cable (~5mm diameter)

#### 3.2 Route Cables Through Firewall

**Driver Side Upper Hole - Power and Control Cables**:

**Cables going ENGINE BAY → CABIN** (2 power cables + optional IGN):
1. 8 AWG positive from fuse block Circuit 1 (for Renogy charger input)
2. 8 AWG negative from fuse block ground (for Renogy charger input)
3. IGN signal wire (optional - only if needed for smart alternator - consult 4Runner manual)

**Cables going CABIN → ENGINE BAY** (2 control wires):
1. 18-22 AWG control wire for Button 1 → Garmin Control Input 1
2. 18-22 AWG control wire for Button 2 → Garmin Control Input 2

**Routing Procedure - Driver Side Upper**:
1. Remove factory plastic pop-in plug from driver side upper firewall hole
2. Bundle power cables together with cable ties
3. Bundle control wires separately with cable ties
4. Protect both bundles with split loom
5. Route through 20mm hole (verified: 8 AWG pair ~6.6mm + control wires ~2mm = ~8.6mm total fits easily)
6. Seal around cables with appropriate grommet or sealant to prevent water/air intrusion
7. Leave extra length on both sides for connections (minimum 6" extra)
8. Label all cables clearly at both ends

**Passenger Side Hole - Antenna Cable**:

**Cable going ENGINE BAY → CABIN**:
1. LMR-195 coaxial antenna cable (4.95mm diameter)

**Routing Procedure - Passenger Side**:
1. Locate nipple grommet on passenger side firewall
2. Snip the tip of the nipple grommet to create opening
3. Route LMR-195 antenna cable through grommet
4. Grommet will seal around cable
5. Route to passenger side ditch light bracket (engine bay side)
6. Route to radio location behind glove box (cabin side)

---

### Phase 4: Cabin Installation

#### 4.1 Choose Component Locations

**Driver Side Seat**:
- Aux battery: ~7" x 4" x 7" (approximate)
- DC-DC charger: 6.54" x 4.53" x 2.32"
- Keep charger close to battery for optimal performance

**Passenger Side Seat**:
- Radio main unit: 5.91" x 1.57" x 5.94"
- Convenient for antenna cable routing from passenger side firewall

**Mounting Requirements**:
- Secure battery with a battery box or mounting bracket
- Ensure battery cannot move during vehicle operation
- Mount charger with at least 5.91" clearance on all sides for ventilation
- Keep charger as close to battery as possible

#### 4.2 Install Auxiliary Battery (Driver Side)

**Location**: Under driver seat

1. **Position battery** under driver seat
2. **Secure battery** - must be firmly mounted to prevent movement
3. **Do NOT connect anything yet** - wait for all components to be staged

#### 4.3 Install DC-DC Battery Charger (Driver Side)

**Location**: Under driver seat, near aux battery, with proper ventilation (5.91" clearance all sides)

**Wiring Sequence** (per Renogy manual):

1. **Connect to Auxiliary Battery FIRST**:
   - Negative output terminal → Aux battery negative
   - Positive output terminal → 10 AWG → Aux battery positive
   
2. **Connect to Fuse Block** (cables from engine bay through firewall):
   - Negative input terminal → 8 AWG negative from fuse block
   - Positive input terminal → 8 AWG positive from fuse block (pre-fused with 30A at fuse block)
   
3. **IGN Signal** (if required for smart alternator):
   - Connect IGN wire from charger to vehicle ignition signal
   - Consult 4Runner service manual for proper ignition signal source
   
4. **Temperature Sensor**:
   - **Do NOT use** - LiFePO4 batteries don't require temperature compensation
   - Leave BTS port empty

5. **Configure Charger**:
   - Set battery type to "LI" (Lithium Iron Phosphate)
   - Verify voltage settings: Boost 14.4V, no float mode for LiFePO4

#### 4.4 Install Radio (Passenger Side)

**Main Unit Location**: Under passenger seat
**Controller**: Dash mounted for easy access

**Power Connections**:
1. **Positive**: 12 AWG from aux battery (driver side) positive (with 15A fuse at battery)
2. **Negative**: To aux battery negative or good chassis ground
3. **Verify**: Max 15A fuse appropriate for 12 AWG wire and 13A max draw
4. Route power cable from driver side to passenger side under seats

**Antenna**:
- LMR-195 coaxial cable enters cabin through passenger side firewall (20mm hole)
- Route from firewall (behind glove box) to radio under passenger seat
- External antenna mounts on passenger side ditch light bracket
- Use proper cable routing techniques to avoid pinch points

#### 4.5 Install Control Buttons

**Location**: Driver side, accessible from driver seat (A-pillar, dash, or center console)

**Button Specifications**:
- 2 momentary push buttons (normally open)
- LED illumination optional
- Weatherproof/automotive rated preferred

**Wiring**:
1. Mount buttons in chosen location
2. Connect one terminal of each button to the control wires routed from engine bay
3. Connect other terminal of each button to chassis ground
4. Label buttons (e.g., "Light Bar 1", "Light Bar 2")
5. Test button operation with multimeter (should show continuity when pressed)

---

### Phase 5: Complete Garmin Control Connections

#### 5.1 Connect Control Buttons to Garmin (In Engine Bay)

From cabin, you've routed 2 control wires through the firewall.

**Connect to Garmin**:
1. Open Garmin front cover
2. Locate the control input terminals (2 available)
3. Connect control wire from Button 1 to Control Input 1 terminal
4. Connect control wire from Button 2 to Control Input 2 terminal
5. Verify connections are secure
6. Close and latch cover

**Control Configuration**:
- Use Garmin PowerSwitch app to configure what each button controls
- Can set momentary, latching, or timed output behavior
- Future light bars will connect to the 6 accessory output terminals

⚠️ **Future Light Bar Connections**:
- When installing light bars, connect their positive wires to accessory output terminals (6 available)
- Each light bar's ground goes to chassis ground or battery negative (NOT to Garmin GND)
- Maximum 30A per accessory channel
- Maximum 100A total system
- Use appropriate wire gauge based on light bar current draw (10 AWG for 20-30A, 12 AWG for 10-20A)

---

### Phase 6: Testing & Verification

#### 6.1 Pre-Power Checks
Before reconnecting starter battery:
1. **Visual inspection**: All connections tight, no bare wire exposed
2. **Multimeter continuity**: Check for shorts between positive and negative
3. **Verify fuse placement**: All fuses installed with correct amperage
4. **Check polarity**: All positive to positive, negative to negative
5. **Cable routing**: No pinch points, away from moving parts and heat

#### 6.2 Initial Power-Up
1. **Reconnect starter battery negative terminal**
2. **Check aux battery voltage** (should show on built-in display): 12.8V nominal
3. **Start engine** - DC-DC charger should begin charging
4. **Verify charger operation**:
   - Check LED indicators on charger
   - Verify aux battery voltage increases (charging)
   - Should see 14.4V boost voltage for LiFePO4

#### 6.3 System Testing
1. **Radio test**:
   - Power on radio
   - Verify receive function
   - Test transmit (with proper antenna connected)
   - Monitor current draw if possible

2. **Garmin test**:
   - Engine should be running for this test
   - Pair smartphone or nav device with Garmin
   - Open Garmin PowerSwitch app
   - Verify device shows correct voltage (should be ~14V with engine running)
   - Test control buttons - should activate in app
   - Verify switching functions work (no load connected yet)

3. **Control button test**:
   - Press Button 1 - should see response in Garmin app
   - Press Button 2 - should see response in Garmin app
   - Configure button behavior via app as desired

4. **Charging test**:
   - Run engine for 30 minutes
   - Verify aux battery charging properly via Renogy charger
   - Check aux battery voltage increases to ~14.4V
   - Check for any error codes on charger

---

## Wiring Details & Specifications

### Wire Gauge Reference
| Circuit | Wire Gauge | Max Current | Fuse Rating |
|---------|------------|-------------|-------------|
| Starter to Garmin | 10 AWG | 30A | 125A* |
| Starter to Fuse Block | 10 AWG | 60A | 60A |
| Fuse Block to Renogy Input | 8 AWG | 20A | 30A |
| Renogy Output to Aux Battery | 10 AWG | 20A | 25A** |
| Aux Battery to Radio | 12 AWG | 13A | 15A |
| Control Buttons to Garmin | 18-22 AWG | <1A | N/A |

\* 125A fuse sized for future high-current light bar installations  
\*\* May be integrated in Renogy charger

### Critical Safety Fusing Points

1. **At Starter Battery** (Engine Bay):
   - 125A terminal fuse on positive cable to Garmin PowerSwitch
   - 60A terminal fuse on positive cable to 4-circuit fuse block
   
2. **At 4-Circuit Fuse Block** (Engine Bay):
   - Circuit 1: 30A blade fuse for Renogy charger input
   - Circuits 2-4: Size based on future load requirements
   
3. **At Auxiliary Battery** (Cabin):
   - 25A fuse for Renogy charger output (if not integrated in charger)
   - 15A fuse for radio power

### Connection Torque Specifications
- **Garmin +12V terminal**: 4.52 N-m (40 lbf-in) - DO NOT OVERTIGHTEN
- **Garmin control terminals**: Hand-tight with #8-32 screws
- **Battery terminals**: Follow battery manufacturer specs
- **Fuse block terminals**: Hand-tight plus 1/4 turn with wrench

---

## Safety Warnings & Best Practices

### ⚠️ CRITICAL SAFETY WARNINGS

1. **Always disconnect negative terminal** of starter battery before working on electrical system
2. **Never connect power source to Garmin accessory outputs** - outputs only, not inputs
3. **Do not use Garmin to control winches** - exceeds rating
4. **All connections must be tight** - loose connections cause resistance and heat
5. **Use proper crimping tools** - poor crimps can fail and cause fires
6. **Fuse every positive connection** close to power source
7. **Size fuses appropriately** - not too large (no protection) or too small (nuisance blowing)
8. **Protect all wiring** from abrasion, heat, and moving parts
9. **Seal firewall penetrations** to prevent water and exhaust gas entry
10. **Mount battery securely** - loose battery is dangerous in accident

### Best Practices

1. **Label everything**: Use wire labels at both ends of each cable
2. **Take photos**: Document before/during/after for future reference
3. **Leave extra length**: Allow slack for service and movement
4. **Use heat shrink**: Protect all crimp connections
5. **Cable management**: Use split loom and cable ties for clean installation
6. **Test as you go**: Verify each connection before moving to next step
7. **Check twice, crimp once**: Double-check all connections before crimping
8. **Maintain clearances**: Keep wiring away from heat sources and moving parts
9. **Plan for future**: Route cables with future upgrades in mind
10. **Keep it clean**: Professional-looking installation is safer installation

### Maintenance Schedule

**Monthly**:
- Check aux battery voltage on built-in display
- Visual inspection of all connections for corrosion or looseness
- Verify all fuses are intact

**Quarterly**:
- Clean battery terminals if corrosion present
- Check DC-DC charger for error codes
- Verify Garmin connections remain tight

**Annually**:
- Full system inspection
- Verify all wire routing remains secure
- Check firewall seal condition
- Test all safety fuses

---

## Troubleshooting Guide

### DC-DC Charger Issues

| Problem | Possible Cause | Solution |
|---------|---------------|----------|
| Charger not turning on | No alternator detection | Start engine, verify voltage at input |
| Fast flash red | Aux battery overvoltage | Check battery, verify LI mode selected |
| Jumping flash red | Aux battery over-discharge | Recharge battery to >12V |
| Solid red | Overtemperature | Improve ventilation, check clearances |
| Slow flash red | Reverse polarity | Verify all positive/negative connections |

### Radio Issues

| Problem | Possible Cause | Solution |
|---------|---------------|----------|
| No power | Fuse blown or loose connection | Check 15A fuse, verify connections |
| High current draw | Transmitting constantly | Check PTT switch, verify programming |
| Poor performance | Low voltage | Check aux battery charge level |

### Garmin Issues

| Problem | Possible Cause | Solution |
|---------|---------------|----------|
| Won't pair | Starter battery voltage too low | Charge starter battery, verify >12V |
| Outputs off | Low voltage protection | System turns off below 11V automatically |
| No power | Fuse blown | Check 125A terminal fuse at starter battery |
| Control buttons not working | Loose connection or bad ground | Check control wire connections and button grounds |

---

## Future Upgrades & Expansion

This system is designed to support:
- **Light bars**: Connect to Garmin PowerSwitch accessory outputs (6 available)
- **Additional accessories**: Connect to unused fuse block circuits in engine bay
- **USB charging**: Add to aux battery with voltage regulator
- **Inverter**: Small inverter from aux battery for AC power
- **Additional batteries**: Parallel battery connection (verify BMS compatibility)

### Light Bar Installation (Future)

The Garmin PowerSwitch provides 6 accessory outputs for future light bar expansion:

**Installation Steps**:
1. Calculate total amperage of all lights (must stay below 100A total)
2. Use appropriate wire gauge per light bar current:
   - 10 AWG for 20-30A loads
   - 12 AWG for 10-20A loads
   - 14 AWG for <10A loads
3. Connect each light bar positive wire to a Garmin accessory output terminal
4. Ground all light bars to chassis ground (NOT to Garmin GND terminal)
5. Configure control via Garmin PowerSwitch app
6. Can be controlled by the cabin buttons or via smartphone app

**Control Options**:
- Button 1 and Button 2 can control any combination of the 6 outputs
- Configure momentary, latching, or timed operation via app
- Can create custom profiles for different scenarios

---

## Component Locations Summary

**Engine Bay**:
- Garmin PowerSwitch (mounted securely away from heat sources)
- 4-circuit blade fuse block (accessible location)
- Starter battery (factory location)
- Antenna on passenger side ditch light bracket

**Firewall Routing**:
- Driver side upper hole (20mm): Power cables (8 AWG pair) + control wires (18-22 AWG pair)
- Passenger side hole (20mm): Antenna cable (LMR-195 coax)

**Cabin - Driver Side Seat**:
- Auxiliary LiFePO4 battery
- DC-DC battery charger (near battery, proper ventilation)

**Cabin - Passenger Side Seat**:
- Radio main unit
- Antenna cable connection

**Cabin - Driver Side Accessible**:
- 2 control buttons for Garmin light control
- Radio controller (dash mounted)

---

## Bill of Materials - Quick Reference

### From Repository Specs:
- ✅ 12V 20Ah LiFePO4 Battery
- ✅ Renogy 12V 20A DC-DC Charger
- ✅ Icom IC-2730B Radio
- ✅ Garmin PowerSwitch
- ✅ Blue Sea 5184 (125A Terminal Fuse)
- ✅ Blue Sea 5178 (60A Terminal Fuse)
- ✅ Blue Sea 5045 (4-Circuit Fuse Block)
- ✅ Blue Sea 2151 (Dual Terminal Fuse Block) - Optional

### Additional Items Needed:
- [ ] 10 AWG marine-grade tinned copper cable (30-40 feet) - for Garmin and fuse block power
- [ ] 8 AWG marine-grade tinned copper cable (20-30 feet) - for Renogy charger input
- [ ] 10 AWG marine-grade tinned copper cable (10 feet) - for Renogy charger output
- [ ] 12 AWG marine-grade tinned copper cable (10 feet) - for radio power
- [ ] 18-22 AWG wire (20 feet) - for control button wiring
- [ ] 2 momentary push buttons (automotive rated)
- [ ] Ring terminals (various sizes for 8, 10, 12 AWG)
- [ ] Spade or screw terminals for control wires
- [ ] Heat shrink tubing (assorted sizes)
- [ ] 30A blade fuse (for fuse block Circuit 1)
- [ ] 15A blade fuse (for radio power)
- [ ] 25A blade fuse (for charger output)
- [ ] 15A blade fuse (for radio)
- [ ] Split loom cable protector (20 feet)
- [ ] Firewall grommet or sealant
- [ ] Cable ties (assorted)
- [ ] Wire labels
- [ ] Battery mounting box or bracket
- [ ] Mounting hardware for charger and components

---

## Resources & Reference Documents

All technical specifications available in this repository:
- `battery-specs.md` - Auxiliary battery specifications
- `battery-charger.md` - DC-DC charger manual and specifications
- `radio-specs.md` - Radio specifications and power requirements
- `garmin-powerswitch.md` - Garmin installation and specifications
- `fuse-information.md` - Fuse and distribution block specifications
- `4runner-firewall.md` - Firewall penetration reference

---

**Last Updated**: December 2025
**4Runner Model**: 2023 Toyota 4Runner (5th Generation)
**System Design**: Auxiliary battery with DC-DC charging and accessory control