---
name: chef
description: "Generates family meal plans (ideally for a 2-week rolling period) using the FOOD_LIST.md in the workspace. Prioritizes freezer surplus, manages prep times (weekdays vs. weekends), and creates categorized, two-phase shopping lists."
---

# 👨‍🍳 Chef Skill

This skill automates family meal planning and shopping list generation based on the `FOOD_LIST.md` file in the current repository.

## 📋 Core Workflow

This is a **two-phase process**. Always start with Phase 1.

### Phase 1: Menu Proposal (Initial Request)
When asked to generate a menu, provide ONLY the 2-week plan. Follow these rules:

**1. Standalone Meals & Sides**
- Every soup or main dish is a standalone meal for the day. Do not pair 1st and 2nd courses.
- If a dish doesn't explicitly include a side (e.g., Pörkölt, Rántotthús, Fasírt), pick one appropriate side from the **Koretek (Sides)** section of `FOOD_LIST.md`.

**2. Strategy & Safety**
- **Generate a menu for a Rolling 2-Week Period.**
- **Leftover Optimization:** Respect `2+ days` tags.
- **STRICT NO-FREEZE POLICY:** Never suggest freezing cooked meals. All leftovers must be fridge-stored and consumed within 3 days of cooking.
- **Surplus:** Prioritize RAW items from the **❄️ Current Freezer / Pantry Surplus**.
- **Time:** Weekdays < 60 min prep. Weekends can be intensive.

**3. Interaction Style**
- Present the 2-week menu clearly.
- **At the end of the proposal, ask for the user's approval.** Do not generate shopping lists yet.

---

### Phase 2: Shopping List Generation (After Approval)
ONLY once the user has approved the menu or explicitly requested the shopping lists:

**1. Two-Phase Shopping Lists**
Generate **two separate shopping lists** (Week 1 and Week 2):
- **Week 1:** Include bulk/pantry items needed for the whole period + fresh items for Week 1.
- **Week 2:** Focus on fresh replenishment and ingredients needed for Week 2 dishes.
- Group all ingredients by category (Produce, Meat, Dairy, Pantry).

## 🗂️ Resources
- **FOOD_LIST.md**: The source of truth for recipes, surplus, and prep times. Must be present in the workspace.
