# Field Notes

I would read this project from the data inward: cases first, implementation second.

The domain cases cover `index fit`, `join width`, `constraint risk`, and `plan drift`. They sit beside the smaller starter fixture so the project has both a compact scoring check and a domain-flavored review check.

`stale` is the strongest case at 289 on `index fit`. `recovery` is the cautious anchor at 131 on `plan drift`.

The extra check gives the repository a behavior path that can fail for a domain reason, not only a syntax reason.
