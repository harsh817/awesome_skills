---
name: video-quality-review-fix
description: Review rendered AI-assisted videos for production quality, identify exact failures, and decide whether to regenerate clips or fix them in edit.
metadata:
  short-description: Review and fix weak video sections
---

# Video Quality Review Fix

Use this skill after a render, when the user reports a bad section, or when a video must be made production ready.

## Review Priorities

Look for:

- Incoherent story progression.
- Repeated or looping clips.
- Wavering, morphing, or deformation.
- Abrupt transitions.
- Bad timestamp handoffs.
- Overlays that hide important visual information.
- Captions or labels that feel internal or unclear.
- Audio/visual mismatch.
- Human-centered scripts represented with abstract avatars, faceless placeholders, generic silhouettes, or symbolic cards when realistic human faces or bodies are needed for credibility.

## Timestamp Method

When the user names a timestamp range, inspect that range directly. Create proof frames around it when possible. Do not judge the whole video from memory.

## Fix Decision

Choose the smallest reliable fix:

- Regenerate a dedicated short clip when motion itself is broken.
- Replace a failed generated segment with a still/keyframe when motion is not needed.
- Use Hyperframes overlays, bridges, or callouts when the visual is good but the edit logic is unclear.
- Rework timing when a transition feels rushed or disconnected.

## Production Standard

Do not call a video production ready only because it rendered. It should have:

- Coherent scene logic.
- Clear viewer takeaway.
- Main visuals that match the script's subject. For face, DP, hairstyle, beard, outfit, grooming, or styling content, this usually means realistic human visuals instead of abstract placeholders.
- Controlled transitions.
- No obvious deformation in key frames.
- Proof sheet or sampled frames for the changed area.

## Response

Lead with the real issue, then the fix. Be direct if the output is not good enough.
