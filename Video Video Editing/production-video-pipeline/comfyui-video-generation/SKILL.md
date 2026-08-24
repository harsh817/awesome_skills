---
name: comfyui-video-generation
description: Generate controlled short video clips through local ComfyUI workflows such as MiniMax H3 or LTX, then collect outputs for final editing.
metadata:
  short-description: Generate ComfyUI video clips safely
---

# ComfyUI Video Generation

Use this skill when the task requires local ComfyUI video generation.

## Core Approach

Generate short, controlled clips rather than one long clip. Use ComfyUI for visual motion, then use an editor such as Hyperframes to build the full story.

## Before Queueing

Check:

- ComfyUI is running and reachable.
- The workflow loads without missing custom nodes.
- Required models exist in the correct folders.
- The requested dimensions match the workflow's expected image/video dimensions.
- The clip duration, frames, and steps are realistic for the available GPU memory.

## Generation Guidance

- Prefer image-to-video from approved keyframes for consistency.
- Keep prompts specific to camera motion, subject action, outfit, and scene.
- Avoid asking one clip to perform multiple story jobs.
- If a clip wavers after a certain timestamp, regenerate that segment as a shorter dedicated clip.
- If a transition breaks cohesion, keep the same subject or background across the handoff.
- Track generated files by shot number and purpose.

## Troubleshooting

When a run stalls:

- Check whether ComfyUI is still processing or waiting on a failed node.
- Inspect GPU VRAM separately from system RAM.
- Stop unused local model servers if memory pressure is real.
- Reduce frames, dimensions, or steps before assuming the workflow is broken.
- Prefer replacing only the bad section instead of rerunning the whole video.

## Output

At the end of generation, report:

- Workflow used.
- Clips generated.
- Duration and resolution.
- Any failed or rejected clips.
- Which clips should go into the Hyperframes edit.

