# Full System Review

A system review asks whether the parts work together clearly and reliably. It is not only a final check. It is a way to understand the system.

## Review Path

Use this path whenever you need to understand a feature:

```mermaid
flowchart LR
    UI[React component] --> Event[User action]
    Event --> Request[HTTP request]
    Request --> Route[Flask route]
    Route --> Query[SQLite query]
    Query --> Response[JSON response]
    Response --> State[React state update]
    State --> Screen[Updated screen]
```

For example:

> A user creates a new risk review record.

Trace it as:

1. The user fills in a React form.
2. React sends a `POST /api/reviews` request.
3. Flask validates the request body.
4. Flask inserts a row into SQLite.
5. Flask returns the created review record as JSON.
6. React updates state and shows the new review record.

## API Contract

The API contract is the agreement between frontend and backend.

For `GET /api/reviews`, React expects:

```json
[
  {
    "id": 1,
    "applicant_name": "Avery Tan",
    "product_type": "Personal Loan",
    "risk_band": "Medium",
    "model_score": 0.67,
    "review_date": "2026-09-18",
    "analyst_note": "Stable income, moderate utilization."
  }
]
```

For `POST /api/reviews`, Flask expects:

```json
{
  "applicant_name": "Avery Tan",
  "product_type": "Personal Loan",
  "risk_band": "Medium",
  "model_score": 0.67,
  "review_date": "2026-09-18",
  "analyst_note": "Stable income, moderate utilization."
}
```

## Review Checklist

- Can you run the backend from a clean terminal?
- Can you run the frontend from a clean terminal?
- Can you explain every API route?
- Can you find where each database field is created?
- Can you trace one user action from the browser to SQLite?
- Can you explain one error you fixed during development?

## Common Failure Modes

| Symptom | Likely area to inspect |
| --- | --- |
| Page is blank | Browser console and React code |
| API request fails | Network tab, Flask terminal, URL |
| Data disappears after restart | SQLite connection or insert logic |
| CORS error appears | Backend CORS configuration |
| Wrong fields appear | API contract mismatch |

## Final Reflection

A complete system is not a pile of files. It is a set of cooperating parts with clear responsibilities.

When you can explain the flow of data, you are no longer only using the code. You are reading the system.

## Review Questions

1. What is an API contract?
2. Where should you look first if the page is blank?
3. What does it mean to trace data through the system?
