# Engineering Spike Plan
## My Dolla $ign - AI Budget Analysis Proof of Concept

**Date:** February 15, 2026  
**Timebox:** 3-5 days (Complete by February 20, 2026)  
**Authors:** Hugo, Rene, Gauge, Allison

---

## 1. Riskiest Assumption

**The AI (OpenAI API) can generate accurate, helpful, and easy-to-understand budget explanations based on user-provided income and expense data.**

We need to prove that:
- The AI can interpret structured budget data correctly
- The AI produces educational content that is understandable to our target users (students, young adults)
- The AI response time is acceptable (< 10 seconds)
- The AI doesn't provide harmful or incorrect financial information
- The AI can explain budgeting concepts like the 50/30/20 rule in simple terms

---

## 2. Spike Goal

**Success means:** We can demonstrate a working prototype where:
1. A user inputs income and expense data (via simple form or hardcoded test data)
2. The data is sent to OpenAI API with a well-crafted prompt
3. The AI returns a budget analysis that is:
   - Accurate (correctly interprets the numbers and calculates percentages)
   - Educational (explains concepts simply)
   - Safe (includes appropriate disclaimers, no harmful advice)
   - Fast (responds within 10 seconds)

---

## 3. Inputs / Outputs

### Input (User Data)
```json
{
  "monthly_income": 3000,
  "expenses": {
    "rent": 1200,
    "food": 400,
    "transportation": 150,
    "utilities": 100,
    "entertainment": 200,
    "savings": 300,
    "other": 150
  }
}
```

### Expected Output (AI Response)
```
Budget Analysis for Your Monthly Finances

Income: $3,000/month
Total Expenses: $2,500
Remaining: $500

Expense Breakdown:
- Housing (Rent): $1,200 (40% of income) 
  This is slightly above the recommended 30% guideline for housing costs.
  
- Food: $400 (13% of income)
  This is reasonable for a monthly food budget.

- Savings: $300 (10% of income)
  You're saving, which is great! Consider increasing to 20% over time.

[... additional categories ...]

Key Insights:
1. Your housing costs are your biggest expense at 40% of income.
2. You're saving 10% - a good start, but aim for 20% if possible.
3. You have $500 unallocated - consider adding this to savings.

What is the 50/30/20 Rule?
This budgeting guideline suggests:
- 50% for NEEDS (rent, utilities, groceries, transportation)
- 30% for WANTS (entertainment, dining out, hobbies)
- 20% for SAVINGS (emergency fund, future goals)

Disclaimer: This analysis is for educational purposes only and does not constitute financial advice.
```

---

## 4. Demo Plan (2-3 minutes)

### Demo Flow:

| Time | Action | Who |
|------|--------|-----|
| 0:00 - 0:30 | Introduce the spike goal and what we're testing | Gauge |
| 0:30 - 1:30 | Live demo: Enter sample budget data, submit, show AI response | Gauge |
| 1:30 - 2:00 | Show the prompt engineering approach and explain why it works | Gauge |
| 2:00 - 2:30 | Discuss edge cases tested (zero income, overspending) | Rene |
| 2:30 - 3:00 | Q&A and next steps | All |

### What We'll Show:
1. Simple web form OR command-line script accepting budget input
2. Real-time API call to OpenAI
3. Formatted response displayed to user
4. At least 2 different test scenarios:
   - Student budget (low income, high rent percentage)
   - Working adult budget (moderate income, balanced expenses)

---

## 5. Owner(s) + Tasks

### Gauge (AI/ML Lead) - PRIMARY OWNER
- [ ] Design and test AI prompt for budget analysis
- [ ] Experiment with different prompt structures for clarity
- [ ] Test edge cases (zero values, extreme values, negative values)
- [ ] Test with expenses exceeding income
- [ ] Document prompt engineering decisions
- [ ] Ensure AI explains the 50/30/20 rule clearly
- [ ] Lead the demo presentation

### Rene (Backend Lead) - SUPPORT
- [ ] Set up OpenAI API integration (Python script)
- [ ] Create simple `/api/analyze` endpoint to receive budget data
- [ ] Handle API errors gracefully (timeouts, rate limits)
- [ ] Measure and log response times
- [ ] Create fallback response if API fails

### Hugo (Frontend Lead) - SUPPORT
- [ ] Create minimal budget input form (functional, not polished)
- [ ] Display AI response in readable format
- [ ] Add loading spinner while waiting for AI
- [ ] Handle and display error messages

### Allison (Documentation Lead) - SUPPORT
- [ ] Document the spike process and findings
- [ ] Record demo video as backup
- [ ] Note any issues or learnings for the PRD
- [ ] Prepare spike results summary

---

## 6. Exit Criteria (Pass/Fail)

### PASS Criteria (All must be met)

| Criteria | Target | How to Verify |
|----------|--------|---------------|
| API Integration | Successfully calls OpenAI API | API returns 200 response |
| Response Time | < 10 seconds | Measured with timestamps |
| Accuracy | Correctly calculates percentages | Manual verification with calculator |
| Readability | Non-technical person understands output | Test with 2 non-CS people |
| Safety | Includes disclaimer, no harmful advice | Manual review of 5+ responses |
| Edge Cases | Handles 0 income, overspending scenarios | Test suite passes |
| 50/30/20 Explanation | AI explains the rule clearly | Manual review |

### FAIL Criteria (Any one = failure)

- API consistently times out or fails (>50% failure rate)
- AI produces incorrect calculations (wrong percentages)
- AI gives specific financial advice beyond budgeting education
- Response takes > 30 seconds consistently
- Cost per request exceeds $0.10
- AI response is confusing or uses too much jargon

---

## 7. If It Fails... (Plan B)

### Fallback Options:

**Option A: Use a different AI model**
- Try Claude API or Gemini as alternatives
- May have different pricing/performance tradeoffs
- Gauge will research alternatives

**Option B: Rule-based analysis with limited AI**
- Use AI only for generating tips/explanations
- Use code to calculate percentages and comparisons
- Reduces AI dependency and cost

**Option C: Template-based responses**
- Pre-write budget analysis templates
- Use AI only to fill in specific numbers
- Most reliable but least personalized

**Option D: Simplified MVP scope**
- Remove AI-generated explanations entirely
- Focus on visual budget breakdown only (charts/graphs)
- Add AI features in post-MVP phase

### Decision Process:
If the spike fails, the team will meet to:
1. Analyze what specifically failed
2. Evaluate each fallback option (pros/cons)
3. Choose the best path forward within 1 day
4. Adjust PRD and timeline accordingly

---

## Spike Timeline

| Day | Tasks | Owner |
|-----|-------|-------|
| Day 1 (Mon) | Set up OpenAI API, initial prompt testing | Rene, Gauge |
| Day 2 (Tue) | Refine prompts, test edge cases | Gauge |
| Day 3 (Wed) | Build minimal UI, integrate end-to-end | Hugo, Rene |
| Day 4 (Thu) | Testing, bug fixes, documentation | All |
| Day 5 (Fri) | Demo prep, final testing, record backup video | All |

---

## Resources Needed

- **OpenAI API key** - Sign up at platform.openai.com (Gauge to set up)
- **Estimated API cost for spike:** $5-10
- **Development environment:** 
  - Node.js 18+ (Hugo)
  - Python 3.10+ (Rene, Gauge)
- **Test data:** Sample budgets (see examples above)

---

## Sample Prompts to Test

### Prompt v1 (Basic)
```
Analyze this budget and provide insights:
Income: $3000
Expenses: Rent $1200, Food $400, Transportation $150...
```

### Prompt v2 (Structured with Rules)
```
You are a friendly budget educator. Analyze the following budget data.

RULES:
1. Use simple language (no jargon)
2. Calculate percentages for each category
3. Compare to the 50/30/20 rule
4. Give 3-4 specific tips
5. End with a disclaimer

BUDGET DATA:
[user data here]
```

### Prompt v3 (System + User Message)
```
System: You are a helpful budget educator for young adults. 
Explain concepts simply. Never give investment advice.
Always include a disclaimer.

User: Please analyze my budget:
Monthly income: $3000
Rent: $1200
Food: $400
...
```

**Gauge will test all three approaches and document which works best.**

---

## Notes

```
Space for team notes during the spike:

- 
- 
- 

```

---

*Last Updated: February 15, 2026*
