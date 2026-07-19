# AI Video-to-Shorts Repurposing Engine

A short cut from a long video fails for one reason above all others: it was *trimmed* when it needed to be *re-authored*. The clip keeps the long-form's slow warm-up, its 16:9 framing, and its assumption that you saw the previous forty minutes — and then dies in the first second on a feed where nobody has that context. Repurposing is not trimming. It is rebuilding a self-contained vertical video from source material, on a repeatable spec, so a thirty-clip batch comes out consistent instead of thirty one-off edits. This skill is that spec and that pipeline.

## When you activate

Trigger when the user has an existing long video and wants vertical shorts out of it: podcasts, webinars, YouTube uploads, course lessons, livestream recordings, sales-call or interview recordings, or long AI-generated footage. Also when they name the mechanical problems — "reframe 16:9 to 9:16," "the captions cover the subject," "the clip starts too slow," "I need ten clips from this and they all look different."

Do **not** activate for writing or generating original footage (that's production, not repurposing), for choosing *which* content strategy or hooks to pursue as a channel (that's clip *strategy* — this skill executes on a chosen video, it doesn't set the content plan), or for editing that isn't format conversion. This is the conversion engine: long horizontal source → finished vertical shorts with a per-clip spec.

## The rule that governs everything

**Every short must stand completely alone for a viewer who will never see the source.** No "as I mentioned earlier," no payoff that depends on setup that got left behind, no first frame that only makes sense in context. If a clip needs the long video to make sense, it isn't finished being repurposed — it's a fragment. The whole pipeline exists to enforce self-containment: pick a moment that is already whole, re-author its open so the payoff comes first, and frame and caption it for the exact surface it will play on.

## The pipeline — run all 6 stages per clip

### Stage 1 — Mine the transcript for whole moments, not timestamps

Work from the transcript, not the scrubber. Scan for segments that are *already self-contained*: a complete thought, a story with a punchline, a question-and-payoff, a strong claim with its one-line proof, a number that lands. A moment qualifies only if it survives the standalone test — could a stranger drop into it cold and get the whole thing in under a minute?

Reject: anything that opens with "so, going back to," anything whose payoff is in a different part of the video, and anything that's only interesting because of what came before it. Mark each kept moment with `[start–end]` from the transcript, a one-line "why this stands alone," and the single sentence that is its payoff. Aim to over-select (say, 12 candidates) then cut to the strongest, rather than forcing a target count out of weak material — a video does not owe you thirty good clips.

### Stage 2 — Re-author the open (this is where trimmed clips die)

The source moment almost never opens where the short should. Long-form builds; shorts must *pay off first, then build*. For each clip:

- **Find the payoff line, and open on or just before it.** The strongest sentence in the moment is usually 15–40 seconds in. Move it to the front — either by cutting straight to it, or by opening on it as a spoken cold-open and then cutting back to the build.
- **Kill the ramp.** Delete "so," "yeah," "I think," throat-clearing, and the host's setup question if the answer implies it. First audible word should carry meaning by ~0.5s.
- **Write the on-screen hook line** (the burned text in the first frame) as a separate act of writing — it is not the transcript. It states the stakes or the payoff in ≤7 words: "This pricing mistake cost them $40k," not "Let's talk about pricing."
- **Confirm the standalone open:** read the first three seconds with no prior context. If it's confusing, the open is wrong, not the viewer.

### Stage 3 — Reframe 16:9 → 9:16 around the subject

The source is horizontal; the destination is `1080×1920`, 9:16. Never just letterbox a 16:9 frame into a vertical box with black bars — it wastes 60% of the screen and reads as lazy. Reframe:

- **Single speaker:** crop to a vertical window tracking the speaker's face in the upper-middle third, eyes around the upper-third line, not dead center. If they move, the crop tracks or cuts — it does not drift.
- **Two speakers (podcast/interview):** either an active-speaker crop that cuts to whoever's talking, or a stacked split (two vertical-stacked 16:9 crops) when both react. Pick one per clip and hold it; don't mix within a clip.
- **Screen-share / slides:** the content goes in the upper 60%, speaker in a lower corner inset — but keep the inset out of the caption zone (below).
- **B-roll / AI-generated wide footage:** use a punched-in center crop or a slow reframing pan; if the composition can't survive a vertical crop, don't force it — that clip stays horizontal or gets cut.

### Stage 4 — Respect the platform UI safe zones (2026)

All three platforms are `1080×1920`, 9:16, MP4/MOV, H.264/AAC — one master export plays everywhere. But their interface chrome overlaps the frame differently, and this is what causes "the caption is behind the like button." Keep all critical content — faces, captions, key text — inside the safe box:

| Zone | TikTok | Instagram Reels | YouTube Shorts |
|---|---|---|---|
| Top overlay (avoid) | ~200 px | ~250 px | ~200 px |
| Bottom overlay (avoid) | ~350–400 px | ~400 px (caption/CTA) | ~400 px |
| Right rail (buttons) | ~130 px | ~150 px | ~130 px |

Practical rule: **keep captions and essential text within the center vertical band, roughly 250 px from the top and 420 px from the bottom, and 160 px in from the right edge.** Design to the tightest of the three (Reels) so the one master is safe on all. Never place the payoff word in the bottom 400 px or under the right rail.

### Stage 5 — Caption direction (assume sound is off)

Most impressions are muted, so captions are not an accessory — they are the video. Spec them:

- **Burn them in** (open captions), don't rely on platform auto-caption placement, which drifts into the unsafe zones.
- **Karaoke/word-highlight style**, 1–3 words visible at a time for pace; max 2 short lines. Big, high-contrast, with a subtle plate or stroke so they survive a bright background.
- **Position in the center band**, never the bottom UI zone. Vertically center-low but above the 420 px floor.
- **Punch-emphasize the payoff word** — scale or color it on the beat it's spoken. That one moment of emphasis is what makes a muted viewer stop.
- **Never cover a face or on-screen number with a caption.** Reposition the crop, not the caption.

### Stage 6 — Export spec and QA

Deliver one master plus the QA checklist:

- **Master:** `1080×1920`, 9:16, H.264 high profile, AAC, 30 or 60 fps matching source, ~8–12 Mbps, MP4. Loudness around −14 LUFS integrated, true-peak ≤ −1 dBTP so it isn't quiet in-feed.
- **Length:** trim to the moment's natural end — usually 15–45s. Don't pad to hit a number; a tight 22s clip beats a baggy 50s one. (Reels/Shorts cap at 3 min, TikTok far longer, but length is not the constraint — retention is.)
- **Loop check:** does the last frame hand cleanly back to the first for a replay? A clean loop buys watch-time.
- **The muted cold-open test, per clip:** play the first 3 seconds silent. If a stranger doesn't know what they're watching and why to stay, the clip fails and goes back to Stage 2.

## Deliverable

For a source video, produce a **clip manifest**: a numbered table of selected moments — `[source in–out]`, the payoff line, the re-authored open (where it now starts + the ≤7-word on-screen hook), the reframe approach, the caption style note, and the final length — followed by the shared export spec (Stage 6) and a per-clip QA checkbox. Where the user wants it, add the platform-native title/caption text and 3–5 hashtags per clip built from the content (never generic #fyp filler). The output is a spec an editor or an automated tool can execute clip-by-clip without re-watching the whole source.

## Negative / failure bank

Letterboxing 16:9 into 9:16 with black bars. Opening the clip where the moment opens in the source instead of on the payoff. A first frame that only makes sense if you saw the long video. Captions in the bottom 400 px, behind the platform CTA. Captions over the speaker's face. A center-cropped two-shot that keeps cutting off whoever's talking. Padding a 20-second moment to 50 seconds to "look substantial." Forcing a fixed clip count out of a video that only had four good moments. Generic #fyp #viral hashtags. Relying on the platform's auto-captions for placement. One master with the payoff word under the like button. Leaving "so, um, going back to what I said" in the open. Speeding the whole clip to fit a length instead of cutting to the moment.

## Guardrails

Only repurpose footage the user owns or has the right to use — do not design a pipeline that lifts clips from someone else's video, and say so if that's what's being asked. Do not fabricate or re-order spoken words to change their meaning: trimming filler and moving to the payoff is fine; splicing sentences so someone appears to say something they didn't is a misrepresentation, and it's especially dangerous with interview, podcast, or any real-person footage — flag it rather than do it. If the source moment is being cut in a way that reverses the speaker's actual point (a common "gotcha clip" failure), call it out. Do not invent captions for words that weren't said; caption what's actually in the audio. Where AI-generated source footage is involved, keep any required "AI-generated" disclosure intact in the repurposed cut rather than cropping it out.

## Worked example (baked in)

**Task:** "I have a 52-minute podcast episode. I want 8 vertical clips for TikTok and Reels. The last batch I made just had black bars top and bottom and the captions were half behind the TikTok buttons. Where do I start?"

**1. Transcript first, not the timeline.** Read the transcript and mark every self-contained moment — a story with a punchline, a hot take with a reason, a specific number. On a 52-minute episode you're realistically looking for 8–14 candidates; mark 12, then keep the 8 strongest by the standalone test. For each, note `[in–out]` and the single payoff sentence. If you can only find 5 that stand alone, deliver 5 — four strong clips beat eight limp ones, and the weak ones drag the channel's average watch-time down for weeks.

**2. Re-author each open — this is why the last batch underperformed even before the framing.** Take clip 3, where the guest says (at 0:31 into the moment) "…and that's when we realized we'd been pricing it 60% too low the whole time." That sentence is the clip. Open on it — cold, as the first spoken words — then cut back to the ten seconds of setup. On-screen hook line, written fresh, ≤7 words: "They priced it 60% too low." Not "Let's talk about our pricing journey."

**3. Reframe to 9:16, no bars.** Two speakers, so per clip pick either an active-speaker crop (cut to whoever's talking, face in the upper third) or a vertical stack of both. Hold one approach per clip. The black bars from last time meant a 16:9 frame was dropped into a 9:16 box — instead, crop *into* the footage so the frame is full-bleed vertical. If a moment has both people cross-talking and reacting, that's the one to stack.

**4. Fix the caption-behind-buttons problem at the source.** Last batch failed because captions sat in the bottom 400 px, exactly where TikTok's caption/CTA and Reels' overlay live. Move burned captions into the center band — above the 420 px floor, 160 px clear of the right rail. Design to Reels' tighter box so the single master is safe on TikTok too. Word-highlight style, 1–3 words, payoff word punched on its beat.

**5. Export one master per clip.** `1080×1920`, H.264/AAC, ~10 Mbps, −14 LUFS, MP4 — plays on both platforms from one file. Lengths follow the moments: expect most in the 18–40s range. QA each with the muted 3-second test before you call it done.

**Deliverable:** an 8-row clip manifest — in/out, payoff line, new open + hook text, reframe method, caption note, length — plus the shared export spec and a per-clip muted-open checkbox. The two failures from last time (bars, buried captions) are now structural rules in Stages 3–4, not things to remember to fix by hand on clip nine.

Allowed tools (optional)
Read, Edit, Bash

Examples

Example 1
User message (activates the skill)
I recorded a 40-minute webinar. I want to cut vertical clips for Reels and TikTok, but the ones I made last time just had black bars top and bottom and honestly nobody watched past the first couple seconds. What am I doing wrong?
Agent response (what your skill produces)
Two different failures stacked on top of each other, and they're both fixable structurally — one is why nobody stayed, the other is why the clips looked cheap.

The retention drop is an open problem, not a content problem. A webinar clip almost always opens the way the webinar opened that moment — with a build-up, a "so what we found was…," a slow ramp toward the point. That works in a 40-minute session where the viewer already opted in. On a feed it's death, because the payoff is fifteen seconds in and nobody gives you fifteen seconds cold. The fix is to re-author the open: find the single strongest sentence in each moment — the actual payoff — and move it to the front, either by cutting straight to it or opening on it as a cold line and then cutting back to the setup. Then write a separate on-screen hook line, seven words max, that states the stakes in the first frame: "This one change doubled our signups," not "Let's talk about our onboarding." First audible word should mean something by half a second in. That single change usually does more for retention than anything else you could do.

The black bars are a reframing shortcut you can just stop taking. Bars mean a 16:9 frame got dropped into a 9:16 box, wasting more than half the screen and signaling "reposted horizontal video," which the platforms and viewers both discount. Instead, crop into the footage to fill the vertical frame: for a single presenter, a vertical window that tracks their face in the upper third; for slides, the slide in the upper 60% with the speaker in a lower corner inset. Full-bleed vertical, no bars.

And while you're in there, fix where the captions sit — on a webinar clip they usually default to the bottom, which on Reels and TikTok is exactly where the caption bar and CTA buttons cover them. Move burned captions into the center band, above roughly the bottom 420 pixels and clear of the right-side buttons, word-highlight style, payoff word emphasized on its beat.

If you tell me the topic and paste the transcript (or even rough notes on the best moments), I'll give you a clip-by-clip manifest: where each one now opens, its hook line, how to reframe it, and the caption and export settings — one master per clip that plays on both platforms.

Example 2
User message (activates the skill)
My VA cuts our podcast into shorts and every batch looks different — some are zoomed weird, captions in random spots, some clips just kind of end. How do I make them consistent without editing each one myself?
Agent response (what your skill produces)
Inconsistency across a batch is the signal that there's no spec — your VA is making a dozen creative decisions per clip from scratch, so of course clip three and clip nine don't match. The fix isn't editing them yourself, it's giving the VA a fixed spec so the decisions are already made and the only work left is execution. Here's the spec to hand them.

Framing, decided once. Your podcast is two people, so pick one of exactly two reframing modes per clip and forbid mixing within a clip: active-speaker crop (cut to whoever's talking, face in the upper third) or a vertical stack of both when they're cross-talking. "Zoomed weird" happens when someone center-crops a two-shot and it keeps cutting off the person talking — the two named modes remove that guess.

Captions, decided once. Fixed position for every clip: center band, above the bottom 420 pixels, 160 pixels clear of the right edge so they never collide with the platform buttons. One caption style — word-highlight, one to three words, big, high-contrast with a stroke — applied to every clip. "Random spots" is just the absence of a rule; give the rule.

The "clips that just end" problem is a selection rule, not an editing one. A clip that trails off was never a self-contained moment — it was a timestamp your VA cut on. The rule: only select a moment that passes the standalone test (a stranger could drop in cold and get the whole thing in under a minute) and that has a clear payoff line. Cut out on the beat after the payoff lands, not whenever the transcript happened to pause. Moments that don't have a clean end don't get selected.

Lock the export so every file is identical: 1080×1920, H.264/AAC, around 10 Mbps, −14 LUFS, MP4 — one master per clip, same settings every time.

Put those four things — two framing modes, one caption spec, the standalone-moment selection rule, one export preset — into a one-page checklist and your VA produces a consistent batch without you touching an edit. If you paste a transcript I'll build you the actual clip manifest for one episode as the template they copy from next time.
