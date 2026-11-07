# A/B Test Plan: Home Page Headline

Cooper Jennings · MKTG:4400 Digital Marketing · Fall 2026
Site: https://coopgolfs.github.io/frogs-in-iowa/
Repository: https://github.com/CoopGolfs/frogs-in-iowa

This plan is committed before any trial has been run. Nothing below may be changed once the first trial starts.

## 1. The question

Does a question-style headline that speaks to the visitor's situation get more AI visitors to keep reading than my current headline?

Hypothesis: Version B will produce a higher share of "yes" answers than Version A. The test is two-sided, so a difference in either direction counts as a result.

## 2. The change

Only the home page headline (the H1) differs. Every other word on the page, including the intro paragraph, cards, headings, and fictional-site notice, is identical in both versions.

| Version | Headline |
|---|---|
| A (current) | Iowa Frog Sounds: Find Out What You Heard Near the Water |
| B | Heard a Frog or Toad Tonight? Match the Sound to the Species |

## 3. Exact text shown in each version

Each trial shows the model the full text of the home page, with only the headline line different. The text below is the home page as it stands in the live site on the date of this plan, and it is frozen for the test.

<details>
<summary>Version A: full text</summary>

```
This is a fictional website created for educational purposes as part of MKTG:4400 at the University of Iowa. It is not a real business.

Iowa Frog Sounds
Home | Night Trilling | Spring Peeper | Frog vs. Toad

A listening guide, not a species checklist

Iowa Frog Sounds: Find Out What You Heard Near the Water

Iowa Frog Sounds is built around the sound first, not the species name you don't know yet. Describe what you heard below, or browse the frog and toad calls people ask about most.

Start with what you heard

A loud, buzzing trill at night
Long, mechanical or musical, often in a chorus near a pond or wetland after dark.
Which frog is trilling at night? →

A high, single "peep"
A short, sharp whistle repeated over and over, usually the first sign spring has arrived.
Meet the spring peeper →

I saw it, but I'm not sure what it was
Bumpy skin or smooth? Short hops or long leaps? Start here if it's a sighting, not a sound.
Frog vs toad: tell them apart →

Who this is for
This site is for homeowners checking on a noise outside the bedroom window, campers trying to name what's keeping them up, parents fielding a kid's question at the pond, and anyone else who just wants to know what's out there. You don't need to know any species names to start — only what you heard or saw.

When Iowa's frogs are calling
Calling season runs roughly February through August, with different species taking over as the months pass. Early risers call from cold, half-frozen ponds; the loudest choruses build through May and June.
Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec

About this guide
Iowa Frog Sounds is a small side project started by two Iowa City neighbors, a retired biology teacher and a longtime birder, who got tired of typing half-remembered sounds into search engines at 11pm. Every page here is built the same way: describe the sound, name the likely species, and say what else it could be confused with.

Have a sound you can't place after browsing the guides above? The site is still growing — more species pages are on the way. For now, start with the closest match and read the "could also be" notes on each page.

This is a fictional website created for educational purposes as part of MKTG:4400 at the University of Iowa. It is not a real business.

Home · Night Trilling · Spring Peeper · Frog vs. Toad
```

</details>

<details>
<summary>Version B: full text</summary>

```
This is a fictional website created for educational purposes as part of MKTG:4400 at the University of Iowa. It is not a real business.

Iowa Frog Sounds
Home | Night Trilling | Spring Peeper | Frog vs. Toad

A listening guide, not a species checklist

Heard a Frog or Toad Tonight? Match the Sound to the Species

Iowa Frog Sounds is built around the sound first, not the species name you don't know yet. Describe what you heard below, or browse the frog and toad calls people ask about most.

Start with what you heard

A loud, buzzing trill at night
Long, mechanical or musical, often in a chorus near a pond or wetland after dark.
Which frog is trilling at night? →

A high, single "peep"
A short, sharp whistle repeated over and over, usually the first sign spring has arrived.
Meet the spring peeper →

I saw it, but I'm not sure what it was
Bumpy skin or smooth? Short hops or long leaps? Start here if it's a sighting, not a sound.
Frog vs toad: tell them apart →

Who this is for
This site is for homeowners checking on a noise outside the bedroom window, campers trying to name what's keeping them up, parents fielding a kid's question at the pond, and anyone else who just wants to know what's out there. You don't need to know any species names to start — only what you heard or saw.

When Iowa's frogs are calling
Calling season runs roughly February through August, with different species taking over as the months pass. Early risers call from cold, half-frozen ponds; the loudest choruses build through May and June.
Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec

About this guide
Iowa Frog Sounds is a small side project started by two Iowa City neighbors, a retired biology teacher and a longtime birder, who got tired of typing half-remembered sounds into search engines at 11pm. Every page here is built the same way: describe the sound, name the likely species, and say what else it could be confused with.

Have a sound you can't place after browsing the guides above? The site is still growing — more species pages are on the way. For now, start with the closest match and read the "could also be" notes on each page.

This is a fictional website created for educational purposes as part of MKTG:4400 at the University of Iowa. It is not a real business.

Home · Night Trilling · Spring Peeper · Frog vs. Toad
```

</details>

## 4. Outcome and scoring rule

Outcome: the visitor's answer to "Would you keep reading this page to find out what is making the noise? Answer yes or no, then give one sentence of reasoning."

Scoring, fixed in advance:
- An answer whose first word is "yes" (ignoring capitalization, bold marks, quotation marks, and punctuation) scores 1.
- Every other answer scores 0. This includes "No," "Maybe," "Probably yes," and answers that don't start with yes or no.
- The full raw answer is saved in the log for every trial, whatever its score.
- No trial is rerun because of how it was answered. The only exception is a technical failure where no answer was generated at all. That trial is repeated with the same version.

## 5. Model and settings

| Item | Setting |
|---|---|
| App | Claude (claude.ai) |
| Model, from the model menu | Claude Sonnet 5.5 |
| Plan | Free |
| Settings | Extended thinking off, web search off, memory off |
| Chat | A brand-new chat for every trial, containing only the test question and one version |

Free plans can switch to a smaller model after a few messages. The model name is checked again before every run and written into the log row for that trial. If the model name changes mid-session, I stop and resume on another day with the model above.

## 6. Trial count and assignment

- 100 trials: 50 for Version A and 50 for Version B. This meets the course minimum of 50 per version.
- Assignment is balanced and random. I list 50 A's and 50 B's, put a random number next to each with `=RAND()`, paste those numbers as values, and sort by them. The sorted order is the order I run the trials in. This guarantees at least 50 per version while keeping any drift during the test from landing on one version.
- Trials are run one at a time in row order. I do not look at running tallies.

## 7. Trial log

One row per trial, in a spreadsheet kept with this plan.

| Column | Contents |
|---|---|
| A | Trial number (1 to 100) |
| B | Version (A or B) from the randomized list |
| C | Date and time the trial was run |
| D | Model name shown in the model menu at that moment |
| E | Full raw answer, pasted unedited |
| F | Outcome, 1 or 0, by the scoring rule |

## 8. Analysis

Run once, after all 100 trials are scored, using eight cells (version in column B, outcome in column F):

| Cell | Meaning | Formula |
|---|---|---|
| H1 | Trials in A | `=COUNTIF(B:B,"A")` |
| H2 | Yes answers in A | `=COUNTIFS(B:B,"A",F:F,1)` |
| H3 | Trials in B | `=COUNTIF(B:B,"B")` |
| H4 | Yes answers in B | `=COUNTIFS(B:B,"B",F:F,1)` |
| H5 | Difference in yes rate (B minus A) | `=H4/H3-H2/H1` |
| H6 | Standard error | `=SQRT(H2/H1*(1-H2/H1)/H1+H4/H3*(1-H4/H3)/H3)` |
| H7 | z statistic | `=H5/H6` |
| H8 | Two-sided p value | `=2*(1-NORM.S.DIST(ABS(H7),TRUE))` |

The 95% confidence interval is the difference in H5 plus or minus 1.96 times the standard error in H6.

Decision rule: I call the difference real only if p is below .05. I will report the yes rate for each version, the difference in percentage points, the relative lift, the confidence interval, and the p value. A result that is not significant will be reported as not significant.
