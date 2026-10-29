# Workflow: security finding handling

**Trigger:** during any read, you notice something like committed key files, `.env` files, user-data exports, server logs, or tokens in a README.

## Steps

1. **Don't open it.** Don't print, summarise, or copy its contents. File **names and paths** are enough.
2. Tell the user right away, in one short message: the paths, why they look sensitive, and that you didn't open them.
3. Create a **highest-priority** task in the "Platform Sync" project (or the equivalent), due within 1–3 days, that **the user does themselves**:
   1. Rotate every credential that may have been in those files: API keys, master or admin keys, provider keys, database passwords.
   2. Remove the files from **all git history** with `git filter-repo --path <file> --invert-paths` (or BFG), then force-push and re-clone.
   3. Add the paths to `.gitignore`. Move secrets to env vars or a secret manager.
   4. If the repo was ever public or shared, treat the old credentials as leaked.
4. Don't rotate keys, rewrite history, or force-push yourself.
5. Mention the open item in each daily message until it's done (one line).
6. Never put the contents, or any secret, in `profile/`, tasks, the brain delta, or a commit.
