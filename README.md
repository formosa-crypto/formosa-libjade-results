# formosa-libjade results

Proof-checking timings, cycle benchmarks and checks of
[formosa-libjade](https://github.com/formosa-crypto/formosa-libjade), one record per
commit on its `main` branch, published at
https://formosa-crypto.github.io/formosa-libjade-results/.

- `data/proofs/<commit>.json`: EasyCrypt proof-checking time per file, with
  the machine and tool versions of the run (main).
- `data/bench/<runner>/<commit>.json`: median cycles per scheme, backend and
  operation over several passes, with their spread and the environment (main).
- `data/checks/<commit>.json`: the checks of the commit (KATs, Valgrind's
  memcheck, CT and SCT per parameter set, extraction of the EasyCrypt models),
  one result per check and target, with the tool versions (main); its
  `data.claims` (scripts/claims.py) gives the lemma of each proved claim of
  each implementation, shown in the Proofs card of the Checks tab.
- `data/pr/<number>/{bench/<runner>,proofs,checks}/<commit>.json`: the same
  for the runs of a pull request, with the PR's merge base; kept apart from
  main's history (delete a PR's folder to prune it).
- `site/`: the dashboard. `tools/build_index.py` generates, at deploy time,
  a light `index.json` (main commits and their run metadata, PRs), the
  Trends data (`series/`) and one manifest per PR (`pr/<number>.json`).

The files are pushed by formosa-libjade's CI (a publish job on a GitHub-hosted
runner, with this repo's deploy key) and are never edited afterwards; the
`pages` workflow rebuilds and deploys the site on every push.
