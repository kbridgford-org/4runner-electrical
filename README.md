# 4Runner Auxiliary Battery System

## Project Overview

This project provides a complete plan for installing a dual-battery system in a 2023 Toyota 4Runner, featuring:
- Auxiliary LiFePO4 battery under the seat for accessory power
- DC-DC battery charger to keep aux battery charged from the starter battery
- Ham radio system (Icom IC-2730B) powered by aux battery
- Garmin PowerSwitch for controlling light bars and accessories

---

## Equipment List

### Main Components
1. **Auxiliary Battery**: 12V 20Ah LiFePO4 (256Wh) with 30A BMS
2. **Battery Charger**: Renogy 12V 20A DC-DC Battery Charger (RBC20D1U)
3. **Radio System**: Icom IC-2730B with separate controller and main unit
4. **Garmin PowerSwitch**: Digital accessory control (30A per channel, 100A total)

### Protection & Distribution
1. **Blue Sea 5184 Terminal Fuse (125A)**: Protects Garmin PowerSwitch from aux battery
2. **Blue Sea 5178 Terminal Fuse (60A)**: Protects 4-circuit fuse block from aux battery
3. **Blue Sea 5045 Compact Blade Fuse Block (4 Circuits)**: Protects cabin accessories
4. **Blue Sea 2151 Dual Terminal Fuse Block**: For aux battery connection point (optional)

### Cables & Hardware
- **8 AWG** cable: Starter battery to charger input (per Renogy specs)
- **10 AWG** cable: Charger output to aux battery (per Renogy specs)
- **10 AWG** cable: Aux battery to Garmin PowerSwitch (for high-current loads)
- **10 AWG** cable: Aux battery to 4-circuit fuse block (via 60A fuse)
- **10 AWG** cable: 4-circuit fuse block to DC-DC charger input
- **12 AWG** cable: Radio main unit power connection
- Appropriate length LMR-195 coaxial cable for antenna
- Cable ties, heat shrink tubing, split loom, terminal connectors

---

## Safety Analysis & Compatibility

### Power Requirements
- **Radio Max Draw**: 13A transmit, 1.8A receive, 1.2A standby
- **DC-DC Charger Draw**: 20A max output from aux battery
- **Garmin PowerSwitch**: Up to 100A total (will be used for future light bars)
- **Auxiliary Battery Capacity**: 30A BMS protection, 20Ah capacity

### Safety Verification ✓
- ✅ Radio (13A max) < Aux Battery BMS (30A)
- ✅ Charger output (20A) < Aux Battery BMS (30A)
- ✅ All connections properly fused at or below wire ratings
- ✅ Wire gauges meet manufacturer specifications
- ✅ Garmin connection uses 10 AWG for high-current capability
- ✅ 125A fuse protects Garmin from overcurrent
- ✅ 60A fuse protects 4-circuit fuse block
- ✅ 4-circuit fuse block (30A per circuit max) protects cabin loads
- ✅ Total system design within all component ratings

---

## System Architecture

### Power Flow Diagram

```
START BATTERY (Engine Bay)
        │
        │ 8 AWG (through firewall)
        ↓
    [DRIVER SIDE LOWER FIREWALL HOLE]
        │
        ↓
┌───────────────────────────────────────────┐
│      CABIN - Under Driver/Passenger Seat  │
│                                           │
│   ┌─────────────────────────────┐        │
│   │  4-Circuit Blade Fuse Block │        │
│   │  (30A per circuit max)       │        │
│   │  (powered by 60A fuse)       │        │
│   └──────────┬──────────────────┘        │
│              │ 10 AWG                     │
│              ↓                            │
│   ┌─────────────────────────────┐        │
│   │  Renogy DC-DC Charger       │        │
│   │  (20A, 8 AWG in/10 AWG out) │        │
│   └──────────┬──────────────────┘        │
│              │ 10 AWG                     │
│              ↓                            │
│   ┌─────────────────────────────┐        │
│   │  AUX BATTERY                │        │
│   │  12V 20Ah LiFePO4           │        │
│   │  (30A BMS Protection)       │        │
│   └──┬────┬──────────────────┬──┘        │
│      │    │                  │           │
│      │    │ 12 AWG           │ 10 AWG    │
│      │    │                  │ (60A fuse)│
│      │    ↓                  ↓           │
│      │  Radio              4-Circuit     │
│      │  (13A max)          Fuse Block    │
│      │                                   │
│      │ 10 AWG (125A fuse)                │
│      │ (through firewall)                │
└──────┼───────────────────────────────────┘
       ↓
   [DRIVER SIDE LOWER FIREWALL HOLE]
       │
       ↓
┌──────────────────────────────┐
│   ENGINE BAY                 │
│                              │
│   ┌────────────────────┐     │
│   │ Garmin PowerSwitch │     │
│   │ (125A fused)       │     │
│   │ For light bars     │     │
│   └────────────────────┘     │
│                              │
└──────────────────────────────┘
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

### Phase 2: Engine Bay Installation (Garmin PowerSwitch)

#### 2.1 Mount Garmin PowerSwitch
**Location**: Engine bay, mounted to a suitable location away from heat sources
- Must be within reach of battery cables
- Avoid mounting near turbocharger or exhaust
- Operating temperature must stay below 85°C (185°F)
- Ensure adequate ventilation

#### 2.2 Prepare Garmin Power Cables (For Future Light Bars)
This cable will run FROM the aux battery TO the Garmin:

1. **Primary Power Channel**:
   - 10 AWG positive cable with 125A Blue Sea 5184 Terminal Fuse
   - Connect fuse close to aux battery positive terminal
   - Route through firewall (driver side lower hole)

2. **Ground**:
   - 10 AWG negative cable
   - Will connect to Garmin GND terminal
   - Ground at aux battery negative terminal in cabin

⚠️ **NOTE**: Do NOT connect these to the Garmin yet - cables will be routed first, then connected in Phase 4

---

### Phase 3: Firewall Cable Routing

#### 3.1 Identify Firewall Entry Point
**Use**: Driver Side Lower Firewall Hole (Clutch Master area)
- **Size**: 45-50mm (1.75-2")
- **Location**: Lower driver side, exits near parking brake inside cabin
- **Best for**: Large battery and power cables

#### 3.2 Route Cables Through Firewall

**Cables going ENGINE BAY → CABIN** (3 cables):
1. 8 AWG positive from starter battery (for charger input)
2. 8 AWG negative from starter battery (for charger input)
3. IGN signal wire (if needed for smart alternator - consult 4Runner manual)

**Cables going CABIN → ENGINE BAY** (2 cables):
1. 10 AWG positive with 125A fuse (Garmin power)
2. 10 AWG negative (Garmin ground)

**Routing Procedure**:
1. Remove factory plug/seal from driver side lower firewall hole
2. Bundle cables together with cable ties
3. Protect cable bundle with split loom
4. Use fish tape or coat hanger to guide bundle through
5. Seal around cables with appropriate grommet or sealant to prevent water/air intrusion
6. Leave extra length on both sides for connections (minimum 6" extra)

---

### Phase 4: Cabin Installation

#### 4.1 Choose Seat Location
**Primary Option**: Under driver seat (more accessible)
**Alternative**: Under passenger seat if space limited

**Space Requirements**:
- Aux battery: ~7" x 4" x 7" (approximate)
- DC-DC charger: 6.54" x 4.53" x 2.32"
- Radio main unit: 5.91" x 1.57" x 5.94"
- 4-circuit fuse block: compact

**Mounting**:
- Secure battery with a battery box or mounting bracket
- Ensure battery cannot move during vehicle operation
- Mount charger with at least 5.91" clearance on all sides for ventilation
- Keep charger as close to battery as possible

#### 4.2 Install Auxiliary Battery

1. **Position battery** under chosen seat
2. **Secure battery** - must be firmly mounted to prevent movement
3. **Do NOT connect anything yet** - wait for all components to be staged

#### 4.3 Install DC-DC Battery Charger

**Location**: Near aux battery, with proper ventilation (5.91" clearance all sides)

**Wiring Sequence** (per Renogy manual):

1. **Connect to Auxiliary Battery FIRST**:
   - Negative output terminal → Aux battery negative
   - Positive output terminal → 10 AWG → Aux battery positive
   
2. **Connect to Starter Battery** (cables from engine bay):
   - Negative input terminal → 8 AWG negative from starter battery
   - Positive input terminal → 8 AWG positive from starter battery (pre-fused at starter battery)
   
3. **IGN Signal** (if required for smart alternator):
   - Connect IGN wire from charger to vehicle ignition signal
   - Consult 4Runner service manual for proper ignition signal source
   
4. **Temperature Sensor**:
   - **Do NOT use** - LiFePO4 batteries don't require temperature compensation
   - Leave BTS port empty

5. **Configure Charger**:
   - Set battery type to "LI" (Lithium Iron Phosphate)
   - Verify voltage settings: Boost 14.4V, no float mode for LiFePO4

#### 4.4 Install 4-Circuit Blade Fuse Block

**Location**: Accessible under seat, near battery

**Connections**:
1. **Input Power**:
   - Positive: 10 AWG from aux battery positive (with 60A Blue Sea 5178 Terminal Fuse at battery)
   - Negative: Connect to aux battery negative

2. **Output Circuits** (load side - 30A max per circuit):
   - **Circuit 1**: DC-DC charger input power (8 AWG from starter battery)
   - **Circuit 2**: Future accessory
   - **Circuit 3**: Future accessory
   - **Circuit 4**: Future accessory

**Fusing**:
- Circuit 1: 30A blade fuse (for charger input line)
- Other circuits: Size based on future load requirements

**Note**: The 60A terminal fuse at the battery protects the entire fuse block and all downstream loads.

#### 4.5 Install Radio

**Main Unit**: Under same seat as battery (if space allows), otherwise under other seat
**Controller**: Dash mounted for easy access

**Power Connections**:
1. **Positive**: 12 AWG from aux battery positive (with 15A fuse at battery or fuse block)
2. **Negative**: To aux battery negative or good chassis ground
3. **Verify**: Max 13A fuse appropriate for 12 AWG wire and 13A max draw

**Antenna**:
- Route LMR-195 coaxial cable to passenger side ditch light bracket
- Use proper cable routing techniques to avoid pinch points
- May route through door jamb or under trim panels

---

### Phase 5: Complete Garmin PowerSwitch Connections

#### 5.1 Connect Power to Garmin (In Engine Bay)

From cabin, you've routed:
- 10 AWG positive with 125A fuse (for power)
- 10 AWG negative (ground)

**Connect to Garmin**:
1. Open Garmin front cover
2. Connect large ring end of ground wire to GND terminal on Garmin
3. Connect 125A fused positive to +12V terminal (torque to 4.52 N-m max)
4. Close and latch cover

⚠️ **Future Light Bar Connections**:
- When installing light bars, connect their positive wires to the accessory terminals
- Each light bar's ground goes to chassis ground or battery negative (NOT to Garmin)
- Maximum 30A per accessory channel
- Maximum 100A total system
- The Garmin has 4 accessory channels available for future use

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
   - Pair smartphone or nav device
   - Open Garmin PowerSwitch app
   - Verify device shows correct voltage and amperage
   - Test switching functions (no load connected yet)

3. **Charging test**:
   - Run engine for 30 minutes
   - Verify aux battery charging properly
   - Check for any error codes on charger

---

## Wiring Details & Specifications

### Wire Gauge Reference
| Circuit | Wire Gauge | Max Current | Fuse Rating |
|---------|------------|-------------|-------------|
| Starter to Charger Input | 8 AWG | 20A | 30A |
| Charger to Aux Battery | 10 AWG | 20A | 25A |
| Aux Battery to Radio | 12 AWG | 13A | 15A |
| Aux Battery to Garmin | 10 AWG | 30A | 125A* |
| Aux Battery to Fuse Block | 10 AWG | 60A | 60A |

\* 125A fuse sized for future high-current light bar installations

### Critical Safety Fusing Points

1. **At Starter Battery** (Engine Bay):
   - 30A fuse on positive cable going to DC-DC charger
   
2. **At Auxiliary Battery** (Cabin):
   - 25A fuse for DC-DC charger output (if not integrated in charger)
   - 15A fuse for radio power
   - 125A terminal fuse for Garmin PowerSwitch
   - 60A terminal fuse for 4-circuit fuse block input

3. **At 4-Circuit Fuse Block**:
   - Individual blade fuses per circuit (size based on load)
   - Recommended: 30A for charger input circuit

### Connection Torque Specifications
- **Garmin +12V terminal**: 4.52 N-m (40 lbf-in) - DO NOT OVERTIGHTEN
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
| Won't pair | Battery voltage too low | Charge batteries, verify >12V |
| Outputs off | Battery protection mode | System turns off below 11V automatically |
| No power | Fuse blown | Check 125A terminal fuse |

---

## Future Upgrades & Expansion

This system is designed to support:
- **Light bars**: Connect to Garmin PowerSwitch accessory outputs
- **Additional radios**: Connect to 4-circuit fuse block (verify current capacity)
- **USB charging**: Connect to fuse block with voltage regulator
- **Inverter**: Small inverter from aux battery for AC power
- **Additional batteries**: Parallel battery connection (verify BMS compatibility)

### Light Bar Installation (Future)
When installing light bars:
1. Calculate total amperage of all lights
2. Ensure total stays below 100A Garmin limit
3. Use appropriate wire gauge per light bar specs
4. Connect positive to Garmin accessory terminal
5. Ground light bars to chassis (NOT to Garmin)
6. Program Garmin app for control

---

## Component Locations Summary

**Engine Bay**:
- Garmin PowerSwitch (mounted securely away from heat)
- Antenna on passenger side ditch light bracket
- Starter battery (factory location)

**Firewall**:
- Driver side lower hole for all cable routing

**Cabin - Under Seat(s)**:
- Auxiliary LiFePO4 battery (primary seat)
- DC-DC battery charger (near battery)
- 4-circuit blade fuse block (accessible)
- Radio main unit (if space allows, else under other seat)
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
- [ ] 8 AWG marine-grade tinned copper cable (20-30 feet)
- [ ] 10 AWG marine-grade tinned copper cable (40-50 feet)
- [ ] 12 AWG marine-grade tinned copper cable (10 feet)
- [ ] Ring terminals (various sizes for 8, 10, 12 AWG)
- [ ] Heat shrink tubing (assorted sizes)
- [ ] 30A ANL fuse (for starter battery positive)
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

## Project Timeline

**Estimated Installation Time**: 8-12 hours for beginner

**Day 1** (4-6 hours):
- Phase 1: Preparation
- Phase 2: Engine bay work
- Phase 3: Firewall routing

**Day 2** (4-6 hours):
- Phase 4: Cabin installation
- Phase 5: Final connections
- Phase 6: Testing

**Recommended Approach**: 
- Take your time
- Test each phase before proceeding
- Don't rush - safety first
- Take breaks to avoid mistakes from fatigue

---

## Support & Questions

Before starting:
1. Read all reference documents in this repository
2. Review complete plan twice
3. Gather all materials and tools
4. Work in good lighting
5. Have a helper available if possible

During installation:
- Reference this document at each step
- Take photos as you go
- Double-check all connections
- Test before moving to next phase

---

**Last Updated**: December 2025
**4Runner Model**: 2023 Toyota 4Runner (5th Generation)
**System Design**: Auxiliary battery with DC-DC charging and accessory control