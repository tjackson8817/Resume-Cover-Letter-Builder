# Resume & Cover Letter Tailoring

A single self-contained HTML tool that takes a real job posting and your actual resume, and generates a keyword/gap analysis, tailored bullet suggestions, and a cover letter draft — grounded strictly in what's actually true about you, never invented.

**[Open the live tool](https://tjackson8817.github.io/Resume-Cover-Letter-Tailoring/resume_cover_letter_tailoring.html)**

No install, no account, nothing sent anywhere — it's a static form that assembles text entirely in your browser.

## Fourth tool in this family

Alongside:
- **[Target-Company-Prompt-Builder](https://tjackson8817.github.io/Target-Company-Prompt-Builder/prompt_builder.html)** — researches and ranks companies
- **[Job-Posting-Finder](https://tjackson8817.github.io/Job-Posting-Finder/job_posting_finder.html)** — checks who's actively hiring, right now
- **[Outreach-Message-Builder](https://tjackson8817.github.io/Outreach-Message-Builder/outreach_message_builder.html)** — drafts the actual outreach messages

This tool is the one whose core input is fundamentally different from the rest — it needs the actual text of a job posting and your actual resume, not company research metadata. That's why it's a standalone tool rather than a mode added to an existing one.

## Files in this repo

| File | What it is |
|---|---|
| `resume_cover_letter_tailoring.html` | The interactive tool. Open it directly in any browser, or use the GitHub Pages link above. |
| `Resume_Cover_Letter_Tailoring_User_Guide.md` | Full usage guide. |
| `Resume_Cover_Letter_Tailoring_User_Guide.docx` | Same guide, as a Word document. |

## Quick start

1. Open `resume_cover_letter_tailoring.html` (via GitHub Pages, or download and double-click it).
2. Paste the full job posting text.
3. Paste your complete resume text, plus any additional context.
4. Choose what to generate (gap analysis, bullet rewrites, cover letter) and your tone.
5. Copy the generated prompt and paste it into a new Claude chat.
6. Review the gap analysis honestly, and check every bullet rewrite against your original before using it.

See `Resume_Cover_Letter_Tailoring_User_Guide.md` for the full walkthrough.

## The one non-negotiable rule

Nothing gets invented. Every resume bullet suggestion is a re-emphasis or re-wording of something genuinely already in your pasted resume — never a new employer, title, metric, achievement, or credential that wasn't actually there. If a job posting wants something your resume doesn't support, the tool is built to say so plainly rather than quietly writing a bullet that implies you have it. This is baked into the generated prompt as a hard rule, not a toggle. The same rule applies to the Qualifications Match Letter format below — every mapped qualification has to be genuinely true.

## Cover letter formats

Two shapes for the same purpose, chosen at generation time:

- **Traditional narrative** — the standard prose cover letter.
- **Qualifications Match Letter** — a short, position-focused opening paragraph followed by a two-column table: **Your Qualifications** (the posting's stated requirements) against **How I Meet / Exceed the Qualifications** (mapped to your real experience). This does a recruiter's requirement-matching work for them up front, which is exactly why it tends to get read all the way through — especially useful for postings with a long, explicit requirements list.
- Or generate **both** at once, at no extra cost.

## Recruiter identification

Optionally (on by default), the tool searches for who's actually likely handling a given posting — starting with "[Company] recruiter" — before drafting your letter. If a clear match is found, that name replaces "Dear Hiring Manager" in the salutation. If several names turn up, the tool disambiguates using each candidate's title and LinkedIn info to find the best functional match for the role, rather than guessing.

The honesty rule here is the strictest in this whole toolkit: if no real, verifiable recruiter can be found with reasonable confidence, the tool is instructed to say so and fall back to a professional generic salutation — never invent a plausible-sounding name. A fabricated name in a real cover letter is a genuine integrity problem, not a cosmetic shortcut. This feature requires Claude's **Web search** capability to be enabled.

## Formatting guarantees

Every table this tool produces — the Gap Analysis, Bullet Rewrites, and Qualifications Match Letter — is instructed to come back as a real formatted table (Word table object with a shaded header row in `.docx`, real markdown table in chat), not plain dashes or informal pairing standing in for one. Any cover letter or Qualifications Match Letter also gets genuine letter formatting: today's date, a proper salutation, clear paragraph breaks, and a proper closing — not one undifferentiated block of text.

## Notes

- This repo can be public or private — GitHub Pages on the free tier requires a public repo (or a paid plan for private-repo Pages).
- Like the Outreach Message Builder, this tool doesn't strictly require the Web search capability in Claude for its core functions — it becomes relevant only if recruiter identification is turned on.
