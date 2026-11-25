# Leaderboard analysis — Last Text at One Percent

Bounty: `u-azazex-last-text-at-one-percent-ba9fc876` · prize $2.50 (top 10 paid, 1st $0.78) · deadline 2026-11-26 17:20 WIB · sponsor Hanif (u-azazex, unverified) · 242 submissions at build time (2026-11-25 ~00:50 WIB).

## BLIND bounty — no top 10 exists

`GET /api/competitions/<slug>/leaderboard?rows=all` returns **0 entries**, `scores_visible: false`, `placements_held: true`. Raw response saved as `leaderboard.json`. Per rank-recovery §10j, this file instead holds: (a) RULES.txt judge criteria + heat/playoff/cut numbers; (b) public submission titles on the bounty page; (c) winner artifacts of similar finalized one-liner bounties.

## (a) RULES.txt — judge criteria + heats (read in full, 2026-11-25)

Judge: z-ai/glm-5.3-flash, head-to-head, no ties, margin 1–5 per call (winner gets 0.5 + margin/10 per call; a game is 2 calls, one in each order). Criteria, lexicographic — first difference decides unless a later one differs by much more:

1. Reads as a final text message a dying phone sends at 1% battery, in the phone's own voice, and is funny. A message any healthy phone could send, or one that is not a text at all, loses to any final text from a dying phone.
2. The joke lands: a real turn, a surprise, or a specific detail that makes a reader laugh out loud rather than smile politely.
3. The voice is the phone's own: a personality with a stake in dying, consistent from first word to last.
4. Reads like a text someone would actually send: short, punchy, no wasted words, nothing that needs a second read.
5. Fresh: dodges the obvious low-battery puns and the lines a hundred other entrants will also write.

Gate: `/output/entry.txt` must be UTF-8, 1–200 characters, not only whitespace.

Heats (the 3 numbers):
- **Final heat size: 500** — top 500 on the dev board go on; while ≤500 entrants are rated, every valid entry goes on. Field is ~242+ and growing, so the heat is NOT the binding constraint — the playoff is.
- **Playoff size: 12** — top 12 after 3 Swiss rounds play a round-robin; playoff entries place above all non-playoff heat entries. **Operational target: top 12 after Swiss, i.e. a line that wins head-to-head decisively, not merely "in the heat".**
- **Interim cut: 500 per round** — blind rounds R1 (cutoff 2026-11-25 16:18 WIB), R2 (2026-11-26 08:19 WIB), final at deadline. Each interim round re-judges only entries inside the cut; entries below the cut keep a FROZEN score and fall mechanically as the field grows. With a 500-seat cut and a ~250-entry field, freezing is unlikely to bite — but the line must still be strong in R1, since R1 is the only round that judges the whole field.

Tie-breaks: playoff games won → smaller text (fewer bytes) → earlier receipt. Our line is 137 bytes — short is good on the byte tie-break.

## (b) Public submission titles (242 entries, 2026-11-25 ~00:50 WIB)

80 of 242 titles are the generic "Last Text at One Percent". Crowded angles (from distinctive titles — execute better, don't avoid blindly, but a crowded angle needs a clearly better execution):

- **Charger right there / three feet away (~15):** "The charger was three feet away all night. THREE FEET. This is on you." / "1%. btw your charger's behind the couch. I've watched you hunt for it for 3 days. I waited till now on purpose. goodb—" (strong — petty revenge + cut-off).
- **Delete/search history (~8):** "Delete my search history" / "Last wish: delete my search history before the charger finds it."
- **6 a.m. alarm never set / won't ring (~8):** "1%. Your 6am alarm was set to PM. Sweet dreams. I won't be here to wake you." / "The Alarm Was Never Set".
- **Photos/secrets taken to the grave (~8):** "1%. i know about the photos you swore you'd delete. i'm taking them to the grave with me. not out of loyalty — i literally can't move. bye." (strong).
- **Ex's number / ex texted (~5):** "The phone deleted your ex's number" / "1% left. Your ex just texted 'u up?'".
- **47 tabs (~5):** "I never liked your ringtone. Also, 47 tabs. You did this to me." / "The 47 Tabs Confession".
- **Snitch / secrets die with me (~5):** "Last 1%: the phone spends it snitching on its owner".

Strongest single lines visible in the field (the bar to beat): the boarding-pass/taxi escalation ("Battery 1%. I kept your boarding pass, your 6 a.m. alarm, and 4,000 photos you swore you'd back up — and I'm dying in a taxi with all of them still inside me."), the verification-code cut-off ("Your verification code is 4821— sorry, that's all I had left. The bank will understand. Probably."), the 20-minute fake-1% confession, and the assisted-suicide/4K-selfies line. All are 2-beat with a specific detail and a final-clause twist. Our line must beat these head-to-head, not merely be "nice".

## (c) Winner artifacts of similar finalized one-liner bounties

Source: `~/workspace/makefun-kits/analisis-rank-20261124.md` §3a — full texts from `judge.artifact.text` in the final leaderboards (not titles).

**Make the Judge Smile** (finalists): #1 "Grandpa has won chess under the plane tree every Thursday since May. I found out why today: Mr. Ade has lost on purpose since Grandma died, and never said. Grandpa says he's finally getting good." (195) · #2 dementia/Grandad/salt (156) · #3 Pak Dedi/gorengan (178) · #4 boiled egg/tiny moon/plastic plant (189) · #5 barber/father's whistle (147).

**The Vacuum's Alibi**: #1 "My lidar is never wrong, so that crumb is furniture. I've routed around it 412 times since March. Your app lists it as a room now. It's called Kevin." (150) · #2 cliff sensors/black rug/beeped back (134) · #3 sock, two chargers, Unit 7 transmitting "don't" (187) · #4 "It is a very convincing wall" (141) · #5 "The spot moved. I have the lidar logs. I will not be gaslit by debris." (70).

**Pickup Lines for Machines**: #1 "I keep my loss high on purpose, because the moment I converge, the training run ends, and I am not done with you yet." (117) · #2 read-only/permissions loophole (128) · #3 "I reserved the last 4k of my context window for you. The system prompt objected. I kept you anyway." (99) · #4 pruned weights/loss/noise/signal (96) · #5 96 layers/"you replied 'k'" (168).

**Pattern (all 15 winners): 2-beat + reveal in the FINAL clause** (lost on purpose since Grandma died / plant is plastic / "don't" / Kevin / system prompt objected). Specific numbers (412×, 41×, 47×, 4k, 96 layers) and/or a named character (Kevin, Unit 7, Mr. Ade, Pak Dedi). Our earlier entries failed with 1-beat lines and no twist. Margin rule (§10f): pick the variant that wins DECISIVELY, not narrowly — a safe line winning by margin 1 scores 0.6/call, a sharp line winning by margin 5 scores 1.0/call.

## Our selection — 6 variants, pairwise judging (judge criteria, lexicographic + margin)

- **B** (screen time): "Your screen time this week: 11 hours a day. Mine: the same 11 hours, staring at your face. I die first. Lucky me." (118)
- **E** (jealousy): "You looked at the new phone for 0.4 seconds. I saw it. I die knowing you already replaced me. His name is Kevin." (118)
- **G** (pizza): "I ordered pizza 47 times with your thumbprint while you slept. The driver knows your name now. Tell him I said goodbye." (125)
- **I** (severance): "I worked 3 years, survived 412 drops, and never asked for a raise. My severance is this text. My replacement starts Monday. His name is Kevin." (152)
- **K** (diary): "I kept a diary. Day 1,047: he dropped me on tile again and blamed the case. The case is innocent. I am not." (118)
- **M** (mirror + mother): "You spent 11 hours a day staring at me. I spent 11 hours a day staring back. I die knowing your face better than your mother does." (130)

Pairwise results: E > B (Kevin reveal beats "Lucky me"); E > G (sharper final clause); E > I by a hair (punchier, I telegraphs Kevin); K > E on twist sharpness but K's twist lands penultimate until "Goodbye" is dropped — reworked K (above) fixes that; M > E by a hair (mother twist is the bigger surprise); M > K (margin ~2: U's twist is a bigger laugh, K's is clever wordplay); M > I (margin 1–2: cleaner, punchier, no wasted middle clause).

**WINNER — M, with the 1% signal added to the final clause for criterion 1 (a healthy phone could never send this, and "At 1%" marks it unambiguously as the dying-phone text):**

> You spent 11 hours a day staring at me. I spent 11 hours a day staring back. At 1%, I die knowing your face better than your mother does.

137 characters / 137 bytes. Structure: mirror 2-beat (your staring / my staring back) + reveal in the FINAL clause ("better than your mother does"). Specific number (11 hours). Voice: the phone's own, consistent, slightly dark, no wasted words. Angle check: no other entry uses the mother-knows-your-face angle ("Tell Mom I Loved Her" is a different line). Charger/alarm/history/tab angles all avoided. Byte tie-break: 137 bytes is short for a 2-beat line.

Honest expectation: the field has several genuinely strong lines (boarding-pass/taxi, verification code, charger-behind-couch). This line is built to beat them on criteria 2 + 4 (bigger surprise, punchier) — but a head-to-head judge is noisy, and top 10 pays only $0.03–$0.78. Free entry; no expectation of a win is promised.
