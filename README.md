# Dronage Move Manual

Ambient drone workstation for **Ableton Move**, running as a standalone takeover
tool via [Schwung](https://github.com/charlesvestal/schwung).

Dronage Move is part of the **Dronage** series. The idea began with
[Dronage Terminal](https://boorch.itch.io/dronage-terminal), the original desktop
drone synth and the first iteration of the series; Dronage Move brings that sound
to Ableton Move hardware.

Four voices built on a famous open-source macro synth module, each with its own
filter, drive, envelope and per-step sequencer, fed through a shared delay /
reverb / dirt section. Eight LFOs and eight macros modulate anything. Eight
scenes per project, full undo, and direct-to-disk recording.

---

## Contents

1. [Getting started](#1-getting-started)
2. [The big picture](#2-the-big-picture)
3. [The control surface](#3-the-control-surface)
4. [Global view](#4-global-view-the-home-screen)
5. [Track view](#5-track-view-editing-a-voice)
6. [The pad keyboard](#6-the-pad-keyboard)
7. [The step sequencer and p-locks](#7-the-step-sequencer-and-p-locks)
8. [LFOs](#8-lfos)
9. [Macros](#9-macros)
10. [Scenes](#10-scenes)
11. [Undo and redo](#11-undo-and-redo)
12. [Transport and recording](#12-transport-and-recording)
13. [Projects: save, load, new](#13-projects-save-load-new)
14. [Recipe: ambient melodies](#14-recipe-ambient-melodies)
15. [Cheat sheet](#15-cheat-sheet)

---

## 1. Getting started

**Launch:** on the Move, **Shift + Vol + Step 13**, then **Tools**, then
**Dronage Move**.

**Quit:** hold **Back + MODE (≡) + jog-click**, or use the MODE menu and choose
**QUIT**.

**Make your first sound in 30 seconds:**

1. You boot into **Global** view and **all four voices start muted on purpose**
   (you really don't want four identical drones blaring at you the second it
   loads, nobody does).
2. Hold **Shift** and tap **Track 1** to switch that voice on. You should hear a
   drone.
3. Tap **Track 1** (no Shift) to open its editor and turn the knobs.
4. Turn the **Vol** encoder to set overall level.

That's the whole loop: switch a voice on, open it, shape it.

---

## 2. The big picture

Dronage Move has four top-level **views**. You're always in one of them:

| View       | How to reach it          | What it's for                                   |
|------------|--------------------------|-------------------------------------------------|
| **Global** | home (boot) / **Back**   | tempo, scale, and the shared delay/reverb/dirt  |
| **Track**  | tap a **Track** button   | edit one voice plus its step sequencer          |
| **LFO**    | **M** (toggle)           | shape the 8 LFOs and route them                 |
| **Macro**  | **SAMP** (toggle)        | 8 hands-on performance controls                 |

**Back** always returns you to Global (think "cd .."). **M** and **SAMP** toggle
their views on and off, returning you to where you were.

Four **voices** (tracks) make sound. Modulation (LFOs, macros, and per-step
p-locks) reshapes their parameters over time.

**Gate mode** is the first thing to understand about a voice. Every voice is in
one of two modes, and it changes everything about how that voice behaves:

- **DRN (drone):** the voice plays **continuously**, a held wall of sound. This
  is the default, and it's the heart of what Dronage does.
- **SEQ (sequenced):** the voice only sounds when its step sequencer triggers it,
  so you get rhythmic hits and patterns instead of a constant tone.

You set this per voice with the `GATE` control on the Track view's STRUCT page
(see [Track view](#5-track-view-editing-a-voice)). If a voice seems silent even
though it's switched on, check whether it's in SEQ mode with no active steps.

Everything you edit lives in the **current scene**, and a project holds 8 scenes
(see [Scenes](#10-scenes)).

---

## 3. The control surface

**The 8 knobs (encoders)** edit whatever the current view shows.
- **Touch** a knob (don't turn) to reveal its current value on screen.
- **Turn** to change it. Hold **Shift** for coarse steps.
- Hold **DEL** and turn to **reset that knob to its default**.

**The Vol encoder** is the master volume. It's a global performance control and
is never saved into a scene. Hold **DEL** + Vol to reset to 100%.

**The jog wheel** changes the page or selection within a view (Global section,
Track page, LFO selection). While holding a step, LFO or macro it scrolls that
item's list. **Jog-click** clears the highlighted item in a list.

**The 16 Step buttons** are the sequencer row in Track view, and double as the
selectors for LFOs (1-8), macros (1-8) and scenes (1-8) depending on what you're
holding.

**The pad grid** is a scale keyboard (see [The pad keyboard](#6-the-pad-keyboard)).

**Modifier buttons** (hold while pressing something else):

| Button   | Role                                                            |
|----------|-----------------------------------------------------------------|
| **Shift**| coarse edits; **Shift+Track** mutes or un-mutes a voice         |
| **DEL**  | reset / clear / remove                                          |
| **COPY** | copy (a step, an LFO's routing, a scene, a project)             |
| **LOOP** | set a track's loop length                                       |
| **CAPT** | scenes modifier (hold, then the steps become the 8 scene slots) |

---

## 4. Global view (the home screen)

The home view. The jog wheel moves between four pages; the 8 knobs edit the
page's parameters.

- **BASICS:** `BPM`, `ROOT` (key), `SCALE`, `SEED` (for the random/S&H sources).
- **DELAY:** `FBK` (feedback), `TONE`, `RVB` (delay to reverb send), `MOD` (tape
  wobble), `GRAN` (granular texture).
- **REVERB:** `SIZE`, `TIME`, `MOD` (diffusion), `TONE`, `SHIM` (shimmer).
- **DIRT:** `FLOR` (noise floor), `COLR`, `BAL`, `HP`, `FAT` (compression).

**Defaults:** 120 BPM, key of **C**, **Major** scale. `ROOT` and `SCALE` set the
musical grid for pitch knobs and the pad keyboard. With `SCALE` set to **OFF** the
keyboard and pitch knobs are chromatic.

The step row is dark in Global. The sequencer belongs to a voice, and Global
isn't a voice.

---

## 5. Track view (editing a voice)

Tap a **Track** button (1 to 4) to focus that voice and open its editor. Re-tap
the same Track button to cycle its three pages (the jog wheel also switches
pages):

**SHAPE** (page 1), the sound source and filter:

| `ENG` | `PIT` | `HARM` | `TIMB` | `MORF` | `CUT` | `RES` | `HPF` |
|-------|-------|--------|--------|--------|-------|-------|-------|

`ENG` picks the synthesis engine/model; `PIT` is pitch (shown as a note name);
`HARM`/`TIMB`/`MORF` are the timbre controls; `CUT`/`RES` the filter.

`HPF` is more of a utility high-pass, there to tame low-end rumble and keep a
voice from muddying the mix. Pushed further, though, it can shift the proverbial
role of a track entirely, thinning it out by stripping the low-frequency domain
so it sits as a lighter, airier layer above everything else.

**COLOR** (page 2), drive, sends and output:

| `DRIV` | `CHOR` | `DLY` | `RVB` | `LPGD` | `OUT` | `PAN` | `LVL` |
|--------|--------|-------|-------|--------|-------|-------|-------|

`DRIV` is bipolar (doom one way, marshall the other); `DLY`/`RVB` are the send
levels; `PAN`/`LVL` are placement and level.

`OUT` sets how the voice's two raw outputs (a main signal and an aux signal) map
to the stereo field:

- **MIX:** blend both equally to mono (default).
- **OUT:** main output only, mono.
- **AUX:** aux output only, mono.
- **STE:** stereo, main to the left channel, aux to the right.
- **INV:** inverted stereo, main to the right and aux to the left (STE with the
  two channels swapped).

**STRUCT** (page 3), set-and-forget per-track behaviour:

| `GATE` | `LEN` | `RSNC` | `CLK` | `QNT` | (none) | `ATK` | `DEC` |
|--------|-------|--------|-------|-------|--------|-------|-------|

- `GATE` switches **DRN** (continuous drone) and **SEQ** (the step sequencer
  triggers the voice).
- `LEN` is the loop length (2 to 16 steps); `RSNC` the resync length; `CLK` the
  per-track clock divider; `QNT` quantize-to-scale on/off.
- `ATK`/`DEC` **are not a per-note amplitude envelope.** Despite the names, they
  are simply the **fade-in and fade-out times for the whole voice** when you gate
  it on or off with Shift+Track: a slew on the voice level. They default to a slow
  4 seconds each (range about 0.1 to 30 seconds), so a voice swells in and
  releases gently instead of snapping on. Bringing layers in and out by hand,
  slowly, is the core gesture of ambient and drone music, and that is exactly what
  these are for. The fade always follows your Shift+Track gate in
  **both DRN and SEQ modes**: in SEQ the step triggers separately drive the
  voice's internal decay, while `ATK`/`DEC` still shape the overall swell on top.

**Pitch and scale:** when `QNT` is on, turning the `PIT` knob steps through the
notes of the current scale; Shift jumps by octaves.

**Mute and un-mute:** **Shift + Track** toggles a voice on or off, from any view.
This isn't a hard switch. The voice fades in over its `ATK` time and fades out
over its `DEC` time (set on the STRUCT page), like a slew with settable attack
and decay, so voices swell and release rather than snapping on and off.

---

## 6. The pad keyboard

The pad grid plays notes, quantized to the current key/scale (set in Global,
BASICS).

- **In Track view:** the whole grid is a keyboard for the **focused voice**.
  Bottom-left is **C2**; notes rise left to right and bottom to top, landing only
  on scale notes. Playing a pad sets that voice's base pitch and auditions it
  while held.
- **In any other view:** each of the four rows is a keyboard for one track (top
  row is Track 1).
- **Octave:** **Up / Down** shift the octave. That's just the focused track in
  Track view, or all four tracks elsewhere.
- Pads outside the playable range stay dark, and pressing them does nothing.

Each track has its own colour so you can tell the rows apart:
**T1 blue, T2 purple, T3 magenta, T4 red.** Scale roots glow at full colour,
other in-scale notes are dimmer, and the note currently sounding is brightest.

---

## 7. The step sequencer and p-locks

In Track view the 16 Step buttons are the focused voice's pattern. (Set `GATE` to
**SEQ** on the STRUCT page so the steps actually trigger the voice.)

**Editing steps:**

| Action                      | Result                                              |
|-----------------------------|-----------------------------------------------------|
| **Shift + tap**             | fill a step / cycle one-shot and latched            |
| **DEL + tap**               | remove the step (and its p-locks)                   |
| **COPY + tap**              | copy the step to the clipboard                      |
| **Shift + COPY + tap**      | paste the clipboard into the step                   |
| **LOOP + tap**              | set the track's loop length to that step            |
| **Left / Right** (no hold)  | rotate the whole pattern                            |

**P-locks (parameter locks):** **press and hold** a step, then **turn any knob**
on the SHAPE or COLOR page. That step now remembers its own value for that
parameter. While holding a step:

- **jog / Up / Down** scroll its list of locks,
- **Left / Right** nudge the highlighted lock,
- **jog-click / DEL** clear the highlighted lock.

While stopped, holding a step also auditions it so you can hear what you're
editing.

---

## 8. LFOs

Press **M** for the LFO view. The 8 Step buttons (1 to 8) are the 8 LFOs; the jog
wheel selects which LFO the 8 knobs are **shaping**:

| `WAVE` | `RATE` | `PHASE` | `SKEW` | `DC` | `SMOO` | `LEN` | `VAR` |
|--------|--------|---------|--------|------|--------|-------|-------|

`WAVE` picks the shape: Sine, Tri, Saw up/down, Square, plus two
sample-and-hold shapes (S&H-R random and S&H-S seeded). `RATE` is the
tempo-synced cycle length, from very slow (/512) to very fast (x512). `PHASE`
shifts the cycle start, `SKEW` warps it, `DC` adds an offset, and `SMOO` rounds
the shape, softening S&H steps into glides between values.

`LEN` and `VAR` apply to the sample-and-hold shapes. `LEN` is the number of
steps per cycle (2 to 32). `VAR` is the S&H-R randomness:
**at 0 the random pattern is frozen and simply loops** every cycle; turn it up
and each step is re-rolled as it comes around, so the pattern keeps evolving
(more `VAR` = bigger jumps).

**Routing an LFO to a parameter:** **press and hold** an LFO's step (1 to 8),
then **turn a knob**. That routes the LFO into the focused voice's parameter at
that knob, with a bipolar depth. While assigning:

- tap a different **Track** button to aim the LFO at another voice; re-tap the
  focused track to flip between its SHAPE and COLOR layers,
- **jog / Up / Down** scroll the assignment list, **Left / Right** nudge a depth,
  **jog-click / DEL** remove the highlighted assignment.

**COPY + LFO step** copies that LFO's whole set of routings;
**Shift + COPY + LFO step** pastes it onto another LFO.

---

## 9. Macros

Press **SAMP** for the Macro view. A macro is simply an LFO that holds still: it
outputs a constant value (the knob position) instead of a moving one, so it's
your hands-on performance control.

- **Idle:** the 8 knobs are the 8 macro values, bipolar (**centre is off**; turn
  up or down to push a target either way). **DEL + turn** resets a macro to 0.
- **Assigning:** **press and hold** a macro selector (Step 1 to 8), then
  **turn a knob** to route that macro into the focused voice's parameter. This
  works exactly like the LFO assign above (cross-voice, with copy/paste via COPY
  and Shift+COPY).

Macros target the same per-voice parameters as the LFOs (pitch, cutoff, level,
sends, and so on). Set up a few routings, then sweep the macro knobs live.

---

## 10. Scenes

A project holds **8 scenes**. Each scene is a full snapshot of everything you
edit: all four voices, the sequencer, LFOs, macros and the global section.

Hold **CAPT** (or double-tap it to latch it on; press again to exit). The Step
buttons 1 to 8 become the scene slots:

| Action                   | Result                              |
|--------------------------|-------------------------------------|
| **tap a slot**           | switch to that scene                |
| **COPY + slot**          | copy that scene to the clipboard    |
| **Shift + COPY + slot**  | paste the clipboard into that scene |
| **DEL + slot**           | reset that scene to defaults        |

Each scene remembers its own edits, so switching saves your current work back
into the slot you're leaving. Slot colours: **green** is the active scene,
**amber** is edited, **dim** is untouched.

---

## 11. Undo and redo

- **Undo** button steps backwards.
- **Shift + Undo** redoes.

Undo covers the whole 8-scene bank, so it survives scene switches. A quick knob
sweep collapses into a single undo step.

---

## 12. Transport and recording

- **Play** starts and stops. Stopping freezes the clock (LFOs and sequencers hold
  their position); starting resets everything to step 1.
- **Rec** toggles WAV recording of the main output. Recordings are saved to
  `…/DronageMove/recordings/` and normalised automatically. A take shorter than
  5 seconds is discarded.

---

## 13. Projects: save, load, new

Press **MODE** (the ≡ button) to open the menu. Use the jog wheel to move and
jog-click to choose:

- **SAVE:** name the project with the letter picker (jog to pick a letter,
  jog-click to add it, Left/Right move the cursor, DEL backspaces). If a project
  is already loaded its name is pre-filled.
- **LOAD:** pick from the list. **DEL** on a file deletes it (with a confirm);
  **COPY** duplicates it.
- **NEW:** reset everything to defaults (you'll be warned if there are unsaved
  changes).
- **QUIT:** exit back to Move firmware.

Projects are stored on the Move at
`/data/UserData/UserLibrary/DronageMove/projects/` as `.dronagemove` files.

---

## 14. Recipe: ambient melodies

A worked example that ties the views together. The trick is to let sample-and-hold
LFOs and a slow sequencer choose notes for you while the
**scale quantizer keeps everything in key**, so the result is always musical even
though it's generative.

**1. Set the key.** In Global, BASICS, pick a `ROOT` and a `SCALE`. Forgiving
scales like a minor or a pentatonic make every note land well. Leave `QNT` on
(STRUCT page, on by default) for each voice you want locked to the key. This is
the whole reason the random pitches below sound intentional: the quantizer snaps
all pitch modulation to scale notes.

**2. Design a few voices.** Give each track a role on its SHAPE/COLOR pages: a
lead, a bass, a pad or chord voice. Keep them as drones (`GATE` = DRN) and use
slow `ATK`/`DEC` so they breathe in and out.

**3. Lead melody from a long S&H LFO.** Press **M**, select an LFO, set `WAVE` to
a sample-and-hold shape and `LEN` to **16** (a 16-note phrase). Choose a `RATE`
(clock division) for how fast it walks. Hold that LFO's step, focus the lead
track, and turn `PIT` to route the LFO into its pitch with a moderate depth. Each
step picks a fresh in-scale note, so you get an evolving 16-note melody.

**4. Bass and chords from shorter S&H LFOs.** On another LFO set `LEN` to **4**
and route it to the bass track's `PIT` with a smaller depth, so it cycles a short
4-note ostinato down low. Do the same with a third LFO on a pad or chord voice.
Because each S&H has a different `LEN` and `RATE`, the lines drift against each
other and never repeat the same combination.

**5. Slow transposition from a short sequencer.** Take one track, set its `LEN` to
**3** (LOOP + tap Step 3, or the STRUCT `LEN` knob) and slow its `CLK` divider so
the pattern crawls. Hold each of the three steps and dial a `PIT` p-lock, a small
transposition per step. As those three steps cycle slowly they shift the whole
line through the scale for complex, ever-changing movement, all still in key. In
DRN mode this re-pitches the drone without re-attacking it; in SEQ mode each step
also re-triggers the voice.

**6. Perform and capture.** Reroll the random sequences with `SEED` (Global,
BASICS). Use macros (**SAMP**) to ride a few depths or levels live. When a
combination sings, snapshot it to a scene (hold **CAPT**, tap a slot) and build a
set of variations to move between.

Start with modest depths and slow rates. The magic is in the interplay of a few
quantized, out-of-phase lines, not in any single busy one.

---

## 15. Cheat sheet

**Views**

| Press           | Goes to        |
|-----------------|----------------|
| Track 1 to 4    | that voice     |
| **M**           | LFO view       |
| **SAMP**        | Macro view     |
| **MODE (≡)**    | menu           |
| **Back**        | Global (home)  |

**Modifiers (hold plus action)**

| Combo                     | Does                                       |
|---------------------------|--------------------------------------------|
| Shift + Track             | mute / un-mute a voice                     |
| Shift + knob              | coarse edit                                |
| DEL + knob                | reset knob to default                      |
| Hold Step + knob          | p-lock that parameter on the step          |
| Shift + tap Step          | fill / cycle a step                        |
| DEL + tap Step            | remove a step                              |
| COPY + Step / scene / LFO | copy it                                    |
| Shift + COPY + …          | paste it                                   |
| LOOP + tap Step           | set loop length                            |
| Hold LFO/Macro + knob     | route it into the focused voice's param    |
| CAPT (hold) + Step 1 to 8 | scene switch / copy / paste / reset        |
| Up / Down                 | octave (pads) / scroll (held list)         |
| Left / Right              | rotate pattern / nudge a held value        |
| Undo / Shift + Undo       | undo / redo                                |
| Play / Rec                | transport / record                         |
| **Back + MODE + jog-click** | **quit to Move firmware**                |

---

## Install

Via the Schwung **Module Store** on your Move (recommended): browse to
**Dronage Move** and install.

Manual install: download `dronage-tool-module.tar.gz` from the latest Release,
extract into `/data/UserData/schwung/modules/tools/`, then launch from the Move:
**Shift + Vol + Step 13**, then **Tools**, then **Dronage Move**.

## Licensing

Dronage Move is proprietary; you may use the distributed binary freely. The
bundled open-source components and their licenses are listed in
`THIRD-PARTY-LICENSES.txt` inside the module package.
