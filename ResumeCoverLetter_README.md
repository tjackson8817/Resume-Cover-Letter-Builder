# Resume & Cover Letter Tailoring

A single self-contained HTML tool that takes a real job posting and your actual resume, and generates a keyword/gap analysis, tailored bullet suggestions, a cover letter draft, and/or a Qualifications Match Letter (T-Letter) — grounded strictly in what's actually true about you, never invented.

**[Open the live tool](https://tjackson8817.github.io/Resume-Cover-Letter-Builder/resume_cover_letter_tailoring.html)**

No install, no account, nothing sent anywhere — it's a static form that assembles text entirely in your browser.

## Fifth tool in this family

Alongside:
- **[Career-Path-Discovery-Prompt-Builder](https://tjackson8817.github.io/Career-Path-Discovery-Prompt-Builder/prompt_builder.html)** — Step 0, for when you're not sure what to target yet
- **[Target-Company-Prompt-Builder](https://tjackson8817.github.io/Target-Company-Prompt-Builder/prompt_builder.html)**
- **[Job-Posting-Finder](https://tjackson8817.github.io/Job-Posting-Finder/job_posting_finder.html)**
- **[Outreach-Message-Builder](https://tjackson8817.github.io/Outreach-Message-Builder/outreach_message_builder.html)**

This tool's core input is fundamentally different from the rest — it needs the actual text of a job posting and your actual resume, not company research metadata. That's why it's a standalone tool rather than a mode added to an existing one.

## Files in this repo

| File | What it is |
|---|---|
| `resume_cover_letter_tailoring.html` | The interactive tool. |
| `Resume_Cover_Letter_Tailoring_User_Guide.md` | Full usage guide. |
| `Resume_Cover_Letter_Tailoring_User_Guide.docx` | Same guide, as a Word document. |
| `Sale_Fish_Resume_Cover_Letter_Tailoring_Combined_Guide.docx` | Same guide content, combined with an "About This Tool" overview section, for Sale Fish–branded distribution. |
| `sample_prompt_pivot_positioning.txt` | Real example of the generated prompt — a career-pivot scenario (Sarah Chen, Senior Account Executive moving into Customer Success), showing Gap Analysis, Bullet Rewrites, Pivot Positioning Notes, and a Cover Letter Draft together. |
| `resume_sample_output.md` / `.docx` | The actual output Claude returns when that prompt is run — same content, two formats. |
| `new_sample_prompt.txt` | A second real example, covering the checkboxes the first sample doesn't: Gap Analysis, Bullet Rewrites with "apply directly," a Cover Letter, and a Qualifications Match Letter (T-Letter), for a non-pivot senior-level application (Tom Jackson, OT Cybersecurity Executive, applying to PwC). |
| `new_sample_output.docx` | The actual output for that second prompt — includes the applied-rewrites Updated Resume section, not shown in the first sample. |
| `Example_Resume_Tom_Jackson.docx` | The source resume used in the second sample above, as a standalone reference. |
| `Example_Cover_Letter.docx` / `Example_T-Letter.docx` | The Cover Letter and T-Letter sections from the second sample, as standalone reference documents. |

## Quick start

1. Open `resume_cover_letter_tailoring.html`.
2. Paste the full job posting text (and optionally the company name).
3. Paste your complete resume text, plus any additional context.
4. Check any combination of: ATS/Keyword Gap Analysis, Resume Bullet Rewrite Suggestions, Cover Letter Draft, Qualifications Match Letter (T-Letter), Pivot Positioning Notes. All five are independent — check as many as you want.
5. Set your cover letter tone and length (1 page or 2-3 pages).
6. Copy the generated prompt and paste it into a new Claude chat.
7. Review the gap analysis honestly, and check every bullet rewrite against your original before using it.

See `Resume_Cover_Letter_Tailoring_User_Guide.md` for the full walkthrough.

## What gets generated

Five independent checkboxes, not a single locked format:

- **ATS / Keyword Gap Analysis** — a three-column table: Requirement / Resume Coverage / Note.
- **Resume Bullet Rewrite Suggestions** — a two-column table: Original / Suggested Rewrite.
- **Cover Letter Draft** (default: on) — traditional prose letter. Length choice: **1 page (standard)** or **2-3 pages (detailed/executive)**, for roles that genuinely call for the longer form.
- **Qualifications Match Letter / T-Letter** (default: off) — a short opening paragraph plus a two-column table (Your Qualifications / How I Meet or Exceed the Qualifications). **Always kept to 1 page**, regardless of the Cover Letter length setting — its whole purpose is a fast, scannable read for the reviewer.
- **Pivot Positioning Notes** (default: off) — for when a posting represents a genuine change of direction from what your resume's titles alone suggest, not just a same-lane application. Checking it reveals an optional field to name the pivot yourself; leave it blank and Claude infers the gap from your resume's apparent trajectory instead. Produces direct positioning guidance: what to lead with, what to minimize (not hide), any real skill/certification gaps worth naming, and an honest answer for "why this move" — grounded only in what's actually true, same as every other section.

Cover Letter Draft and the T-Letter can both be checked at once if you want both formats for the same posting. Pivot Positioning Notes can be combined with any of the others in the same run.

### Optional: apply the suggestions directly

Two additional checkboxes, nested under Gap Analysis and Bullet Rewrites respectively, ask for a ready-to-use **updated resume** with those suggestions actually applied — rather than leaving you to manually incorporate every table row yourself:

- Also produce an updated resume with the Gap Analysis keyword alignments applied
- Also produce an updated resume with the Bullet Rewrite suggestions applied

Each requires its parent checkbox (Gap Analysis / Bullet Rewrites) to be checked, since the updated resume is built strictly from what those tables already justified — check one, the other, or both together for a single resume reflecting both categories of changes. This is additive: the recommendation tables still get generated in full, this just adds a finished version on top. Same non-negotiable rule applies — nothing beyond what the tables already proposed gets applied.

## The one non-negotiable rule

Nothing gets invented. Every resume bullet suggestion is a re-emphasis or re-wording of something genuinely already in your pasted resume — never a new employer, title, metric, achievement, or credential that wasn't actually there. If a job posting wants something your resume doesn't support, the tool is built to say so plainly rather than quietly writing a bullet that implies you have it. This is baked into the generated prompt as a hard rule, not a toggle.

## Recruiter identification

Optionally (on by default, requires Web search), the tool searches for who's actually likely handling a given posting before drafting either letter. This runs in two tiers:

- **Tier 1 — function match.** Searches for a recruiter whose title matches the posting's department/function (e.g. a "Technical Recruiter — Cybersecurity" for a security role). If a clear match is found, that name replaces "Dear Hiring Manager" in the salutation. If several names turn up, the tool disambiguates using each candidate's title and LinkedIn info to find the best functional match.
- **Tier 2 — broader fallback, only if Tier 1 comes up empty.** Searches more broadly by the posting's location and by role-appropriate seniority. Candidates found this way are **not** picked automatically — the letter drafts with a generic salutation, and every Tier 2 candidate is listed separately (name, title, LinkedIn URL, location, confidence, reasoning) so you can choose whether to swap one in yourself. These are inherently lower-confidence than a direct department match.

If no real, verifiable name can be found with reasonable confidence at either tier, the tool falls back to a professional generic salutation — never invents one.

## Formatting guarantees

Every table this tool produces is a real formatted table (Word table object with a shaded header row in `.docx`, real markdown table in chat) — not plain dashes standing in for one. Any cover letter or T-Letter gets genuine letter formatting: date, salutation, paragraph breaks, and closing, not one undifferentiated block of text.

## Notes

- This repo can be public or private — GitHub Pages on the free tier requires a public repo (or a paid plan for private-repo Pages).
- Requires **Code execution and file creation** only if you choose the Word document output format. Requires **Web search** only if recruiter identification is on (the default).
- The generated prompt opens with an explicit "execute this directly, don't ask clarifying questions first" instruction, aimed at other AI tools (e.g. ChatGPT) that sometimes respond with a plan or questions instead of just running the task.
