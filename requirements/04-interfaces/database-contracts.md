# Database Contracts

## Purpose

This document records database ownership, access rules, and cross-subsystem persistence contracts.

## Current Status

No database contracts have been approved.

## Rules

- Each durable entity should have an owning subsystem.
- Cross-subsystem writes require explicit approval.
- Shared tables require explicit architectural justification.
- Migrations should be traceable to requirement IDs where practical.
