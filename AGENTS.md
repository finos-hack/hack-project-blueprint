# Agent instructions

Coding agents working in this repository must sign every commit with a Developer Certificate of Origin (DCO) sign-off. The DCO bot rejects a pull request if any commit on the branch is missing one. See [CONTRIBUTING.md](./CONTRIBUTING.md).

The sign-off is the human contributor's certification under the [Developer Certificate of Origin](https://developercertificate.org/). Do not invent a name or email, and do not substitute `Co-authored-by`.

Every commit message must end with a trailer that matches the commit author exactly:

```text
Signed-off-by: Ada Lovelace <ada@example.com>
```

1. Read the configured identity:

   ```bash
   git config user.name
   git config user.email
   ```

2. If either value is empty, stop and ask the human to set their own name and email. Do not run `git config`, and do not set `GIT_AUTHOR_NAME`, `GIT_AUTHOR_EMAIL`, `GIT_COMMITTER_NAME`, or `GIT_COMMITTER_EMAIL`.
3. Commit with `-s` / `--signoff`. Do not pass `--author`.

   ```bash
   git commit -s -m "$(cat <<'EOF'
   Add quote lookup for the demo portfolio

   EOF
   )"
   ```

4. The email must be an address on the contributor's GitHub account. If they keep their email private, use the GitHub noreply address already in `user.email` (`ID+username@users.noreply.github.com`).

If you just created an unpushed commit and it is missing the trailer, repair it with `git commit --amend -s --no-edit` before it is pushed. Do not interactive-rebase and do not force-push unless the human explicitly asks. If older commits on a pushed branch fail the DCO check, tell the human. The repair is `git rebase HEAD~N --signoff` followed by a force push, and they should request that explicitly.
