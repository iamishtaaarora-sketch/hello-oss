# Contributing

Welcome. This page is the reference for the full setup and the errors you will probably hit. Nothing here is scary, everything here is fixable.

## One-time setup (terminal path only)

```bash
# Tell git who you are (shows up on your commits)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

For pushing to GitHub the easiest route is the GitHub CLI:

```bash
# macOS: brew install gh | Windows: winget install GitHub.cli | Linux: see cli.github.com
gh auth login
```

Pick `GitHub.com`, `HTTPS`, and `Login with a web browser`. After this, pushes just work.

## The flow

1. **Fork** this repo (your own copy under your account)
2. **Clone** your fork to your machine
3. **Branch**, make your change, **commit**
4. **Push** the branch to your fork
5. Open a **pull request** from your branch to our `main`

You never push to this repo directly. Everything arrives through pull requests. That is not a beginner restriction, it is how virtually every open source project on earth works.

## When it breaks

| You see | What happened | Fix |
|---------|---------------|-----|
| `Permission denied (publickey)` | Cloned with SSH but no SSH key set up | Re-clone with the HTTPS URL instead |
| `Authentication failed` | Git does not have your credentials | Run `gh auth login`, then retry the push |
| `Please tell me who you are` | Git identity not set | Run the two `git config` lines above |
| `remote: Permission denied` on push | You are pushing to OUR repo, not your fork | Check `git remote -v`. The URL must contain YOUR username |
| `failed to push some refs` | Your fork is behind | `git pull --rebase origin main`, then push again |
| Merge conflict in the PR | Someone edited the same lines before you | Pull latest main into your branch, fix the marked lines by hand, commit, push |
| Editor opened and you are trapped | Git wanted a commit message and opened vim | Type `:q!` then Enter. Next time use `git commit -m "message"` |

Not in the table? Paste the exact error in the group chat. Someone has hit it before.

## PR checklist

- The change does what the issue asked, and nothing else
- Commit message says what changed, in plain words
- You added yourself to MEMBERS.md at most once (we count)

## Being decent

Be patient with beginners, you were one. Review comments are about the code, never the person. Nobody gets mocked for a question.
