# Week 1: Project Launch, Software Verification, and Study Plan

## Semester Project

**Stability and Control of a Renewable Two-Area Power System**

## Week 1 Objective

The goal of Week 1 is to establish the engineering problem, organize the project team, verify that all required software is available, understand the baseline Kundur two-area system, and create a reproducible file-management system for the rest of the semester.


---

# Required Work

## 1. Verify PowerWorld Simulator

Install PowerWorld Simulator or verify access to the CSUS academic version.

Confirm that the following opens successfully:

- 13-bus educational/evaluation edition

Record:

- PowerWorld version
- License/edition being used
- Any available add-ons

### Required Screenshot

Take a screenshot showing:

- PowerWorld open
- PowerWorld version
- **Add Ons** ribbon

---

## 2. Verify Required PowerWorld Add-Ons

Open the **Add Ons** ribbon and verify that the following tools are available:

- Transient Stability
- PV Curve
- QV Curve

These tools will be used later in the project for dynamic and voltage-stability studies.

Record which tools are available.

---

## 3. Form the Project Team

Create a three-person team.

Assign the following initial roles:

### Network / Modeling Lead

Responsible for:

- PowerWorld network model
- Bus and transmission data
- Generator locations
- Loads
- Power-flow setup
- Maintaining the baseline network model

### Dynamics / Control Lead

Responsible for:

- Generator dynamic models
- Excitation systems
- Governors
- Power System Stabilizers
- Solar/BESS models
- Controller development
- MATLAB/Simulink work

### Verification / Reporting Lead

Responsible for:

- Checking calculations and simulations
- Comparing results
- Maintaining figures and data
- Documenting assumptions
- Preparing reports and presentations

## Role Rotation

Roles must rotate throughout the semester so that every team member gains experience with modeling, controls, and verification/reporting.

---

# 4. Review the Kundur Two-Area System

Become familiar with the classic Kundur two-area, four-machine, 11-bus system.

Identify:

- Area 1
- Area 2
- Generator G1
- Generator G2
- Generator G3
- Generator G4
- Major load buses
- Transmission corridor connecting the two areas

## Basic System Concept

```text
        AREA 1                           AREA 2

     G1       G2                      G3       G4
      \       /                        \       /
       \     /                          \     /
      Local Grid ===== Tie Lines ===== Local Grid
           |                              |
         Loads                          Loads
```

The transmission connection between the two areas allows power to be transferred between them.

One of the important dynamic behaviors of this system is an **inter-area oscillation**, where the generators in Area 1 tend to swing against the generators in Area 2.

Later in the project, **Generator G4 will be replaced by a solar-plus-battery plant**.

---

# 5. Create an Annotated One-Line Diagram

Create or obtain a one-line diagram of the Kundur system.

Clearly label:

- G1
- G2
- G3
- G4
- Area 1
- Area 2
- Loads
- Major buses
- Tie-line / inter-area transmission corridor

The diagram should make it easy for someone unfamiliar with the project to understand the general system structure.

---

# 6. Establish File-Naming Rules

Use descriptive and consistent filenames.

Example:

```text
Team03_W01_Kundur_Base_v01.pwb
Team03_W01_Kundur_Base_v02.pwb
```

Once a file has been checked and accepted:

```text
Team03_W01_Kundur_Base_VALIDATED.pwb
```

Do not overwrite validated baseline models.

Instead, copy the validated file into the next week's folder before making new changes.

---

# 7. Establish Version-Control Rules


1. Never directly modify the validated base-case file.
2. Increment the version number whenever a significant modification is made.
3. Keep notes describing major changes between versions.
4. Clearly identify validated models.
5. Store raw simulation data separately from processed results.
6. Keep final figures separate from temporary figures.
7. Record assumptions and controller settings.
8. Carry validated files forward each week rather than rebuilding the model.

---

# 8. State the Main Project Question

The semester project is centered on the following question:

> **Can the power system remain stable after replacing Generator G4 with a solar-plus-battery plant, and what controls are required?**

The project will eventually compare the original system:

```text
Area 1                     Area 2

G1 + G2  <-------------->  G3 + G4
```

with the renewable-rich system:

```text
Area 1                     Area 2

G1 + G2  <-------------->  G3 + Solar/BESS
```

The goal will be to determine how replacing G4 affects system stability and whether inverter and battery controls can maintain acceptable performance.

---

# Required Week 1 Evidence

The Week 1 submission should include:

- [X] Screenshot showing PowerWorld version
- [X] Screenshot showing the Add Ons ribbon
- [X] Confirmation that Transient Stability is available
- [X] Confirmation that PV/QV tools are available
- [ ] Annotated Kundur one-line diagram
- [ ] Area 1 and Area 2 identified
- [ ] G1–G4 identified
- [ ] Major loads identified
- [ ] Inter-area transmission corridor identified
- [ ] Team-member roles listed
- [ ] Role-rotation plan
- [X] Folder structure
- [X] File-naming rules
- [X] Version-control/reproducibility rules
- [X] Main project question
- [ ] One-page stability metrics table

---

# Week 1 Submission

Submit:

1. **One PDF project-launch memo**
2. **One ZIP file containing the project folder structure and initial project files**


---

#  Memo Organization

## 1. Project Objective

- Brief project description
- Main research question

## 2. Software Verification

- PowerWorld version
- PowerWorld edition
- Available add-ons
- Screenshot

## 3. Kundur System Overview

- Annotated one-line diagram
- Area 1
- Area 2
- G1–G4
- Loads
- Tie-line corridor

## 4. Team Organization

- Team members
- Initial roles
- Role-rotation plan

## 5. Reproducibility Plan

- Folder structure
- File-naming convention
- Version-control rules
- Validated-file procedure

## 6. Stability Metrics

Include the Week 1 stability-metrics table.

---

# Quality Requirements

All project work should follow these requirements throughout the semester.

## Plots

Every plot should include:

- Descriptive title
- Labeled x-axis
- Labeled y-axis
- Units
- Readable legend when appropriate
- Caption explaining the engineering meaning

## Documentation

Clearly distinguish between:

- Supplied data
- Calculated values
- Selected controller settings
- Engineering assumptions

## Reproducibility

Another engineering team should be able to reproduce the results using the information contained in the project files and report.

## Baseline Preservation

Validated files should be carried forward throughout the semester.

Do not rebuild an unrelated model each week.