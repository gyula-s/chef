---
name: chef
description: "Generates family meal plans (ideally for a 2-week rolling period) using the FOOD_LIST.md in the workspace. Prioritizes freezer surplus, manages prep times (weekdays vs. weekends), and creates categorized, two-phase shopping lists."
---

# 👨‍🍳 Chef Skill

This skill automates family meal planning and shopping list generation based on the `FOOD_LIST.md` file in the current repository.

## 📋 Core Workflow

When asked to generate a menu, follow these rules:

### 1. Standalone Meals & Sides
- Every soup or main dish is a standalone meal for the day. Do not pair 1st and 2nd courses.
- If a dish doesn't explicitly include a side (e.g., Pörkölt, Rántotthús, Fasírt), pick one appropriate side from the **Koretek (Sides)** section of `FOOD_LIST.md`.

### 2. Rolling 2-Week Strategy & Food Safety
- **Generate a menu for a Rolling 2-Week Period.**
- **Leftover Optimization:** Respect `2+ days` tags.
- **Leftover Safety Rule:** Never schedule a leftover more than 3 days after it was cooked (e.g., a Monday meal can be eaten on Tuesday or Wednesday, but not after). 
- **Freezing for Week 2:** If you want to use a Week 1 batch in Week 2, you **must** explicitly instruct to "Freeze half for Week 2" in the Week 1 plan.
- **Continuity:** Week 2 **must** explicitly list any meals saved or frozen from Week 1 (e.g., *"Tuesday: [Frozen from Week 1] Lasagna"*).
- **Ingredient Cascading:** Look for synergies. If Week 1 uses half a cabbage or a large bag of potatoes, ensure Week 2 has a dish that uses the rest.

### 3. Surplus & Prioritization
- Always prioritize items listed in the **❄️ Current Freezer / Pantry Surplus** section of `FOOD_LIST.md` (e.g., Bacon, Sausages).

### 4. Time Management
- **Weekdays:** Prioritize meals with `Prep: < 60 min`.
- **Weekends:** Include more time-intensive meals.
- **Thinking Ahead:** Identify `[Make Ahead]` items. On weekends, suggest a prep session to prepare a meal for a busy weekday.

### 5. Two-Phase Shopping Lists
Generate **two separate shopping lists** (Week 1 and Week 2):
- **Week 1:** Include bulk/pantry items needed for the whole period + fresh items for Week 1.
- **Week 2:** Focus on fresh replenishment and ingredients needed for Week 2 dishes.
- Group all ingredients by category (Produce, Meat, Dairy, Pantry).

## 🗂️ Resources
- **FOOD_LIST.md**: The source of truth for recipes, surplus, and prep times. Must be present in the workspace.
