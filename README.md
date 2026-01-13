# Secure CI/CD with GitHub Actions (DevSecOps Lab)

This repository demonstrates a practical **secure CI/CD pipeline** using GitHub Actions.
It includes quality gates and security checks commonly used in real engineering teams.

## What the pipeline does
- ✅ Lint + tests (CI)
- ✅ SAST with CodeQL
- ✅ Secret scanning with Gitleaks
- ✅ Automated dependency updates with Dependabot

## Workflows
- `.github/workflows/ci.yml` — lint + tests
- `.github/workflows/codeql.yml` — static analysis (SAST)
- `.github/workflows/security-scan.yml` — secret scanning
- `.github/dependabot.yml` — dependency update automation

## How to run locally
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
ruff check .
pytest -q

Evidence
  Actions runs provide the audit trail for:
  build quality (tests/lint),
  security findings (CodeQL),
  secret detection (Gitleaks),
  dependency update PRs (Dependabot).

Next improvements
  Add SBOM generation
  Add container image build + Trivy scan
  Add branch protection + required checks (repo settings)
