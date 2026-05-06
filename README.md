# ledgersql

`ledgersql` is a SQL project in databases. Its focus is to validate double-entry ledger constraints and reconciliation queries.

## Why This Exists

The project exists to keep a narrow engineering decision visible and testable. For this repo, that decision is how index fit and constraint risk should influence a review result.

## Ledgersql Review Notes

For a quick review, compare `index fit` with `plan drift` before reading the middle cases.

## Capabilities

- `fixtures/domain_review.csv` adds cases for index fit and join width.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/ledgersql-walkthrough.md` walks through the case spread.
- The SQL code includes a review path for `index fit` and `plan drift`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Implementation Shape

The core code exposes a scoring path and the added review layer uses `signal`, `slack`, `drag`, and `confidence`. The domain terms are `index fit`, `join width`, `constraint risk`, and `plan drift`.

The SQL checks add a separate view over the domain review fixture.

## Local Usage

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Verification

The check exercises the source code and the review fixture. `stale` is the high score at 289; `recovery` is the low score at 131.

## Roadmap

The fixture set is small enough to audit by hand. The next useful expansion is malformed input coverage, not extra surface area.
