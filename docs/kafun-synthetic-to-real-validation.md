# kafun `:synthetic` → real-stand validation plan (DRAFT, AWAI-706)

> Draft only. No contact, no submission, no consent recorded here.
> kafun's `data/seed.edn` stands are all `:synthetic-*` prefectures; soma's
> `data/stand.edn` has no `:cryptomeria` trees. This plan describes how a REAL
> sugi stand would graduate from synthetic to verified — it does not graduate any.

## 0. Non-goals (what this plan never does)

- Never marks a real stand `:verified` from desk research alone.
- Never pulls owner-restricted data (e.g. 愛知県森林簿小班属性) without the
  owner's application + consent, handled by a human (sugi-kyoryoku G1).
- Never redefines kafun's `remediationVerdict` values; the bridge
  (`bridge-kafun-soma.md` in app-itonami-sugi-kyoryoku, AWAI-2928) owns that mapping.

## 1. Validation ladder (each rung needs a human sign-off)

1. **Range-check (desk, doable now).** Compare kafun synthetic stand parameters
   (area-ha, species, protected flag) against published yield-table bands:
   FFPRI 民有スギ人工林収穫予想表 (2026) and, for 愛知/岐阜, 収穫表調製業務研究資料
   #20. Record per-stand: in-band / out-of-band / unknown. Out-of-band →
   flag, do not silently rescale.
2. **Mesh cross-check (desk, PDL1.0 data).** Where 林野庁 G-space meshes cover the
   district, compare synthetic stand outline/height assumptions against
   樹種ポリゴン + DCHM + 20m資源量集計メッシュ aggregates. Meshes give
   aggregates, not per-tree DBH — a match here still leaves the stand `:unverified`.
3. **Owner consent (human).** Real per-stand attributes (森林簿抜粋, 施業履歴)
   enter only with the forest owner's consent + a recorded `:human-approved-by`,
   per sugi-kyoryoku charter G1/G2. Bot never records consent.
4. **Field survey (human/operator).** Every-tree DBH/height/lean/coords by survey;
   then and only then may a stand be proposed as `:verified`, with surveyor,
   date, and consent refs attached. Proposal is a draft until the owner approves.

## 2. Acceptance criteria for a `:verified` sugi stand

- All trees `:cryptomeria` with surveyed height-m / diameter-m / coords.
- Exclusions enumerated (roads, watercourses, crew positions at survey time).
- G5 statutory circle (2× height) computable — i.e. heights are real numbers,
  not band mid-points.
- Replant spec present (`:stand/replant`) — selective + regenerative only (G2);
  保安林 stands carry the permit path, never a bare `:protected` override
  (cf. `data/authorities.edn` `:shinrin-34-1`).
- Traceability: source URL or survey ref + consent ref + human approver on the stand.

## 3. Current state (2026-11-23)

- `data/stand-sugi-draft.edn`: format example, all `:unverified`. Rung 0.
- No stand is at rung 1 yet (range-check table not filled — owner task to confirm
  which kafun synthetic stands should even be range-checked first).
- Blocked on owner: which districts are in scope, consent workflow owner,
  registry/publication decisions (see PR report).
