---
name: feature-grouping
description: Group discovered features into coherent capabilities, modules, milestones, or user journey areas. Use when organizing a feature map, reducing duplicate work, or aligning features with ownership and deep abstractions.
---

# Feature Grouping

## Definition

Organize features by the knowledge they share and the outcome they support. Grouping should reduce complexity by revealing owner modules and reusable abstractions, not by creating vague buckets.

## Questions To Ask

- Which features share business rules or data?
- Which features serve the same journey phase?
- Which features must change together?
- Which group can become a deep module?
- Which group is only a temporary label?

## Existing Project Comparison

- Compare groups with current modules, folders, routes, entities, and teams.
- Flag groups that mirror technical layers instead of domain meaning.
- Find features that currently live in the wrong module.
- Look for duplicated concepts with different names.

## Suggestive Plan

1. Group by outcome and domain knowledge first.
2. Cross-check by journey phase and user type.
3. Name groups with domain vocabulary.
4. Assign likely owner modules.
5. Split vague groups and merge tiny shallow groups.

## Example

Scheduling group: request slot, validate availability, reserve slot, notify parties, cancel appointment. It shares time, availability, and status rules.

## Vocabulary

- Feature group: coherent set of related features.
- Capability: a stable product ability users rely on.
- Domain vocabulary: names used by the business and users.
- Owner module: module responsible for the group's rules.
- Shallow group: collection that has a name but no shared knowledge.

## Expected Outcome

Produce a grouped feature map with group name, purpose, included features, owner module, shared rules, and boundaries.
