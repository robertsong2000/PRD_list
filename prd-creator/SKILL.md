---
name: prd-creator
description: Guide users through creating comprehensive Product Requirements Documents (PRD). Use when users need to: (1) Write a PRD or product spec, (2) Create requirements documentation, (3) Draft feature specifications, (4) Define product scope and requirements. Supports structured workflow from context gathering to document completion with templates for various project types.
---

# PRD Creator

Guide users through a structured workflow for creating Product Requirements Documents (PRDs).

## Workflow Overview

```
Stage 1: Context Gathering → Stage 2: Document Building → Stage 3: Review & Refine
```

Offer this structured workflow to users. If they decline, work freeform.

---

## Stage 1: Context Gathering

Goal: Collect all necessary information before writing.

### 1.1 Initial Questions

Ask the user:

1. **Target audience**: Who will read this PRD? (developers, stakeholders, PMs)
2. **Purpose**: What's the goal? (guide development, get approval, define scope)
3. **Technical constraints**: Any preferred tech stack or limitations?
4. **Timeline**: Expected delivery timeframe?

### 1.2 Project-Specific Questions

Based on the project type, ask relevant questions. Common categories:

| Category | Questions |
|----------|-----------|
| User scale | How many users? Peak concurrent users? |
| Deployment | Cloud, on-premise, local server? |
| Existing systems | Migration needed? Existing data/code? |
| Features | Must-have vs nice-to-have? |
| Terminals | Web only? Mobile? Desktop? |

Encourage users to dump all context they have. Ask clarifying questions to fill gaps.

### 1.3 Transition

When sufficient context gathered, ask: "Ready to move to document building?"

---

## Stage 2: Document Building

Goal: Build the PRD section by section.

### 2.1 Document Structure

For most PRDs, recommend this structure:

```
1. 文档概述 (Document Overview)
   ├── 文档信息
   ├── 修订历史
   └── 项目背景

2. 产品概述 (Product Overview)
   ├── 产品定位
   ├── 目标用户
   └── 核心价值

3. 角色与权限体系 (Roles & Permissions)
   ├── 角色定义
   └── 权限矩阵

4. 功能需求 (Functional Requirements)
   ├── P0: 核心功能 (MVP)
   ├── P1: 重要功能
   └── P2: 增强功能

5. 非功能需求 (Non-functional Requirements)
   ├── 性能要求
   ├── 安全要求
   └── 兼容性要求

6. 数据模型 (Data Model)
   ├── 核心实体定义
   └── 实体关系

7. 业务流程 (Business Processes)
   ├── 核心流程图
   └── 状态流转

8. 界面设计规范 (UI/UX Specifications)
   ├── 整体布局
   └── 关键页面说明

9. 技术建议 (Technical Recommendations)
   ├── 技术栈推荐
   ├── 架构设计
   └── 开发优先级

10. 附录 (Appendix)
    ├── 术语表
    └── 参考文档
```

Ask if this structure works or needs adjustment.

### 2.2 Build Section by Section

For each section:

1. **Ask clarifying questions** about what to include
2. **Draft the content** based on gathered context
3. **Get feedback** and iterate

**Key principles:**
- Start with the most important sections (usually functional requirements)
- Keep MVP focus for tight timelines
- Use tables for structured data (permissions, data models)
- Use Mermaid diagrams for workflows
- Be concise - every sentence should carry weight

### 2.3 Quality Check

After drafting, review for:
- Consistency across sections
- Missing requirements
- Ambiguous descriptions
- Over-engineering (remove unnecessary complexity)

---

## Stage 3: Review & Refine

Goal: Ensure the PRD works for readers.

### 3.1 Self-Review

Read the complete document and check:
- Flow and consistency
- Redundancy or contradictions
- Whether every section adds value

### 3.2 User Confirmation

Ask the user to review and provide feedback. Common refinements:
- Simplify technical stack for small projects
- Clarify ambiguous requirements
- Add missing edge cases
- Adjust priorities

---

## Templates

### PRD Template

See [assets/prd-template.md](assets/prd-template.md) for a complete PRD template.

### Common Sections

| Section | Purpose |
|---------|---------|
| 功能需求 | List features with priority (P0/P1/P2), include function IDs |
| 数据模型 | Define entities with field name, type, required, description |
| 权限矩阵 | Use table with roles as columns, features as rows |
| 业务流程 | Use Mermaid flowchart syntax |

---

## Tips

**For tight timelines (1-2 months):**
- Focus on P0 features only
- Suggest simpler tech stack
- Recommend phased implementation
- Use "先做能用，再做好用" principle

**For small teams (<10 users):**
- Simplify architecture
- Avoid microservices, complex auth
- Prefer SQLite over PostgreSQL
- Consider monolithic design

**Writing style:**
- Use imperative form in instructions
- Be specific with numbers (not "fast response" but "<2 seconds")
- Include examples in data model definitions
