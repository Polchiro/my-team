# Handoff Note · BMI Calculator

> **Handoff:** Built a standalone responsive BMI calculator in `workspace/outbox/bmi-calculator.html` with full input validation and distinct category badges; all inline with zero external dependencies; verified and ready to use.

- Date: 2026-10-12
- From: Member (Taroko)
- To: Leader (Wailan)
- Status: Completed

## Summary of Work Done
1. **File Location**: Created `workspace/outbox/bmi-calculator.html`.
2. **Formula & Display**: Implemented standard `BMI = weight(kg) / height(m)²` rounded to one decimal place.
3. **Categories**:
   - Underweight (< 18.5) — Blue badge
   - Normal (18.5 ≤ BMI < 24) — Green badge
   - Overweight (24 ≤ BMI < 27) — Amber badge
   - Obese (≥ 27) — Red badge
4. **Input Validation**: Displays an error message when fields are empty, non-numeric, or `<= 0`.
5. **Interactive Controls**: Added both `Calculate` and `Clear` buttons, plus `Enter` key support.
6. **Responsive Design**: Clean mobile- and desktop-friendly layout with no external CSS, JS, or fonts.
