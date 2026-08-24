---
name: video-storyboard-planner
description: Convert a reference analysis or concept into a timed storyboard for a coherent short video with shots, prompts, transitions, captions, and review checkpoints.
metadata:
  short-description: Plan coherent timed video storyboards
---

# Video Storyboard Planner

Use this skill before generating clips. The purpose is to decide what the video should say visually, not to create random attractive shots.

## Planning Inputs

Start from:

- Target duration and aspect ratio.
- Reference analysis or user concept.
- Creative director pass, when available.
- Editing style pass or style pack, when available.
- Required product, outfit, character, or subject.
- Audio source or pacing expectation.
- Output quality target.

## Storyboard Rules

- Use only as many shots as the story needs.
- Assign every shot a timestamp range and purpose.
- Keep the subject consistent across shots.
- When the story is about a real-looking person, profile photo, face, hairstyle, beard, clothes, colors, body shape, grooming, or styling transformation, storyboard realistic human key visuals as mandatory assets. Abstract placeholders, avatar heads, faceless bodies, and symbolic cards are not acceptable for the main visual unless the user requested an illustrative style.
- For marketing creatives, every shot must have a job: hook, diagnose, compare, explain, prove, or pay off.
- Follow the editing style pass for cut rhythm, overlay grammar, caption density, transition behavior, and proof devices.
- Avoid visual jumps that require the viewer to infer missing logic.
- Mark which shots require ComfyUI motion and which can be stills, overlays, or editorial beats.
- Identify risky shots before generation, especially hands, faces, clothing fit, camera turns, and long transformations.

## Recommended Structure For 30s Explainers

For a 30 second fashion or product explainer, a reliable shape is:

- 0-3s: hook and visual promise.
- 3-8s: show the starting item or problem.
- 8-14s: compare or demonstrate the mistake.
- 14-20s: explain why it fails.
- 20-24s: introduce the fix without breaking visual continuity.
- 24-30s: final look, callouts, or payoff.

Adjust timing based on the reference and audio. Do not force this structure when the story clearly needs another one.

## Output

Return a timed storyboard with:

- Shot number.
- Time range.
- Visual description.
- Required visual asset type, such as realistic portrait, phone UI, product shot, generated motion clip, still bridge, or overlay.
- Motion instruction.
- Caption or overlay text.
- Generation method.
- Review checkpoint.
