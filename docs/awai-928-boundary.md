# Boundary with AWAI-928 `app-itonami-public-kafun-bokumetsu` (DRAFT note)

> Draft only. This note records the division of labour so the two tracks do not
> duplicate each other. It changes nothing in the bokumetsu repo; any joint change
> needs AWAI-928-side agreement first (per the bridge doc's rule 3).

Source of truth for the bridge: `bridge-kafun-soma.md` in
`app-itonami-sugi-kyoryoku` (AWAI-2928 draft PR #1) — this note builds on it,
it does not fork it.

## Their track (AWAI-928)

- Repo: `cloud-itonami/app-itonami-public-kafun-bokumetsu`.
- Scope: 花粉撲滅 Fund's `research → action → capability` record
  (`kotoba/` collections + coverage) and the appview skeleton.
- Level: research funding / program actions, not individual stands.

## Our track (AWAI-706, this PR)

- Repo: `cloud-itonami/app-itonami-soma` (this repo).
- Scope: public sugi standing-data source inventory + soma-format sugi-stand
  draft entries (`:unverified`) + kafun synthetic-to-real validation plan.
- Level: stand/tree data + planning format, no funding records.

## Non-duplication rules (from the bridge doc, restated)

1. `remediationVerdict` is canonical in kafun's `lex/remediationVerdict.edn`.
   Neither track redefines verdict values.
2. bokumetsu `action` ≠ bridge `:stand-worklist` edge. Cross-reference by
   stand id; never copy records across repos.
3. If this track ever needs a bokumetsu-side `action` written, get AWAI-928
   agreement first; do not extend their schema unilaterally.
4. soma safety gates (G5 statutory circle, G7 protected refusal) hold
   regardless of which track a stand came through.

## Open coordination items (owner-blocked)

- Confirm AWAI-928 owners accept rules 1–4 (read-only from here; no Linear writes).
- Confirm the `:stand-worklist` handoff edge stays in sugi-kyoryoku/AWAI-2928
  and is NOT re-implemented in either repo.
