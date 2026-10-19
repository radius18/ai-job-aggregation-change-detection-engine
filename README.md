# Automated AI Job Aggregation & Change-Detection Engine

A Python-based portfolio project for collecting, normalizing, tracking, and inspecting AI-related job postings while preserving source identity, lifecycle state, and run-level evidence.

**Status:** Work in progress · October 2026–Present

## Project Overview

The engine is designed to do more than collect listings. It separates source retrieval, normalization, identity, lifecycle tracking, and human inspection so each job record can be traced back to the source observation that produced it.

Current work includes structured workflows for recruiting platforms such as Greenhouse, Lever, and Ashby, with additional acquisition methods planned for sources that do not expose suitable structured endpoints.

## Read-Only Inspector

![Plan V Inspector overview](Screenshot%202026-10-19%20004221.png)

*Read-only local Inspector showing a healthy Ashby/Perplexity source run, 133 canonical open jobs, source health, run completeness, and a job overview.*

The Inspector is intentionally read-only: it can inspect stored evidence but does not publish jobs, alter lifecycle state, activate referrals, or start live retrieval.

## Normalized Job Record & Provenance

![Normalized job record](Screenshot%202026-10-19%20004309.png)

*Detailed normalized record preserving source identity, job metadata, normalized description, version information, and the link back to the originating posting.*

The system keeps source-specific observations separate from normalized job data so derived fields remain inspectable instead of becoming opaque copied text.

## Ingestion Run & Health Validation

![Healthy ingestion run](Screenshot%202026-10-19%20004338.png)

*Run-level evidence showing a complete, healthy Ashby/Perplexity retrieval with 133 declared observations and 133 stored observations.*

Run records preserve completeness, source health, observed/stored counts, artifacts, and errors so the collection pipeline can be evaluated independently from the job content itself.

## Core Capabilities

- structured source ingestion
- normalization into a common job model
- source identity and provenance preservation
- same-source duplicate protection
- lifecycle and change detection
- run history and source health
- database-backed storage and migrations
- read-only human inspection
- explicit separation between retrieval, inspection, publishing, and application actions

## Design Priorities

### Provenance first

Normalized fields should remain traceable to source evidence. The system avoids treating a normalized value as authoritative simply because it exists in the database.

### Preserve platform identity

The same real-world role can appear on more than one recruiting platform. The engine preserves those separate platform observations rather than collapsing them into one record without evidence.

### Fail closed on uncertain authority

Inspection, publishing, referral routing, and application submission are separate capabilities. A successful retrieval run does not automatically authorize downstream actions.

### Historical comparison

Stored observations and job versions support future change detection such as newly added, removed, reopened, or materially changed listings.

## Skills Demonstrated

- Python
- API / structured data integration
- data normalization
- data validation and QA/UAT
- SQL / database-backed workflows
- provenance and lifecycle modeling
- change detection
- workflow automation
- requirements analysis
- debugging and regression testing

## Portfolio Scope

This repository is a public portfolio presentation, not the complete private Job Engine source tree or production datastore. Screenshots demonstrate the working Inspector and real shadow-run evidence while internal configuration, protected source policies, test fixtures, and local databases remain outside this public repository.
