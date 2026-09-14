# Stability Metrics

## Purpose

The following metrics will be tracked throughout the project to compare the original Kundur two-area system with the renewable-rich system in which Generator G4 is replaced by a solar-plus-battery energy storage system.

The table establishes a consistent set of measurements that can be used as the project progresses.

---

# Stability Metrics Table

| Category | Metric | Units | What It Measures | Why It Matters |
|---|---|---:|---|---|
| Frequency | Frequency Nadir | Hz | Lowest system frequency following a disturbance | Indicates how severe the frequency drop is after loss of generation or another disturbance |
| Frequency | Maximum Frequency Deviation | Hz or Hz deviation | Largest difference between frequency and nominal frequency | Provides a general measure of frequency disturbance severity |
| Frequency | ROCOF | Hz/s | Rate of Change of Frequency | Indicates how rapidly system frequency is changing and is strongly affected by system inertia |
| Frequency | Settling Time | s | Time required for frequency to return near its steady-state value | Shows how quickly the system recovers following a disturbance |
| Rotor Angle | Maximum Rotor-Angle Separation | degrees | Maximum angular difference between generators | Helps determine whether synchronous generators remain in synchronism |
| Rotor Angle | Relative Rotor Angle | degrees | Rotor-angle movement of one generator or area relative to another | Allows inter-area generator motion to be observed |
| Oscillation | Inter-Area Oscillation Frequency | Hz | Frequency of oscillation between Area 1 and Area 2 | Characterizes the dominant inter-area mode |
| Oscillation | Damping Ratio | % | Rate at which an oscillation decreases | Indicates whether oscillations decay, persist, or grow |
| Oscillation | Oscillation Settling Time | s | Time required for inter-area oscillations to decay | Provides an intuitive measurement of damping performance |
| Voltage | Minimum Bus Voltage | pu | Lowest voltage reached during or following a disturbance | Indicates the severity of voltage depression |
| Voltage | Maximum Bus Voltage | pu | Highest voltage reached during or following a disturbance | Identifies possible overvoltage conditions |
| Voltage | Voltage Deviation | pu or % | Difference from nominal bus voltage | Measures voltage regulation performance |
| Voltage | Voltage Recovery Time | s | Time required for voltage to recover following a disturbance | Shows how quickly voltage control restores acceptable operation |
| Voltage Stability | PV Margin | MW | Additional real-power transfer possible before reaching the voltage-stability limit | Indicates how close the system is to voltage collapse |
| Voltage Stability | QV Margin | Mvar | Reactive-power margin available at a bus | Indicates the amount of reactive-power support available before voltage instability |
| Power Flow | Inter-Area Tie-Line Active Power | MW | Active-power transfer between Area 1 and Area 2 | Shows how power flows and oscillates between the two areas |
| Power Flow | Tie-Line Power Oscillation | MW | Variation in power transfer following a disturbance | Provides a clear measurement of inter-area oscillation behavior |
| Power Flow | Maximum Transmission-Line Loading | % | Highest loading of monitored transmission lines | Helps identify transmission stress or overload conditions |
| Reactive Power | Generator Reactive Power | Mvar | Reactive-power output from synchronous generators | Indicates generator contribution to voltage support |
| Reactive Power | Inverter Reactive Power | Mvar | Reactive-power output or absorption from the solar/BESS inverter | Shows how the inverter supports system voltage |
| Generator | Generator Active Power | MW | Real-power output of each synchronous generator | Shows how generators respond and redistribute power following disturbances |
| Renewable Plant | Solar Active Power | MW | Real-power output from the solar plant | Tracks renewable generation contribution |
| BESS | Battery Active Power | MW | Real power injected or absorbed by the battery | Shows battery contribution to frequency and oscillation control |
| BESS | Battery Reactive Power | Mvar | Reactive power injected or absorbed by the BESS inverter | Shows battery/inverter contribution to voltage support |
| BESS | Battery State of Charge | % | Remaining stored battery energy | Determines whether the battery can continue providing support |
| Stability | Critical Clearing Time | s or cycles | Maximum fault duration before the system becomes unstable | Provides a direct measure of transient-stability margin |
| Stability | Post-Fault Stability | Stable / Unstable | Whether the system returns to acceptable operation following a disturbance | Provides a basic classification of disturbance performance |

---

# Most Important Metrics for This Project


## 1. Inter-Area Oscillation Frequency

The Kundur system is designed to exhibit a low-frequency oscillation where generators in one area move against generators in the other area.

Conceptually:

```text
Area 1                       Area 2

G1 + G2        <---->       G3 + G4
```

The oscillation frequency tells us how quickly this swinging motion occurs.

---

## 2. Damping Ratio

Damping ratio indicates how quickly an oscillation disappears.

### Well-Damped

```text
Amplitude
   |
   | \    /\
   |  \  /  \_
   |   \/     \___
   |              \____
   +----------------------> Time
```

Oscillations decrease quickly.

### Poorly Damped

```text
Amplitude
   |
   |   /\    /\    /\
   |  /  \  /  \  /  \
   |_/    \/    \/    \_
   +----------------------> Time
```

Oscillations continue for a long time.

### Unstable

```text
Amplitude
   |
   |                 /\
   |          /\    /  \
   |    /\   /  \__/    \
   |___/  \_/
   +----------------------> Time
```

Oscillations grow with time.

---

## 3. Maximum Rotor-Angle Separation

Synchronous generators must remain synchronized with each other.

Tracking generator rotor angles helps determine whether the machines continue operating together following a disturbance.

A rapidly increasing separation between generator rotor angles can indicate loss of synchronism.

---

## 4. Frequency Nadir

Frequency nadir is the lowest frequency reached following a disturbance.

Example:

```text
60.0 Hz
   |
   |\
   | \
   |  \____ 59.55 Hz
   |       \____
   |            \____ 60 Hz
   +----------------------> Time
```

In this example:

```text
Frequency Nadir = 59.55 Hz
```

Replacing a synchronous generator with inverter-based solar generation may change frequency response because the system has different physical and control characteristics.

---

## 5. ROCOF

ROCOF means:

**Rate of Change of Frequency**

Units:

```text
Hz/s
```

It measures how rapidly frequency changes immediately after a disturbance.

For example:

```text
60.0 Hz → 59.8 Hz
```

occurring very quickly results in a larger ROCOF than the same change occurring slowly.

ROCOF will be particularly useful when comparing the original G4 synchronous generator with the solar/BESS replacement.

---

## 6. Minimum Bus Voltage

After a fault or major disturbance, bus voltage may temporarily decrease.

Example:

```text
1.00 pu
   |
   |\
   | \
   |  \____ 0.72 pu
   |       \
   |        \______ 0.99 pu
   +----------------------> Time
```

The minimum value in this example is:

```text
Vmin = 0.72 pu
```

This metric helps evaluate whether sufficient voltage and reactive-power support exists.

---

## 7. Tie-Line Active Power

The active power flowing between Area 1 and Area 2 is one of the most useful measurements for observing inter-area behavior.

```text
Area 1                       Area 2

G1 + G2  ---- Ptie ---->   G3 + G4
```

Following a disturbance, this power may oscillate:

```text
Tie-Line Power
     |
     |     /\      /\
     |____/  \____/  \____
     |
     +----------------------> Time
```

The rate at which these oscillations decay provides information about inter-area damping.

---

# Baseline vs Renewable Case Comparison

Eventually, these metrics can be placed into a comparison table.

| Metric | Original G4 Case | Solar/BESS Case | Solar/BESS + Improved Controls |
|---|---:|---:|---:|
| Frequency Nadir | TBD | TBD | TBD |
| Maximum ROCOF | TBD | TBD | TBD |
| Maximum Rotor-Angle Separation | TBD | TBD | TBD |
| Inter-Area Oscillation Frequency | TBD | TBD | TBD |
| Damping Ratio | TBD | TBD | TBD |
| Minimum Bus Voltage | TBD | TBD | TBD |
| Voltage Recovery Time | TBD | TBD | TBD |
| Maximum Tie-Line Oscillation | TBD | TBD | TBD |
| Critical Clearing Time | TBD | TBD | TBD |

This table can be updated throughout the semester as simulations are completed.

---

# Plot Requirements

For every plotted metric, include:

- Descriptive title
- Time axis labeled in seconds
- Correct engineering units
- Clearly identified signals
- Readable legend
- Figure number
- Caption explaining the engineering significance

---

# Data Documentation

For every recorded result, document whether the value is:

- Supplied system data
- Calculated result
- Simulation result
- Engineering assumption
- Selected controller setting

Controller parameters should not be presented as though they were supplied system data.

---

# Primary Project Comparison

The central comparison throughout the project is:

```text
BASELINE SYSTEM

Area 1                       Area 2

G1 + G2  <-------------->   G3 + G4
```

versus:

```text
RENEWABLE-RICH SYSTEM

Area 1                       Area 2

G1 + G2  <-------------->   G3 + Solar/BESS
```

and eventually:

```text
CONTROLLED RENEWABLE SYSTEM

Area 1                       Area 2

G1 + G2  <-------------->   G3 + Solar/BESS
                                      |
                                      |
                              Improved Controls
```

The stability metrics provide an objective way to determine whether replacing G4 makes system performance better, worse, or approximately equivalent to the original system.