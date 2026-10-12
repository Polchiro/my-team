# Task Note · BMI Calculator

- Date: 2026-10-12
- From: Leader (Wailan)
- To: Member (Taroko)
- Status: To do

## What to do

Build a **BMI calculator web app**. The interface text must be in **English**.

## Format

- **Single HTML file** (HTML + CSS + JavaScript all inline). Do not split into multiple files, do not use external CDNs or network resources.
- Filename: `bmi-calculator.html`
- Save to: `workspace/outbox/` (save as a new file, do not overwrite anything that is already there)
- Input fields:
  - Height (cm)
  - Weight (kg)
- Calculation: `BMI = weight(kg) / height(m)²`
- Buttons: **Calculate** and **Clear**
- Result display:
  - BMI value, **rounded to one decimal place**
  - Category (standard adult ranges):
    - Underweight: BMI < 18.5
    - Normal: 18.5 ≤ BMI < 24
    - Overweight: 24 ≤ BMI < 27
    - Obese: BMI ≥ 27
  - Categories must be visually distinct (color or label)
- Input validation: for non-numbers, empty values, or height/weight ≤ 0, show an error message instead of a result.
- Layout: usable on both phone and desktop (basic responsive design is enough).

## What "done" looks like

1. `workspace/outbox/bmi-calculator.html` exists.
2. Opens in a browser and works with no errors and no external dependencies.
3. Height 170, weight 65 → shows BMI 22.5, category "Normal".
4. Invalid input (e.g. height -1) → shows an error message, not a result.
5. All interface text is in English.

## When finished

Leave a one-handoff line in `workspace/outbox/` (what you did, what to watch out for, ready to use or not), then **STOP** and ask the captain to go back to the leader for a check.
