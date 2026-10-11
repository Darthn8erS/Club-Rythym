# Club Rhythm 2.0 development rules

## Protect production
- Do not edit, overwrite, rename, move, or delete index.html or game.html without explicit owner approval.
- Development changes belong in test.html and new development-only assets (use a dev/ directory if needed). Never modify assets used by production.
- Keep gameplay/timing changes scoped to an explicitly approved task.
- Do not change GitHub Pages settings, Firebase rules/data, repository permissions, or integration access without owner approval.

## Isolation
- test.html starts from the production game with the same gameplay, drawing, audio analysis, difficulty choices, and timing controls. It is labeled TEST.
- Test player names and scores use clubRhythmDevPlayer and clubRhythmDevScores. Production browser storage keys are not used.
- Firebase is intentionally disconnected in test.html. Test leaderboards are local-only; do not reconnect to production Firebase. A separate test backend requires approval.
- MP3 decoding remains local. The existing optional iTunes artwork lookup remains and may send song metadata or filenames to Apple.

## Branch and review workflow
1. Work on development (or a feature branch based on it), not directly on main.
2. Open a pull request to main for approved test-version updates. Review every changed path before merging.
3. Reject any unintended production-file changes. Preserve index.html exactly.
4. Merge only approved development files. Pages publishes main / root: merging test.html updates /test.html; unmerged development commits are not public Pages previews.
5. Verify both URLs after deployment and compare index.html with the baseline. Never promote test.html over index.html without explicit approval.

## Baseline
- Production file commit: eb24e153787cf8872cdbc0f2aefa119fd0d39da0
- SHA-256 of production source text: b3ee8bf55d59344c63cbfe527c1b69af00fa84b12ccb1d3f0ea448e2daed480a
- Original: https://darthn8ers.github.io/Club-Rythym/
- Test: https://darthn8ers.github.io/Club-Rythym/test.html

## Assistant access
These instructions are workflow safeguards, not enforced file-level access controls. A repository writer may be able to alter any file. Do not grant Muse or another assistant access without explicit owner approval. Confirm the exact app and its supported GitHub integration first. Stronger enforcement (review rules, branch protection, or a separate development repository) requires a separate review and approval.
