# Run the Starter Project

The starter project for FinSight Risk Dashboard contains a backend folder and a frontend folder. This structure helps you see the boundary between the API and the user interface.

Running the starter project is not a formality. It proves that your machine can run both halves of the system before you start changing code.

## Expected Project Structure

```text
finsight-risk-dashboard/
  backend/
    app.py
    requirements.txt
  frontend/
    package.json
    src/
  README.md
```

The backend and frontend are developed together, but they run as separate local processes.

## Why Two Processes?

The Flask backend and React frontend have different jobs:

- Flask handles API routes such as `GET /api/reviews`.
- React handles browser interaction and screen updates.
- During development, each tool runs its own local server.

Do not close these terminals while testing. If the backend terminal stops, the frontend may still load, but API calls will fail.

## Start the Backend

From the `backend` folder:

```bash
python -m venv .venv
```

Activate the virtual environment.

On Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

Install backend dependencies:

```bash
python -m pip install -r requirements.txt
```

Run Flask:

```bash
python app.py
```

The backend should start on a local port such as `http://127.0.0.1:5000`.

The backend terminal is also a log window. When Flask receives a request, you should see a line appear there. Treat that line as evidence that the request reached the backend.

## Backend Smoke Test

A smoke test is a quick check that a system is alive before deeper testing.

Before starting the frontend, test the backend directly in the browser:

```text
http://127.0.0.1:5000/api/health
```

Expected response:

```json
{
  "status": "ok"
}
```

If the starter project uses a different health route, use the route listed in its `README.md`.

If the health route fails, do not start debugging React yet. The backend must work before the frontend can use it.

## Start the Frontend

Open a second terminal. From the `frontend` folder:

```bash
npm install
npm run dev
```

The frontend should start on a local port such as `http://127.0.0.1:5173`.

The frontend development server serves the React app and refreshes the browser when files change. It is not the same process as Flask.

## What Is Running

```mermaid
flowchart TD
    T1[Terminal 1] --> Flask[Flask backend on port 5000]
    T2[Terminal 2] --> Vite[React dev server on port 5173]
    Browser[Browser] --> Vite
    Vite --> Flask
```

Two terminals are normal. One runs the backend. One runs the frontend.

## First Manual Test

Open the frontend in your browser. Then open the browser developer tools and check the Network tab.

When the page loads, you should see a request to the backend API, such as:

```text
GET /api/reviews
```

Click the request and inspect:

- Request URL
- Method
- Status code
- Response body

For a working starter project, the status code should usually be `200`.

## Reading the Network Tab

The Network tab is the best first tool for full-stack debugging.

| Item | What it tells you |
| --- | --- |
| URL | Whether React called the right backend route. |
| Method | Whether the request was `GET`, `POST`, or something else. |
| Status | Whether Flask accepted, rejected, or crashed on the request. |
| Response | What data Flask returned. |

If no request appears, the problem is probably in React. If the request appears with `500`, inspect the Flask terminal.

## Mini Exercise

Add one fictional review record through the UI. Use this test data:

```text
Applicant: Avery Tan
Product: Personal Loan
Risk band: Medium
Model score: 0.67
Review date: 2026-09-18
Analyst note: Stable income, moderate utilization.
```

After saving, refresh the page. If the record is still visible, the database path is working.

## Small Change Test

Make one small visible change in the frontend, such as changing a table heading from:

```text
Risk Reviews
```

to:

```text
Risk Review Records
```

Save the file and confirm the browser updates. This tells you the frontend development server is watching your files.

## Checkpoint

You are ready to continue when:

- The backend terminal stays running.
- The frontend terminal stays running.
- The browser shows the starter page.
- The Network tab shows at least one API request.
- You can create one fictional review record and see it after refreshing.

## Review Questions

1. Why do the backend and frontend run in separate terminals?
2. What does the React development server do?
3. How can the browser Network tab help you debug?
4. If the frontend page loads but API calls fail, which terminal should you inspect?
