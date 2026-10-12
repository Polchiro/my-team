# Task Note · BMI Calculator v3 — bilingual (EN / 繁中)

- Date: 2026-10-12
- From: Leader (Wailan)
- To: Member (Taroko)
- Status: To do

## What to do

Make a **bilingual version** of the BMI calculator: **English + Traditional Chinese (Taiwan usage)**, switchable at runtime.

## Format

- **New file, do not modify the original**: save as `workspace/outbox/bmi-calculator-v3.html`
  - 🚫 Do NOT touch `workspace/outbox/bmi-calculator.html` — v1 stays exactly as it is.
  - Single file, HTML + CSS + JS all inline, no external CDN/network resources.
- Same features as v1: height (cm) + weight (kg) → BMI to one decimal → colour category badge, Calculate + Clear buttons, input validation, responsive layout, `Enter` key support.
- **Add a language switcher** (a toggle button showing the *other* language, e.g. `繁體中文` / `English`):
  - Every visible string switches: title, subtitle, field labels, placeholders, both buttons, error messages, "Your BMI", the four category names, and the ranges legend.
  - Default language: follow the browser — if `navigator.language` starts with `zh`, open in Chinese, otherwise English. Remember the user's choice in `localStorage`.
  - Set `document.documentElement.lang` correctly on every switch (`en` / `zh-Hant-TW`).

### Required wording (Traditional Chinese, Taiwan usage)

| English | 繁體中文（台灣用語） |
|---|---|
| BMI Calculator | BMI 計算器 |
| Calculate Body Mass Index based on height and weight | 依身高與體重計算身體質量指數 |
| Height (cm) | 身高（公分） |
| Weight (kg) | 體重（公斤） |
| Calculate | 計算 |
| Clear | 清除 |
| Your BMI | 你的 BMI |
| Underweight | 過輕 |
| Normal | 正常 |
| Overweight | 過重 |
| Obese | 肥胖 |
| Standard Adult Ranges | 成人標準區間 |
| Please enter both height and weight. | 請同時輸入身高與體重。 |
| Height and weight must be greater than zero. | 身高與體重必須大於 0。 |
| Please enter valid numeric values. | 請輸入有效的數字。 |

Use Taiwan conventions throughout: 軟體 not 軟件, 資訊 not 信息, 影片 not 視頻.

## What "done" looks like

1. `workspace/outbox/bmi-calculator-v3.html` exists; `workspace/outbox/bmi-calculator.html` is **byte-for-byte unchanged**.
2. Opens in a browser, no console errors, no external resources.
3. **English test:** 170 / 65 → `22.5` with badge `Normal`.
4. **Chinese test:** switch to 繁體中文 → same input → `22.5` with badge `正常`, labels show 身高（公分）/ 體重（公斤）, buttons 計算 / 清除.
5. Validation messages appear in the **currently selected** language (e.g. height `-1` → `身高與體重必須大於 0。`).
6. Refreshing the page keeps the language the user chose; a fresh browser with `zh-TW` locale opens in Chinese.
7. No English text left on screen while in Chinese mode (and vice versa), including the legend and placeholders.

## When finished

Leave a one-handoff line in `workspace/outbox/` (what you did, what to watch out for, ready to use or not), then **STOP** and ask the captain to go back to the leader for a check.
