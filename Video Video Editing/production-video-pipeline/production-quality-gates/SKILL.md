---
name: production-quality-gates
description: Manage approval gates for AI video production so product goal, creative direction, style, storyboard, assets, clips, edit, and final review are explicitly accepted before moving forward.
metadata:
  short-description: Gate AI video production quality
---

# Production Quality Gates

Use this skill when building or managing an AI-assisted video production workflow that needs clear checkpoints, approvals, rework decisions, and proof before final delivery.

## Purpose

This skill turns video production into a gated process. It prevents weak ideas, wrong visual language, bad keyframes, poor generated clips, or unfinished edits from moving forward only because they technically rendered.

## Gate File

For every serious video project, create or maintain a `PRODUCTION_GATES.md` file in the project folder. Use [references/gate-template.md](references/gate-template.md) when creating a new gate file.

The gate file is the production control surface. It should show:

- Current production stage.
- Gate status.
- Decision owner: user, Codex, or both.
- Required proof.
- Pass criteria.
- Rework notes.
- Next allowed action.

## Gate Statuses

Use only these statuses:

- `pending`: gate has not been reviewed yet.
- `approved`: gate passed and the next stage may begin.
- `needs-fix`: gate failed and must be corrected before moving forward.
- `waived`: user explicitly accepts the risk and allows the next stage.

Do not silently treat a failed gate as approved.

## Required Gates

Use these gates for production video work:

0. `G0 Product / Goal Intake`
   - Confirms the product or offer, target viewer, business goal, desired viewer action, belief shift, proof, emotional direction, and constraints.
   - Blocks creative work if the video has no clear commercial or strategic purpose.

1. `G1 Creative Brief`
   - Confirms audience, objective, emotional hook, promise, and core message.
   - Blocks production if the idea is vague or the viewer takeaway is unclear.

2. `G2 Style Direction`
   - Confirms the editing style, reference language, typography, overlay rules, and what must not be copied.
   - Blocks production if the style choice hurts the story. Example: a heatmap on a face may be rejected as awkward even if the reference used diagnostic overlays.

3. `G3 Storyboard`
   - Confirms shot count, timing, narration mapping, visual job of each shot, and transition logic.
   - Blocks generation if shots are generic, repetitive, or not tied to the script.

4. `G4 Keyframes`
   - Confirms human realism, identity consistency, styling, framing, and suitability for video generation.
   - Blocks video generation if faces, hands, bodies, clothes, or backgrounds are visibly poor.

5. `G5 Generated Clips`
   - Confirms generated video clips have usable motion and no major deformation, wavering, morphing, identity drift, or repeated dead motion.
   - Blocks editing if the core visual material is weak.

6. `G6 Edit Preview`
   - Confirms timing, pacing, captions, overlays, transitions, audio sync, and reference-style application.
   - Blocks final render if the edit feels cheap, confusing, or disconnected.

7. `G7 Final Quality`
   - Confirms the final render meets the brief, style, story, and technical requirements.
   - Requires proof frames or contact sheets plus technical validation.

## Operating Rule

Before starting any major stage, check the previous gate. If it is not `approved` or explicitly `waived`, stop and repair the previous stage first.

When the user explicitly asks to move fast, keep the gates but make each review shorter. Do not remove the gates unless the user asks to skip them.

## Handoff Rules

Use gates to coordinate the specialist skills:

- `product-goal-intake` produces the `G0 Product / Goal Intake` packet.
- `marketing-creative-director` produces the `G1 Creative Brief` packet from the approved G0 packet.
- `editing-style-director` produces the `G2 Style Direction` packet.
- `video-storyboard-planner` produces the `G3 Storyboard` packet.
- `imagegen`, ComfyUI image workflows, or other image tools produce `G4 Keyframes`.
- `comfyui-video-generation` produces `G5 Generated Clips`.
- `hyperframes-video-editing` produces `G6 Edit Preview`.
- `video-quality-review-fix` owns `G7 Final Quality` and any failed gate review.

## Review Behavior

Be direct about failures. If a visual idea is wrong, say why and mark the gate `needs-fix`. Do not soften the gate result because work has already been done.

Each review should answer:

- What passed?
- What failed?
- What is the likely cause?
- What exact fix is needed?
- Can the next stage proceed?
