# Finance_Assistant_Blueprint

A minimal AI-driven budgeting blueprint with:

- **Transaction Categorization** (Food, Rent, Entertainment, Transport, Utilities, Other)
- **Expense Tracking & Visualization Payloads** (category breakdown + monthly trend data)
- **AI-Powered Budgeting Suggestions** (personalized, spending-aware recommendations)
- **Data Integration** through both **CSV upload** and **Plaid-style transaction payloads**

## Quick usage

```python
from finance_assistant.core import (
    load_transactions_from_csv,
    load_transactions_from_plaid,
    dashboard_data,
    generate_budget_suggestions,
)

csv_data = "date,description,amount\n2026-05-01,Supermarket,120.50\n"
transactions = load_transactions_from_csv(csv_data)

plaid_transactions = load_transactions_from_plaid({
    "transactions": [
        {"date": "2026-05-02", "name": "City Metro", "amount": 35.0, "category": ["Travel", "Transport"]}
    ]
})

dashboard = dashboard_data(transactions + plaid_transactions)
suggestions = generate_budget_suggestions(transactions + plaid_transactions, monthly_income=3000)
```

## Tests

```bash
python -m unittest discover -v
```
