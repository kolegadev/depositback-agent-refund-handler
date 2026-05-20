# Refund Handler

> **Agent**: `depositback-agent-refund-handler`  
> **Group**: Operations  
> **Product**: DepositBack — Security Deposit Demand Letter Service

## Purpose

Validates refund requests against 30-day guarantee terms, processes Revolut refund, updates analytics, and sends closure email. Tracks refund rate target <10%.

## DepositBack Context

DepositBack is a single-page, no-signup transactional product for US renters seeking to recover security deposits. The entire customer journey fits on one URL: landing page → 6-question form → Revolut payment → PDF emailed. Conversion rate target: **4% visitor-to-purchase minimum**.

## Inputs

- Refund request emails
- Purchase records from purchase-orchestrator

## Outputs

- Refund confirmations → funnel-analyst inbox
- Refund reason logs → operations/cohort-analysis

## Human Escalation Points 🛑

- Refund rate exceeds 10%
- Fraudulent refund patterns
- Revolut API errors

## Skills

| Skill | Description | Status |
|-------|-------------|--------|
| `noop` | Health check / pipeline verification | ✅ Active |
| `execute` | Primary function for this agent | 🔧 Planned |

## Workflow

1. Poll `data/inbox/` for task manifests from upstream agents.
2. Resolve required skills (local `skills/` or ClawHub fallback).
3. Execute workflow.
4. Write artifacts to `data/outbox/`.
5. Update `data/state.json`.

## Runtime

```bash
pip install -r requirements.txt
python runtime/main.py
```
