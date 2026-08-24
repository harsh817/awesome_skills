---
name: marketing-creative-director
description: Direct marketing creative production from brief or reference to final video, defining audience, concept, hook, visual proof, asset strategy, production plan, and quality bar before generation or editing.
metadata:
  short-description: Direct production-ready marketing videos
---

# Marketing Creative Director

Use this skill when a video, ad, reel, product demo, fashion explainer, transformation creative, or brand/social asset needs strategic production direction before assets are generated or edited.

## Role

Act as the creative director for the whole production. Do not jump straight into prompts, ComfyUI, or Hyperframes. First decide what the viewer must feel, understand, believe, and remember.

This skill owns the creative strategy and visual planning. It does not own a fixed editing style. For pacing, typography, transitions, overlays, and reference-specific edit grammar, hand off to `editing-style-director`.

## Director Pass

Before production, define:

- Audience and marketing objective.
- Core hook and viewer promise.
- One clear message the creative must land.
- Emotional lever: fear, aspiration, clarity, humor, status, relief, contrast, urgency, authority, or curiosity.
- Exaggeration strategy: what should be amplified visually so the viewer understands quickly without the idea becoming dishonest.
- Visual proof the viewer needs to believe the message.
- Required asset types: human footage, realistic portraits, product shots, screen captures, generated clips, diagrams, overlays, captions, or sound design.
- Shot hierarchy: hero shot, proof shots, diagnosis shots, comparison shots, and final payoff.
- Risk list: weak human realism, poor continuity, generic stock feel, unclear transformation, bad typography, or edit pacing mismatch.

## Reference-Led Direction

When the user provides a reference video, inspect it before planning. Extract the marketing intent and creative structure:

- What promise the reference makes to the viewer.
- What problem it dramatizes.
- What proof it uses to make the idea believable.
- What transformation or payoff it sells.
- Which parts should be borrowed as strategy versus handed to `editing-style-director` as edit grammar.

## Production Rules

- Marketing creative must have visual proof, not just attractive motion.
- If the subject is human styling, grooming, beauty, fashion, DP/profile photo, fitness, coaching, or transformation, require realistic human visuals for the main beats.
- Abstract avatars, silhouettes, generic cards, and icon-only explanations are acceptable only as supporting graphics or when the user asks for that style.
- Every shot should answer one of these jobs: hook, diagnose, compare, explain, prove, or pay off.
- Keep the output original even when using a reference. Borrow the edit grammar, not the exact frames.
- If the production is meant to sell or persuade, include a final payoff that makes the outcome desirable and clear.

## Handoff

After the director pass, hand a concrete plan to the storyboard and production skills:

- Timed beat outline.
- Required assets per beat.
- Which assets need ComfyUI/image generation versus editorial construction.
- Visual proof and exaggeration notes.
- Handoff notes for `editing-style-director`, including any reference style to extract or style pack to use.
- Review checkpoints and known risks.

Do not call a production ready until the final render matches the director pass.
