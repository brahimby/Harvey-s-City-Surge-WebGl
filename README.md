# 🥊 Beat 'Em Up WebGL Game

A responsive 2D Beat ’Em Up built with **Unity**, featuring fluid combat, AI-driven enemies, and adaptive controls for both **PC** and **mobile browsers**.

---

## 🎮 Overview

This project is a modern take on the classic **side-scrolling beat ’em up** genre — inspired by games like *Streets of Rage* and *Final Fight* — built entirely in Unity using C# and DOTween for polished animation flow.  
It’s designed to run seamlessly on **WebGL**, automatically adapting input methods depending on whether the player is using a keyboard or touchscreen.

---

## 🧠 Core Systems

### **Player Controller**
- Transform-based top-down movement (non-physics).
- Smooth walking, jumping, and multi-hit combo system.
- Horizontal and vertical clamping within camera bounds.
- Automatic combo reset and direction flipping.
- Dynamic input: supports both PC (keyboard) and mobile (elastic joystick UI).

### **Enemy AI System**
- Modular and scalable behaviour using state logic.
- Handles idle, chase, attack, and smart positioning.
- Aligns vertically before attacking for clean hit zones.
- Includes hurt reactions, death animation, and blinking fade-out.

### **Boss Controller**
- Independent boss logic built for large-scale encounters.
- Custom health pool, unique attack patterns, and phase transitions.

### **Input Handling**
- Auto-detects device type (PC vs Mobile) at runtime.
- Switches between keyboard input and mobile joystick UI automatically.
- WebGL-compatible JavaScript bridge for user-agent detection.

### **Camera System**
- Follows player with smooth tween transitions.
- Optional Post-Processing toggle (blur, vignette, etc.).
- Supports dynamic phase switching between level segments.

---

## ⚙️ Technologies & Packages

| Tool / Package | Purpose |
|----------------|----------|
| **Unity 6+** | Game engine |
| **C# (.NET)** | Core gameplay scripting |
| **DOTween** | Animation, tweens, transitions |
| **Input System / Custom InputReader** | Modular input handling |
| **Post Processing Stack v3** | Visual enhancements (optional) |
| **WebGL Build** | Browser-compatible deployment |

---

## 📱 Device Adaptive Input

| Platform | Input Type | UI |
|-----------|-------------|----|
| **PC (WebGL/Desktop)** | Keyboard + InputReader | Hidden |
| **Mobile (WebGL)** | Elastic Joystick | Visible |

Automatic detection is done at runtime via:
```csharp
SystemInfo.deviceType == DeviceType.Handheld
