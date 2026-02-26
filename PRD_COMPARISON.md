# PRD Comparison: Content-Curator vs Foundry-Stack Template

**Date:** 2026-02-26  
**Author:** Climb  
**Purpose:** Compare content-curator PRD against foundry-stack template standards

---

## Gap Analysis

### ✅ Current Strengths

1. **Clear Product Vision** — The one-liner and market gap analysis are strong
2. **Good Competitive Analysis** — "Blue ocean" insight is well-documented
3. **Comprehensive Feature Requirements** — MVP vs V2/V3 breakdown is clear
4. **Technical Architecture** — Stack choices are documented with rationale
5. **Cost Analysis** — AI/API costs and unit economics are well-thought-out
6. **4-Week Build Plan** — Tactical, day-by-day breakdown

### ❌ Missing Elements (Required by Foundry-Stack Template)

#### 1. **PRD Index Structure**
- **Missing:** Master index with file map, glossary, cross-cutting concerns
- **Foundry has:** PRD_INDEX.md as entry point linking to 18 specialized PRDs
- **Action:** Split monolithic PRD into modular PRDs

#### 2. **Architecture Decision Log (ADL)**
- **Missing:** Formal table documenting key decisions and rationale
- **Foundry has:** AD-001 through AD-021 with "Options Considered" and "Choice" columns
- **Action:** Create ADL table for key decisions

#### 3. **Functional Requirements (FR-XXX)**
- **Missing:** Numbered, testable requirements
- **Foundry has:** FR-AUTH-001, FR-BILLING-012, etc.
- **Action:** Convert features into FRs with pass/fail criteria

#### 4. **Cross-Cutting Concerns**
- **Missing:** Error handling, logging, security, performance patterns
- **Foundry has:** Dedicated section for RLS patterns, error handling, naming conventions
- **Action:** Document error handling, RLS policies, naming conventions

#### 5. **Database Indexes**
- **Present but incomplete:** Schema tables exist, indexes missing
- **Foundry has:** Full index definitions for query optimization
- **Action:** Add indexes for common queries

#### 6. **Tech Stack Version Table**
- **Missing:** Explicit version numbers for dependencies
- **Foundry has:** Table with technology + version + notes
- **Action:** Add versions for all major dependencies

---

## Immediate Actions (Priority Order)

### High Priority (Do First)

1. **Create ADL table** — Document key architectural decisions
2. **Add functional requirements** — Convert features into testable FRs
3. **Define success metrics** — Quantitative targets
4. **Document RLS policies** — Security model for user data
5. **Add database indexes** — Query optimization

### Medium Priority (Do Next)

6. **Split into modular PRDs** — Follow foundry-stack structure
7. **Add DX section** — Setup instructions
8. **Define CI/CD pipeline** — Automated testing and deployment

---

**Total estimated time to foundry-stack parity:** 4-6 hours
