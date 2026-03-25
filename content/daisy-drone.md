---
title: "Daisy Drone User manual"
description: "User manual for the Daisy Drone pedal."
draft: false
---

# Operating modes

Daisy Drone is built around three separate sound engines, each opening a different path into sustained sound:

- A dual looper: one side behaves as a familiar looper, while the other transforms the captured phrase into an infinite textured pad.
- A dynamic sampler: again divided into two voices — the sampled micro-loop itself, and its frozen pad counterpart.
- A textured reverb with freezable tails: a reverb that can either trail away naturally or be held in suspension as part of the soundscape.

The operating sound engine is selected with the upmost toggle switch.

{{< toggle-guide patch="Daisy Drone" body="transparent" knobs="transparent" switches="transparent" leds="transparent" active_toggle="1" left_mode="Dynamic sampler" center_mode="Dual looper" right_mode="Textured reverb" >}}

# Dynamic Sampler

## Working Principle

The pedal behaves as a sound grabber that tracks your playing and captures a short loop as soon as you hit a stronger accent. This loop is then smeared by the PaulStretch algorithm and turned into a smooth, endlessly drifting pad.

## Controls

### Loop Footswitch

{{< pedal-bottom-split patch="Daisy Drone" body="transparent" knobs="transparent" switches="transparent" leds="transparent" active_footswitch="right" active_led="right" >}}

**Single tap**: Unmute sampled loop playback. It does **not** directly start recording in this mode. Recording is triggered by the sampler auto-start logic, which depends on the incoming signal level.

**Double tap**: Mute sampled loop playback.

**Hold**: Lock/unlock current loop. While locked, the loop is preserved and will not be overwritten by new captures (the capture will still take place normally, but only to generate the frozen loop).
{{< /pedal-bottom-split >}}

### Freeze Footswitch

{{< pedal-bottom-split patch="Daisy Drone" body="transparent" knobs="transparent" switches="transparent" leds="transparent" active_footswitch="left" active_led="left" >}}

**Single tap**: Unmute stretched sampler playback.

**Double tap**: Mute stretched playback.

**Hold**: Lock/unlock current loop. While locked, the loop is preserved and will not be overwritten by new captures.
{{< /pedal-bottom-split >}}

### Knobs

| Knob | Function | Notes |
| --- | --- | --- |
| **Attack** | Sampler input sensitivity | Higher settings make the sampler auto-start more easily from incoming signal level. The overdub fading mapping on this knob is inactive in this mode. |
| **Fade** | Stretch attack / fade-in | Sets the fade-in time when stretched sampler playback comes in. The slice control is fixed in sampler mode, so this knob does **not** change loop length here. |
| **Pitch** | Harmony pitch interval | Controls the looper harmony voice from one octave down, through unison, up to one octave up. This is most useful when the harmony voice is mixed in with Modulation. |
| **Modulation** | Harmony mix | Blends the original sampler playback with the harmony voice. Lower settings favor the original playback; higher settings favor the harmony voice. |
| **Grit** | Tape-style delay modulation depth | Fully counterclockwise disables the delay block. Any position above minimum turns the modulated delay on and increases the modulation depth. |
| **Blend** | Split crusher / distortion control | Left of center lowers the crusher sample rate for more bitcrushing. Right of center increases distortion gain. Around center, both effects are at their mildest settings. |

# Dual Looper

## Working Principle

The pedal behaves as a micro-looper with a max loop duration of 4.4s. A press on the FREEZE footswitch can smear the loop and turned into a parallel running smooth, endlessly drifting pad.

## Controls

### Loop Footswitch

{{< pedal-bottom-split patch="Daisy Drone" body="transparent" knobs="transparent" switches="transparent" leds="transparent" active_footswitch="right" active_led="right" >}}

**Single tap**: Controls the overdub record cycle. If the looper is idle, the press arms recording. If a loop is already recording, the press requests a stop. When MIDI clock is active, the actual record start can wait for the next clock beat instead of starting immediately.

**Double tap**: Stops loop playback immediately. If recording is active, the current recording is finalized and committed. The second tap does not also trigger the normal single-press action.

**Hold**: Clears the overdub looper state for a fresh restart. Recording and playback are stopped, loop buffers are cleared, and the looper is re-armed to an empty state.
{{< /pedal-bottom-split >}}

### Freeze Footswitch

{{< pedal-bottom-split patch="Daisy Drone" body="transparent" knobs="transparent" switches="transparent" leds="transparent" active_footswitch="left" active_led="left" >}}

**Single tap**: Starts or enables stretched playback. If no stretched layer exists yet and enough loop material is available, the press also kicks off stretch generation. In the current firmware it also toggles the reverb freeze state in the background.

**Double tap**: Stops stretched playback. The second tap also toggles the hidden reverb freeze state once, and it does **not** also trigger the normal single-press action on tap two.

**Hold**: Re-runs stretch generation for the current loop, when enough loop material exists, and enables stretched playback. No dedicated reverb action is routed for the hold gesture.
{{< /pedal-bottom-split >}}

### Knobs

| Knob | Function | Notes |
| --- | --- | --- |
| **Size** | Overdub fading / loop persistence | Controls how much of the existing loop remains when you overdub. Lower settings replace older material more aggressively; higher settings preserve more of the previous loop while layering new audio on top. |
| **Fade** | Loop slice length and stretch fade-in | Its main job is setting the micro-loop slice length. The same knob also sets the fade-in time when stretched playback is started from the alternate footswitch. |
| **Pitch** | Harmony pitch interval | Controls the looper harmony voice from one octave down, through unison, up to one octave up. |
| **Modulation** | Harmony mix | Blends the original loop playback with the harmony voice. Lower settings favor the original loop; higher settings favor the harmony voice. |
| **Grit** | Tape-style delay modulation depth | Fully counterclockwise disables the delay block. Any position above minimum turns the modulated delay on and increases the modulation depth. |
| **Blend** | Split crusher / distortion control | Left of center lowers the crusher sample rate for more bitcrushing. Right of center increases distortion gain. Around center, both effects are at their mildest settings. |

## Textured Reverb

In this mode the micro-looper is disabled. The signal goes through the reverb first, then the pitch shifter, followed by the downstream delay, distortion, crusher, and mixer stages.

| Knob | Function | Notes |
| --- | --- | --- |
| **Size** | Reverb time | Controls the reverb decay length. The micro-looper sensitivity and fading mappings tied to this knob are inactive in this mode. |
| **Fade** | Unused in the current firmware | This knob still points at micro-looper attack and slice parameters, but those have no audible effect while the micro-looper is disabled. |
| **Pitch** | Pitch-shift amount and direction | Center is unison. Turning left shifts down, and turning right shifts up, with a continuous range up to one octave in either direction. |
| **Modulation** | Pitch-shifter mix | Blends the unshifted reverb signal with the pitch-shifted reverb signal. Lower settings favor the unshifted reverb; higher settings favor the shifted signal. |
| **Grit** | Tape-style delay modulation depth | Fully counterclockwise disables the delay block. Any position above minimum turns the modulated delay on and increases the modulation depth. |
| **Blend** | Split crusher / distortion control | Left of center lowers the crusher sample rate for more bitcrushing. Right of center increases distortion gain. Around center, both effects are at their mildest settings. |

### Bypass Footswitch

In the current firmware, the **bypass** footswitch does **not** bypass the reverb path. Instead, it still drives the hidden micro-looper state in the background while you remain in **REVERB** mode.

| Gesture | Behavior |
| --- | --- |
| **Tap** | Arms hidden overdub recording if the looper is idle, or requests a stop if the hidden looper is already recording. |
| **Double tap** | Stops the hidden looper playback and finalizes the hidden recording if one is active. The second tap does not also trigger the normal single-press action. |
| **Hold** | Clears the hidden overdub looper state for a fresh restart. |

This means the footswitch can change looper state while the audible signal remains in **REVERB** mode.

### Alternate Footswitch

| Gesture | Behavior |
| --- | --- |
| **Tap** | Toggles the audible reverb freeze state. At the same time, it also sends an alternate-footswitch press to the hidden looper, which attempts to start or enable stretched playback in the background. |
| **Release** | No dedicated release action is routed for the alternate footswitch. |
| **Double tap** | Toggles the audible reverb freeze state once and stops hidden stretched looper playback. The second tap does **not** also trigger the normal single-press action on tap two. |
| **Hold** | Has no direct reverb action. Instead, it re-runs or starts hidden stretched playback in the background looper when enough loop material exists. |

## Toggle Switch Functions

### Toggle Switch 2

This switch controls the pitched harmony voice inside the looper.

| Position | Behavior |
| --- | --- |
| **Left** | The harmony voice plays in reverse. |
| **Center** | The harmony voice plays forward. |
| **Right** | Enables randomized speed variation on the harmony voice. |

The main loop itself continues to run forward at normal speed. This switch is most audible when the harmony voice is mixed in.

### Toggle Switch 3

This switch controls how the live input is routed relative to the loop and effect chain.

| Position | Behavior |
| --- | --- |
| **Left** | The live input is routed through the looper and downstream effects. The dry passthrough signal is muted at the mixer output. |
| **Center** | The live input stays dry and is mixed back in after the loop/effect processing. |
| **Right** | Currently behaves the same as **Center** in the firmware. |

> Note: only one side of this toggle has unique behavior in the current code. The opposite outer position is not assigned a separate function yet.
