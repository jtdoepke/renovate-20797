# renovate-20797

This repository is a minimal reproduction of https://github.com/renovatebot/renovate/issues/20797.

It contains chartfile.yaml, which is the Helm chart dependency file for [Tanka](https://tanka.dev/helm).
This dependency file type doesn't have built-in support from Renovate, so you need to use a regex manager
to get Renovate to update it.

PR https://github.com/jtdoepke/renovate-20797/pull/2 is an onboarding pull request for Renovate. It adds
both the regex manager for chartfile.yaml, and a comment to chartfile.yaml that Renvoate needs to determine
the Helm chart URL. However, the PR description does not show what Renovate would do with this repository
if the onboarding PR were merged because the PR description is based on an evaluation of the chartfile.yaml
on the `main` branch, contain the required comment yet.

PR https://github.com/jtdoepke/renovate-20797/pull/3 shows what I believe the PR should look like. The
"What to Expect" section shows that a Helm chart upgrade will be performed. (I got renovate to simulate
this by setting `baseBranches`.)
