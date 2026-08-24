---
name: production-video-pipeline
description: Run a full production video workflow from reference analysis to storyboard, ComfyUI clip generation, Hyperframes editing, quality review, and final proof.
metadata:
  short-description: Produce coherent AI-assisted videos end to end
---

# Production Video Pipeline

Use this skill when the user wants a polished short-form video made from a reference, concept, product, outfit, or visual style. The goal is not just to generate clips; it is to produce a coherent edited video with proof that it works.

## Operating Shape

Treat the work as a production pipeline:

1. Analyze the reference or concept before generating anything.
2. Build a timed storyboard with clear visual beats.
3. Generate only the motion clips that are needed, preferably in short controlled segments.
4. Assemble the final piece in Hyperframes with timing, captions, overlays, callouts, transitions, and audio.
5. Review the rendered result at problem timestamps and fix weak sections.
6. Deliver the final MP4 plus proof frames/contact sheets and validation notes.

## Skill Routing

Use the specialist skills when the task touches their area:

- Use `reference-video-analysis` when a source video, inspiration clip, or existing output needs to be studied.
- Use `video-storyboard-planner` when deciding shot count, timing, prompt direction, or scene logic.
- Use `comfyui-video-generation` when generating clips through ComfyUI, MiniMax, LTX, or similar local workflows.
- Use `fashion-visual-direction` for fashion, outfit, styling, dress explanation, body-shape logic, and pointer/callout copy.
- Use `hyperframes-video-editing` for final assembly, motion graphics, callouts, audio sync, contact sheets, validation, and render.
- Use `video-quality-review-fix` after every render or when the user says a section is incoherent, repetitive, wavering, deformed, or not production ready.

## Production Rules

- Do not rely on a single long AI video generation for the full video. Long generations are more likely to drift, repeat, or lose coherence.
- Use short clips for visual motion, then use Hyperframes to create the edited story.
- If the script or concept depends on a person, face, DP/profile photo, hairstyle, beard, outfit, body type, beauty, grooming, or before/after appearance, require realistic human key visuals before the edit. Do not substitute abstract avatars, silhouettes, or generic icons unless the user explicitly asks for that style.
- Preserve the user's intent from the reference, but make the output original unless they explicitly ask for a duplicate.
- If a timestamp fails, inspect that timestamp directly instead of guessing from the whole video.
- When a visual beat breaks coherence, first decide whether it needs regeneration, replacement with a still/keyframe, or editorial repair in Hyperframes.
- Prefer proof sheets around the changed timestamp over only saying the render completed.

## Delivery Standard

A finished response should include:

- Final video path.
- Proof image/contact sheet path.
- What changed.
- Validation result.
- Any remaining quality risk, if real.
