# Cybersecurity Journey — Offensive Security Track
Documenting my path from zero to offensive security, one small session at a time.
**Background:** EEE student, learning alongside a full academic course load.
**Focus:** Offensive security (pentesting → red teaming)
**Method:** Small daily sessions (~20 min) + spaced repetition (Anki) + weekend application
---
## Current Stage
`Stage 1 — Foundations (Week 3, started 2026-07-01)`
## Stats
- Weeks completed: 2 (started 2026-07-01, currently in Week 3)
- TryHackMe rooms completed: 3
- OverTheWire Bandit levels completed: 10 (0→10)
- Certifications: None yet (target: eJPT around month 8-10)
---
## Progress Log
| Date | Resource | Task | Key Takeaway |
|------|----------|------|---------------|
| 2026-07-01 | OverTheWire Bandit | Level 0→1 | ssh reconnect requires the new level's username, not the old one |
| 2026-07-02 | OverTheWire Bandit | Level 1→2 | ./ forces a literal filename, even one that looks like a flag |
| 2026-07-02 | OverTheWire Bandit | Level 2→3 | quotes stop word-splitting on spaces, ./ stops leading dashes being read as flags |
| 2026-07-03 | OverTheWire Bandit | Level 3→4 | Hidden files begin with `.`, use `ls -a` to reveal them. |
| 2026-07-03 | OverTheWire Bandit | Level 4→5 | Use `file` to identify a file's actual type before reading it. |
| 2026-07-03 | OverTheWire Bandit | Level 5→6 | Learned to use `find` to search files by properties (size), and discovered that `*` wildcards do not match hidden files. |
| 2026-07-03 | OverTheWire Bandit | Level 6→7 | Used `find` with multiple filters (-user, -group, -size) to locate a file across the entire filesystem. |
| 2026-07-12 | TryHackMe | Pre Security — Module 1: Intro to Cyber Security (all 3 rooms) | Blue Team vs Red Team; pentester vs red teamer distinction; Gobuster for hidden-page enumeration |
| 2026-07-19 | OverTheWire Bandit | Level 7→8 | `grep` searches file contents for a text pattern (vs `find`, which searches the filesystem by attribute); grep streams line-by-line so it stays fast on large files. |
| 2026-07-19 | OverTheWire Bandit | Level 8→9 | `sort` orders lines so `uniq -u` (which only compares adjacent lines) can isolate the one line with no duplicate |
| 2026-07-19 | OverTheWire Bandit | Level 9→10 | `strings` extracts human-readable text from binary files; piped to `grep "==="` to isolate the password line |
---
## Monthly Reflections
### Month 1
- What I learned:
- What was hardest:
- What I'd do differently:
---
## Milestones
- [ ] Complete OverTheWire Bandit (0–20+)
- [ ] Complete TryHackMe Pre Security path
- [ ] Complete TryHackMe Offensive Pentesting path (or HTB equivalent)
- [ ] Complete PortSwigger Web Security Academy
- [ ] Pass eJPT
- [ ] Complete first HTB retired box write-up