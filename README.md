# 🩺 Nursing Note Generator

A single-page React application for quickly creating professional nursing notes from structured form inputs.  
It supports ventilator settings, validates inputs, persists state to `localStorage`, and allows copy/print/export of the generated note.

---

## ✨ Features

- **Structured Inputs**: Age, gender, diagnosis, orientation, breathing, pain, ADLs, meds, devices, precautions.
- **Ventilator Settings**: Mode, RR, VT, PEEP, FiO₂ with numeric sanitization.
- **Live Validation**:
  - Age range 1–129
  - Diagnosis or custom diagnosis required
  - SpO₂ required if not on room air
  - Ventilator requires at least one setting
- **Persistent State**: Form data saved in `localStorage` (`nng_state_v1` key).
- **Output Actions**:
  - Copy to clipboard
  - Export as `.txt`
  - Print
  - Reset all fields
- **Accessible & Mobile-Friendly**:
  - Labels linked to inputs
  - Mobile-friendly numeric inputs
  - Keyboard-accessible form
- **Editable Output**: Generated note appears in a textarea for final edits.

---

## 🗂 Project Structure

This file (`NursingNoteGenerator.jsx` or `.tsx`) contains all app logic.  
UI components (Button, Input, Label, etc.) come from [shadcn/ui](https://ui.shadcn.com/) with Tailwind CSS styling.

Key parts:
- **Static options**: `commonDiagnoses`, `orientationOptions`, etc.
- **Hook**: `useLocalStorage` for persistent state
- **Component**: `<VentilatorSettings />`
- **Validation**: `validate()` checks before generating
- **Note Builder**: `useMemo` assembles the note string
- **Actions**: `copyToClipboard`, `exportTxt`, `printNote`, `resetAll`

---

## 🛠 Installation & Local Development

1. **Clone this repo**:
   ```bash
   git clone https://github.com/<your-username>/nursing-note-generator.git
   cd nursing-note-generator
