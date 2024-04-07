# Lerna issue example

Issue: Lerna 8 doesn't work if pnpm contains an exclusion in `pnpm-workspace.yaml`.

Steps to reproduce:

1. Run `pnpm install`
2. Run `pnpm exec lerna list`, it will report 0 package found.
3. Comment out the exclusion line from `pnpm-workspace.yaml` and run `pnpm exec lerna list` again.
4. It reports 2 packages found.

To validate with lerna 7, run `pnpm uninstall lerna` and `pnpm install -w lerna@7`, then repeat step 2 to 4 above. In both cases it will report 2 packages found.