# Creative Intent Format (CIF)

> **A lightweight, user-owned standard for preserving creative identity in generative AI**

**Status**: Draft — Seeking community feedback  
**Author**: [Your Name], independent digital creator  
**License**: [CC0 1.0 Universal](LICENSE)

---

## 🎯 The Problem

Generative AI tools (text-to-image, text-to-3D, etc.) treat every prompt as **stateless**. This forces creators to manually re-specify core traits like *"jade goggles"* or *"twin braids"* with every new image—leading to:

- **Visual drift**: Characters lose their identity  
- **High cognitive load**: Repetitive prompting  
- **Fragmented workflows**: No continuity across sessions or tools  

While models support weighting (e.g., `(trait:1.3)`), there’s **no open, web-native way** to capture and persist *what matters most to the creator*.

---

## 💡 The Solution: CIF

**Creative Intent Format (CIF)** is a simple, JSON-based format that lets web apps:

1. **Declare** sacred, flexible, and forbidden traits  
2. **Persist** creative identity across sessions  
3. **Compile** into model-specific prompts (SDXL, DALL·E, Midjourney, etc.)  
4. **Respect user control** — all data stays client-side unless explicitly shared

CIF is **not a model**—it’s a **contract between creator and tool**.

---

## 📦 Example

```json
{
  "cif_version": "0.1",
  "subject": "Kaela",
  "sacred": [
    { "trait": "jade goggles", "weight": 1.4, "locked": true },
    { "trait": "twin braids", "weight": 1.3 }
  ],
  "contextual": [
    { "trait": "desert temple", "weight": 1.0 }
  ],
  "negative": [
    { "trait": "hat", "weight": 0.2 }
  ],
  "user_consent": "explicit"
}
