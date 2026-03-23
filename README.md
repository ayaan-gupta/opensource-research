# FTC DECODE Season — Open-Source Research

This repository contains original technical research produced during the **2025–2026 FIRST Tech Challenge (FTC) DECODE season**. We are open-sourcing these papers to share novel engineering work with the broader FTC and robotics community.

**Author:** William Wang

---

## 📄 Papers

### 1. [6 Wheeled Mecanum Drive for FTC](./6_Wheel_Mecanum_Kinematics_for_FTC.pdf)

A rigorous kinematic analysis of a novel **6-wheeled Mecanum drivetrain** configuration for FTC robots.

**Key Contributions:**
- Full derivation of **inverse kinematics** — mapping desired robot motion (translation + rotation) to individual wheel velocities for all 6 wheels
- **Forward kinematics** using the Moore-Penrose pseudo-inverse to recover robot velocity from wheel encoder readings
- Systematic treatment of all six wheel positions (front-left/right, middle-left/right, back-left/right)
- Coordinate system conventions aligned with the 2025–2026 FTC DECODE field (NWU — North-West-Up)

**Why it matters:**  
Most FTC teams use the standard 4-wheel Mecanum configuration. A 6-wheel layout can offer improved load distribution and additional traction, but requires custom kinematic math. This paper provides the complete mathematical foundation to implement it in code.

---

### 2. [Camera Field of View & Motion Blur Analysis (DECODE_Fov)](./DECODE_Fov.pdf)

A practical vision-system analysis targeting **fiducial marker detection** with UVC-class cameras under robot motion, developed for the FTC DECODE autonomous period.

**Key Contributions:**
- Camera selection rationale: **global shutter vs. rolling shutter** for robotics vision
- Full **field-of-view (FOV) calculation** for the AR0234CS sensor (2.0 MP, 120° diagonal) at a 3.5 m field distance:
  - Horizontal: ~9.3 m wide
  - Vertical: ~7.0 m tall
  - Ground resolution: **9.68 mm/pixel** at 960 × 720
- Derivation of the **maximum safe exposure time** (~4.8 ms) to limit fiducial marker motion blur to under 1 pixel at 2 m/s robot speed
- Discussion of brightness trade-offs and pixel binning as a mitigation strategy

**Why it matters:**  
Vision-based autonomy in FTC is highly sensitive to motion blur. This paper provides a principled, quantitative framework any team can adapt to their own camera hardware to tune exposure settings for reliable marker detection at speed.

---

## 🤖 Context

**FIRST Tech Challenge (FTC)** is a high school robotics competition in which teams design, build, and program a robot to compete on a 12 × 12 ft field. The **DECODE** season (2025–2026) features challenges that reward precise autonomous navigation and vision-based game-piece detection.

Both papers were developed to push the performance ceiling of our robot's drivetrain control and vision pipeline beyond what existing publicly available resources covered.

---

## 📬 Contributing & Use

These papers are released openly for the FTC community and any robotics enthusiast. You are welcome to:
- Reference or build upon the kinematic derivations in your own drivetrain code
- Adapt the FOV/exposure analysis to your camera hardware
- Open an issue or discussion if you spot an error or want to extend the work

If you use this research, a citation or shout-out to the team is always appreciated!

---

## 📖 Citation

```
Wang, W. (2025). 6 Wheeled Mecanum Drive for FTC.
Wang, W. (2026). Motion Blur in Cameras: Field of View Analysis for Fiducial Marker Detection (DECODE_Fov).
```
