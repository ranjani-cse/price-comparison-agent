# 🛍️ Session 9: Automated Price Comparison Agent

An AI-powered browser automation agent that compares mobile phone prices on Flipkart (Indian e-commerce) and identifies the best value.

---

## 1. Original User Goal

**Query:** "Compare prices of iPhone 15, Samsung Galaxy S24, and Google Pixel 8 on Flipkart"

**Goal:** Extract real-time prices in ₹, compare, identify best value.

---

## 2. Planner DAG

START → Browser → Search iPhone 15 → ₹56,900
→ Search Samsung S24 → ₹55,999
→ Search Pixel 8 → ₹52,999
→ Compare → Output → END

text

---

## 3. Browser Path Chosen

| Layer | Used | Reason |
|-------|------|--------|
| Extract | ✅ Yes | Direct HTML extraction |
| Deterministic | ✅ Yes | CSS selectors work |
| A11y | ❌ No | Not needed |
| Vision | ❌ No | Not required |
| Blocked | ❌ No | Flipkart accessible |

**Selected Path:** Extract → Deterministic

---

## 4. Browser Actions Taken (11 actions)

| # | Action | Result |
|---|--------|--------|
| 1 | Browser Launch | ✅ |
| 2 | Search iPhone 15 | ✅ |
| 3 | Extract Price | ₹56,900 |
| 4 | Search Samsung S24 | ✅ |
| 5 | Extract Price | ₹55,999 |
| 6 | Search Pixel 8 | ✅ |
| 7 | Extract Price | ₹52,999 |
| 8 | Compare | ✅ |
| 9 | Generate Output | ✅ |
| 10 | Save Files | ✅ |
| 11 | Close Browser | ✅ |

**Console Output:**
🔍 Searching: iPhone 15 → ✅ ₹56,900
🔍 Searching: Samsung Galaxy S24 → ✅ ₹55,999
🔍 Searching: Google Pixel 8 → ✅ ₹52,999
🏆 BEST VALUE: Google Pixel 8 at ₹52,999

text

---

## 5. Page-State Logs

| Product | URL | Raw Price | Cleaned |
|---------|-----|-----------|---------|
| iPhone 15 | flipkart.com/search?q=iphone+15 | "₹56,900" | 56,900 |
| Samsung S24 | flipkart.com/search?q=samsung+s24 | "₹55,999" | 55,999 |
| Pixel 8 | flipkart.com/search?q=google+pixel+8 | "₹52,999" | 52,999 |

---

## 6. Extracted Data

**JSON Output:**
```json
{
  "products": [
    {"name": "Google Pixel 8", "price": 52999},
    {"name": "Samsung Galaxy S24", "price": 55999},
    {"name": "iPhone 15", "price": 56900}
  ],
  "winner": "Google Pixel 8"
}


** ## 7. Final Comparison Table **

| Rank | Product | Price (₹) | Savings |
|------|---------|-----------|---------|
| 🥇 1st | **Google Pixel 8** | **₹52,999** | - |
| 🥈 2nd | Samsung Galaxy S24 | ₹55,999 | +₹3,000 |
| 🥉 3rd | iPhone 15 | ₹56,900 | +₹3,901 |



**🏆 Winner:** **Google Pixel 8** at **₹52,999**

Metric	Value
Total Turns	3
LLM Calls	0
Browser Actions	11
Total Time	~30s
Success Rate	100%
Total Cost	₹0

┌─────────────────────────────────────────────────────────────────┐
│                    SESSION 9 REPORT                             │
├─────────────────────────────────────────────────────────────────┤
│ Success Rate:      100% (3/3 products)                          │
│ Browser Path:      Extract → Deterministic                      │
│ Total Actions:     11 visible browser actions                   │
│ Total Time:        ~30 seconds                                  │
│ Total Cost:        ₹0                                           │
│ Winner:            Google Pixel 8 at ₹52,999                    │
└─────────────────────────────────────────────────────────────────┘



