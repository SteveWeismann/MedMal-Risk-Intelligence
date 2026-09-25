# CHART Risk Intelligence — Dashboard Prototype

A working design prototype of the risk-intelligence dashboard for the CHART Claim
Analysis Capability, built by MAPS Technologies.

> **All data in this prototype is synthetic.** No CHART claim information has been
> processed. Every matter number, finding, member hospital and figure is invented
> for design review.

---

## What this is

A single self-contained HTML page. No build step, no dependencies, no server —
open `index.html` in any browser and it runs.

It exists to settle one question ahead of the Statement of Work: **what should the
platform actually show?** Each panel is labelled with the CHART SOW objective it
serves, so coverage can be checked against CHART's own document rather than
argued about.

## Views

| Tab | Covers |
|---|---|
| Overview | Daily working view — what changed overnight, the disposition queue, the priority matters |
| Clinical risk | Findings by category, standard-of-care issues, contributing factors, responsible service, severity |
| Developing claims | Open matters under analysis, information gaps, document intake |
| Claims support | Phase 1A — liability factors, severity factors, posture considerations, comparable matters |
| Mitigation & trends | Trend over time, where to focus, whether mitigation is working, effect on the existing review |
| Members | Normalized per-member rates and Refocus activity |
| Reports | The proposed report catalogue, alert routing, distribution |

## Two things worth clicking

**Any table row** opens the finding detail: the quoted record, the citation to
document and page, a chronology with the entries the finding rests on marked, and
the disposition controls required by SOW parameter P.4.

**The Show control** at the top switches between full capability, Phase 1, and
first release — 28 views down to 8. Sequencing is visible rather than asserted.

## Design decisions carried from the SOW work

- Findings carry an **evidentiary grade** (supported / recorded / proposed). A cause
  is asserted only at the supported threshold.
- Every assertion traces back to its source document and page (objective 1A.7).
- Open-claim findings are marked **protected** and must reach a disposition —
  submit to PSO, retain as work product, or discard (parameter P.4).
- A **reviewed and not flagged** panel shows the boundary of the system's attention
  (parameter P.5).
- No system-generated claim value on an open matter; severity-associated factors
  and comparables only (objective 1A.2).
- Clinical coding follows the CRICO CBS convention: responsible service, major
  allegation, clinical severity, contributing factors.
- Financial metrics follow standard medical professional liability practice:
  incurred indemnity and ALAE shown separately, frequency, severity,
  report-to-close lag.

## Files

| File | Purpose |
|---|---|
| `index.html` | The prototype. This is what GitHub Pages serves. |
| `prototype-compact.html` | A trimmed 41 KB build, small enough to paste into a chat tool. |

## Publishing with GitHub Pages

1. **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)` → **Save**
4. Wait about a minute. The URL appears at the top of that page:
   `https://<your-username>.github.io/<repo-name>/`

**Before you publish:** GitHub Pages on a free account only works from a **public**
repository, which means anyone with the URL can open the page and search engines can
find the repo. The page carries a `noindex` tag, but the repository itself is still
public. For a CHART-branded prototype, consider GitHub Pro (private repos can serve
Pages) or a host that supports password protection.

## Status

Prototype build 0.2 — for discussion, not a commitment to scope, schedule or cost.
