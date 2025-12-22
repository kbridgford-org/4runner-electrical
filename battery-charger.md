# Renogy 12V 20A DC-DC Battery Charger (RBC20D1U)

This manual outlines the operation and maintenance for the **Renogy 12V 20A DC-DC Battery Charger**. This device uses smart control technology to charge a 12V auxiliary battery from your vehicle's starter battery while driving.

---

## 1. General Information

**Charging Efficiency:** Offers up to 94% charging efficiency and over 90% efficiency for voltage boosting.
**Compatibility:** Designed for 12V systems and compatible with both traditional and smart alternators.
**Supported Auxiliary Batteries:** GEL, Flooded (FLD), Sealed Lead-Acid (SLD/AGM), Lithium Iron Phosphate (LI), and a User-defined mode.
**Smart Features:** Includes alternator running detection to prevent starter battery over-discharge and supports remote monitoring via the DC Home app (requires BT-2 module).



---

## 2. Preparation and Wiring

Proper wire sizing is essential to maintain a voltage drop of less than 3%.

### Recommended Cable Gauges (20A Model)

| Cable Path | Gauge Size |
| --- | --- |
| **Output** (to Auxiliary Battery) | 10 AWG () |
| **Input** (from Starter Battery) | 8 AWG () |

### Mounting Site Requirements

**Clearance:** Maintain at least **5.91 inches (150 mm)** of clearance on all sides for proper ventilation .
**Environment:** Install in a clean, dry area with ambient temperatures between ** and  ( to )**.
**Proximity:** Keep the charger as close to the battery as possible; cables should ideally not exceed 10 meters (32.8 feet).

---

## 3. Installation Overview

### Wiring Sequence

1. **Auxiliary Battery:** Connect the Negative Output Terminal to the auxiliary battery negative, and the Positive Output Terminal (via an ANL fuse) to the auxiliary battery positive.
2. **Starter Battery:** Connect the Negative Input Terminal to the starter battery negative, and the Positive Input Terminal (via an ANL fuse) to the starter battery positive.
3. **IGN Signal Wire:** This wire is **only required for smart alternators**. Connect it from the charger's IGN port to the vehicle's ignition signal.
4. **Temperature Sensor:** For lead-acid batteries, mount the sensor near the battery and plug it into the BTS port to enable temperature compensation. **Do not use this for Lithium batteries**.



---

## 4. Charging Logic & Parameters

The charger uses a four-stage algorithm: **Bulk**, **Boost**, **Float**, and **Equalization**.

### Default 12V Battery Parameters

| Parameter | SLD/AGM | FLD | GEL | LI (LFP) |
| --- | --- | --- | --- | --- |
| **Overvoltage Shutdown** | 16.0V | 16.0V | 16.0V | 16.0V |
| **Boost Voltage** | 14.6V | 14.6V | 14.2V | 14.4V |
| **Float Voltage** | 13.8V | 13.8V | 13.8V | N/A  |
| **Equalization Voltage** | N/A | 14.8V | N/A | N/A  |

---

## 5. Troubleshooting

Check the **Fault Status Indicator** (LED) for error codes:

| LED Pattern | Fault Description | Action |
| --- | --- | --- |
| **Fast Flash Red** | Aux Battery Overvoltage | Check if voltage is within range (max 17V).|
| **Jumping Flash Red** | Aux Battery Overdischarge | Recharge the auxiliary battery.|
| **Solid Red** | Aux Battery Overtemperature | Let the battery cool down.|
| **Slow Flash Red** | Charger Overtemperature | Improve ventilation and let the unit cool.|
| **Slow Flash Red** | Starter Reverse Polarity | Correct the polarity of the input connections.|

---

## 6. Technical Specifications (20A Model)

**Max Rated Charge Current:** 20A.
**Max Input Power:** 300W.
**Dimensions:**  ().
**Weight:**  (1.5 kg).
**Protection:** Includes short-circuit, overvoltage, overtemperature, and reverse polarity protection.

