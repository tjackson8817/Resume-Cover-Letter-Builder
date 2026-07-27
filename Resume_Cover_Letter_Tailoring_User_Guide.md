# Resume & Cover Letter Tailoring — User Guide

This tool is a single web page (`resume_cover_letter_tailoring.html`) that takes a real job posting and your actual resume, and generates a keyword/gap analysis, tailored bullet suggestions, and a cover letter draft — all grounded strictly in what's actually true about you. Like the other tools in this family, it runs entirely in your browser: no install, no account, nothing sent anywhere until you copy the prompt and paste it into a Claude chat yourself.

---

## Claude Settings You'll Need Before You Start

| Setting | Why you need it | Where to find it |
|---|---|---|
| **Code execution and file creation** | Only needed if you choose the downloadable Word document output format. | **Settings → Capabilities**, toggle it on. |
| **Web search** | Only needed if **Try to identify the recruiter for this posting?** is set to Yes (the default). Without it, Claude can't actually search for a real recruiter — it would have no way to find one, and would correctly report that rather than fabricate a name. Turn recruiter identification off and this tool works fine without Web search. | Click the **+** (or slider) icon in the chat input, find **Web search**, toggle it on. |

Unlike the Job Posting Finder (where Web search is required for the tool to do anything at all), here it's conditional — only load-bearing for one specific optional feature.

---

## 1. How This Fits With the Rest of the Family

Four tools now, each solving a different stage:

| Tool | Solves |
|---|---|
| Target Company Prompt Builder | Researches and ranks companies |
| Job Posting Finder | Checks who's actively hiring, right now |
| Outreach Message Builder | Drafts the actual outreach messages |
| **Resume & Cover Letter Tailoring** (this tool) | Tailors your application once you've decided to actually apply |

This is the one tool in the family whose core input is fundamentally different from the others — it needs the **actual text of a job posting** and your **actual resume**, not company research metadata. That's why it's a separate tool rather than a mode bolted onto an existing one.

---

## 2. The Job Posting Field

Paste the full posting — title, company, description, requirements — not a summary. The more of the actual language you provide, the sharper the keyword/gap analysis can be, since it's comparing the posting's specific terminology against your resume's specific wording.

**Company** is optional but recommended — it scopes the recruiter search (Section 4) precisely, especially useful if the posting text doesn't clearly state the company name on its own.

**Tailoring more than one posting at once:** you can paste multiple postings, separated by a line of dashes (`---`). Worth knowing: this works best focused on your highest-priority opportunities (2-3 at a time), not your whole tracker at once — tailoring is inherently a per-application, close-attention task, and stretching it across many postings in one pass tends to dilute the depth of each.

---

## 3. Your Resume and Additional Context

**Your full resume text** is required — paste everything: all roles, bullets, skills, credentials. The gap analysis and bullet suggestions can only work with what's actually here. If a real accomplishment isn't in the pasted text, the tool has no way to know about it.

**Additional context** is optional and exists for exactly that gap — anything true about you that isn't yet reflected in your resume (a recent achievement, a certification in progress) or something you specifically want emphasized for this one application.

---

## 4. Recruiter Identification

**Try to identify the recruiter for this posting?** (default: Yes) asks Claude to search for who's actually likely handling this specific posting — starting with something like "[Company] recruiter" — before drafting the cover letter or Qualifications Match Letter.

Two outcomes, both handled honestly:

- **One or two clear candidates found** — that person's name gets used in the letter's salutation instead of "Dear Hiring Manager."
- **Three or more names turn up** — the tool doesn't just guess. It looks at each candidate's title and LinkedIn info to figure out who's actually the best match for *this* posting's function. A "Technical Recruiter — Cybersecurity" is a much better match for an OT security role than a "Recruiter — Finance & Accounting" at the same company, even if both technically work there.

Every result comes with a reported **confidence level** (High/Medium/Low) and brief reasoning, so you can judge the match yourself rather than trust it blindly.

**The honesty rule here matters more than almost anywhere else in this toolkit.** A fabricated recruiter name in a real cover letter isn't a cosmetic error — it's a genuine integrity problem, worse than an impersonal-but-honest "Dear Hiring Manager." The generated prompt is explicit: if no real, verifiable name can be found with reasonable confidence, Claude is instructed to say so plainly and fall back to a professional generic salutation, never to invent a plausible-sounding name or LinkedIn profile.

This feature requires the **Web search** capability — see the settings note above.

---

## 5. What Gets Generated

Four independent checkboxes — check any combination you want for a given run:

- **ATS / Keyword Gap Analysis** — compares the posting's actual requirements and terminology against your resume as written. Flags three things separately: what your resume already covers but in different words (a natural terminology swap), what your resume genuinely doesn't support (a real gap, named directly), and terminology the posting emphasizes that's missing even though the underlying experience exists.
- **Resume Bullet Rewrite Suggestions** — for your most relevant roles, suggests re-worded or re-ordered versions that surface what this specific posting cares about most. Shows the original bullet next to the suggested rewrite, so you can confirm every change is still accurate before using it.
- **Cover Letter Draft** (default: on) — the standard prose cover letter. Tone options: Warm/personable, Formal/executive, or Direct/concise. Grounded specifically in the posting's actual language and your real background, not a generic template with the company name swapped in. Comes with a **length** choice:
  - **1 page (standard)** — the conventional length for most roles.
  - **2–3 pages (detailed/executive)** — for executive-level, federal, or narrative-heavy applications where a longer letter is actually expected. Don't default to this unless the role genuinely calls for it — the extra length should be used for genuine substance, not padding.
- **Qualifications Match Letter (T-Letter)** (default: off) — a short, position-focused opening paragraph, followed by a two-column table: **Your Qualifications** (the posting's actual stated requirements, one by one) against **How I Meet / Exceed the Qualifications** (mapped directly to your real experience). This format does the recruiter's requirement-matching work for them up front — which is exactly why it tends to get read all the way through instead of skimmed, especially for postings with a long, explicit requirements list (common in federal, government-adjacent, and formal corporate roles). **Always kept to 1 page**, regardless of the Cover Letter length setting above — the whole point of this format is a fast, scannable read, so if a posting has many stated requirements, the prompt instructs Claude to prioritize the most important ones rather than let the table run onto a second page.

Since Cover Letter Draft and Qualifications Match Letter are independent checkboxes now, you can check both at once if you want both formats for the same posting — there's no need to choose only one.

---

## 6. The One Non-Negotiable Rule

Every other tool in this family has an honesty guardrail suited to what it produces — the Job Posting Finder won't fabricate postings, the Outreach Message Builder won't fabricate relationships. This tool's version matters more than either of those, because the thing at risk is **your resume's integrity**.

**Nothing gets invented.** Every bullet suggestion is a re-emphasis, re-ordering, or re-wording of something genuinely already in your pasted resume or additional context — never a new employer, title, responsibility, metric, achievement, or credential that wasn't actually there. If the posting wants something your resume doesn't support, the gap analysis says so plainly. A named, honest gap is a correct and useful answer. A fabricated qualification is not acceptable under any framing — this instruction is built into the generated prompt as a hard rule, not a suggestion, and there's no toggle to soften it.

**Practically, this means:** always read the bullet rewrites side by side with your originals before using them, and confirm every suggested change is something you can genuinely stand behind in an interview.

---

## 7. Output Format

- **Text in chat** (default) — clear headings for each section requested, with real markdown tables for the Gap Analysis, Bullet Rewrites, and Qualifications Match Letter sections (not plain dashes or informal pairing).
- **Downloadable Word document** — same structure, plus explicit formatting guarantees baked into the generated prompt:
  - Every table (Gap Analysis, Bullet Rewrites, Qualifications Match Letter) must be a **real Word table object** with a shaded header row — not plain text standing in for a table.
  - Any cover letter or Qualifications Match Letter must use **genuine letter formatting** — today's date, a proper salutation on its own line, clear paragraph breaks, and a proper closing — not run together as one undifferentiated block of text.
  - The Gap Analysis specifically comes back as a three-column table: **Requirement** (from the posting) / **Resume Coverage** (Covered, Terminology Gap, or Not Supported) / **Note**.

---

## 8. Typical Workflow, Start to Finish

1. Identify your highest-priority posting(s) — ideally ones you've already vetted using the rest of this toolkit.
2. Paste the full posting text.
3. Paste your complete resume text, plus any additional context.
4. Choose what to generate and your cover letter tone.
5. Copy the generated prompt, paste into a new Claude chat.
6. Review the gap analysis honestly — a real gap is useful information, not something to paper over.
7. Review every bullet rewrite against the original before using it.

---

## 9. Quick Troubleshooting

| Problem | Fix |
|---|---|
| Gap analysis feels shallow | Paste more of the actual posting text — a short summary gives less to compare against than the full requirements section. |
| Bullet suggestions feel generic | Make sure your full resume text was pasted, not just a summary — the tool can only rewrite what it can see. |
| Prompt panel just shows placeholder text | You need both a job posting and a resume pasted, and at least one of the four output checkboxes still checked. |
| Cover letter feels like it could apply to any company | Check that you pasted the actual posting text, not just a job title — specificity in the posting drives specificity in the letter. |
| In ChatGPT (or another tool), it asks clarifying questions instead of just running the task | The generated prompt now opens with an explicit "execute this directly, don't ask clarifying questions" instruction specifically to head this off — if it still happens, you can restate that instruction even more bluntly as a follow-up message. |
