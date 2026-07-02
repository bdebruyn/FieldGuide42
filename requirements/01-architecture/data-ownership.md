# Data Ownership

## Purpose

This document records which subsystem owns which data.

## Data Ownership Table

| Data Entity | Owning Subsystem | Consumers | Notes |
|---|---|---|---|
| TBD | TBD | TBD | TBD |

## Rules

- Each durable data entity should have one owning subsystem.
- Other subsystems may consume data through documented interfaces.
- Shared database access should not be assumed without an explicit architectural decision.
