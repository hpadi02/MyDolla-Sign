# Product Requirements Document (PRD)
## My Dolla $ign - Budget Education Platform

**Version:** 1.0  
**Date:** February 15, 2026  
**Authors:** Hugo, Rene, Gauge, Allison

---

## 1. Problem + Target Users

**Problem:** Many young adults and first-time earners lack access to trustworthy, easy-to-understand financial education. Without proper guidance, they struggle with basic budgeting and saving habits, leading to poor financial decisions, unnecessary stress, and debt accumulation.

**Target Users:** 
- College students managing money for the first time
- Young adults (18-30) entering the workforce
- First-time earners with limited financial education background

**Why It Matters:** Financial literacy is a critical life skill that affects long-term well-being. By providing accessible budgeting education early, we can help users build healthy financial habits and avoid common pitfalls like overspending and poor savings practices.

---

## 2. Goal / Success Metrics

| Metric | Target | How We'll Measure |
|--------|--------|-------------------|
| User Comprehension | 80%+ users understand their budget breakdown | Post-analysis survey |
| Task Completion | Users complete budget input in < 5 minutes | Time tracking |
| User Satisfaction | 4/5 average rating | In-app feedback form |
| AI Response Quality | Accurate, helpful budget explanations | Manual review of outputs |

---

## 3. MVP User Stories

1. **As a** student, **I want** to input my monthly income and expenses, **so that** I can see a clear breakdown of where my money goes.

2. **As a** first-time earner, **I want** to receive AI-generated explanations of my spending patterns, **so that** I can understand my financial habits.

3. **As a** young adult, **I want** to learn budgeting concepts in simple terms, **so that** I can make better financial decisions.

4. **As a** user, **I want** to categorize my expenses (rent, food, entertainment, etc.), **so that** I can identify areas where I might overspend.

5. **As a** user, **I want** to receive personalized budgeting tips based on my data, **so that** the advice is relevant to my situation.

6. **As a** user, **I want** to see visual representations of my budget, **so that** I can quickly understand my financial snapshot.

7. **As a** user, **I want** the platform to be simple, **so that** I don't feel overwhelmed by financial terminology.

---

## 4. MVP Scope vs. Non-Goals

### Must-Have Features (MVP)

1. **Budget Input Form**
   - Income input field (monthly, after taxes)
   - Expense categories: Rent/Housing, Food/Groceries, Transportation, Entertainment, Utilities, Savings, Other
   - Simple, clean UI with real-time total calculation

2. **AI-Generated Budget Analysis**
   - Spending pattern explanation in plain English
   - Category-by-category breakdown with percentages
   - Personalized budgeting tips based on user's data
   - Explanation of budgeting concepts (like the 50/30/20 rule)

3. **Results Display**
   - Clear budget summary showing income vs. expenses
   - Visual breakdown (progress bars showing percentage per category)
   - Actionable insights list

### Nice-to-Have Features (Post-MVP)

- User accounts and saved budgets
- Budget tracking over time (month-to-month comparison)
- Pie chart or bar chart visualization
- Mobile-responsive design improvements
- Export budget summary as PDF

### Non-Goals (What We Will NOT Build)

- **No investment advice** - We provide budgeting education only, not stock/investment recommendations
- **No stock trading features** - This is not a brokerage or investment platform
- **No real-time market data** - We focus on personal budgeting, not markets
- **No user authentication for MVP** - Simplified single-session experience
- **No payment processing** - Free educational tool
- **No data persistence** - Budgets are not saved between sessions (MVP)

---

## 5. Acceptance Criteria

### Budget Input Form
- [ ] User can enter monthly income (positive numbers only)
- [ ] User can enter expenses in at least 6 categories
- [ ] Form shows real-time total of expenses
- [ ] Form shows remaining balance (income minus expenses)
- [ ] Form validates that all inputs are non-negative numbers
- [ ] Form submits successfully and shows loading state

### AI Analysis
- [ ] AI generates budget explanation within 10 seconds
- [ ] AI response is in plain English (no financial jargon)
- [ ] AI provides at least 3 actionable insights
- [ ] AI explains what the 50/30/20 rule is
- [ ] AI handles edge cases (zero income, expenses exceeding income)
- [ ] AI includes disclaimer that this is educational, not financial advice

### Results Display
- [ ] Shows clear breakdown of each expense category
- [ ] Shows percentage of income for each category
- [ ] Displays visual progress bars for each category
- [ ] Lists key insights in bullet point format

### General
- [ ] Application loads without errors
- [ ] All text is readable and accessible
- [ ] Works on desktop browsers (Chrome, Firefox, Safari)
- [ ] Page is usable (not necessarily optimized) on mobile

---

## 6. Assumptions + Constraints

### Assumptions
- Users have basic computer/internet literacy
- Users will provide honest income/expense data
- OpenAI API will remain available and affordable for our use case
- Users understand this is for educational purposes only
- Users are inputting monthly (not weekly/yearly) figures

### Constraints

| Constraint Type | Details |
|----------------|---------|
| **Time** | MVP must be complete by Milestone 2 |
| **Budget** | Limited API costs - must optimize token usage |
| **Data** | No access to real financial data; user-provided only |
| **Ethics** | Must include disclaimers that this is NOT financial advice |
| **Platform** | Web-based only for MVP; no mobile app |
| **API Limits** | OpenAI rate limits and costs must be managed |

### Privacy & Ethics Considerations
- No personal financial data is stored permanently (MVP)
- Clear disclaimers that AI-generated content is educational, not professional advice
- No collection of personally identifiable information
- User data is only used for the current session analysis

---

## Appendix: Team Task Distribution

| Section | Primary Owner | Reviewer |
|---------|--------------|----------|
| Problem + Users | Allison | Gauge |
| Success Metrics | Allison | All |
| User Stories | Gauge, Allison | All |
| MVP Scope | Hugo, Rene | All |
| Acceptance Criteria | Allison | Hugo, Rene |
| Assumptions | All | All |

### Individual Responsibilities

**Hugo (Frontend Lead)**
- Budget input form UI
- Results display component
- Visual breakdown (progress bars)
- Loading states and error handling
- Responsive design

**Rene (Backend Lead)**
- Flask API setup
- Budget analysis endpoint
- Input validation
- Error handling and logging
- API documentation

**Gauge (AI/ML Lead)**
- OpenAI API integration
- Prompt engineering for budget analysis
- AI response quality testing
- Edge case handling
- Fallback responses when API fails

**Allison (Documentation & QA)**
- PRD maintenance
- Testing all features
- Bug documentation
- User testing coordination
- Pitch deck preparation

---

*Last Updated: February 15, 2026*
