# CIF Compiler Specification v0.1

> A reference implementation for translating Creative Intent Format (CIF) into model-specific prompts, with adaptive weighting and ritualized correction.

## 🎯 Purpose

To compile CIF trait objects into weighted, enforceable prompt strings that preserve character identity across generations — even when using different generative models.

## 🧱 Architecture

The compiler operates in three phases:

### Phase 1: Initialize Master Trait Codex
- On first use, create a persistent JSON structure for the character.
- Structure:
  ```json
  {
    "p_level": 1,
    "trait_type": "Color",
    "description": "Left inner ear YELLOW (#FFD966)",
    "weight_mod": 2.0,
    "locked_rule": true,
    "enforcement_language": "LEFT INNER EAR MUST BE YELLOW."
  }