# SWS3022 AI/ML for Financial Services

This repository contains one tutorial site for **SWS3022 AI/ML for Financial Services**. The current tutorial is named **FinSight Risk Dashboard** and belongs under the course outcome: "Use reactJS, python-flask, basic DB operations (CURD) to build fintech web applications."

## Local Preview

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

Build the site:

```bash
python -m mkdocs build --strict
```

Serve the generated site:

```bash
python -m http.server 4090 --bind 127.0.0.1 --directory site
```

Open `http://127.0.0.1:4090/`.
