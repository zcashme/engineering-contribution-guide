# How we contribute

Welcome to Zcashme. Read this before your first contribution.

We always identify the work in a GitHub issue first. We land work through a pull request.

## Issues first

Start with an issue. If one does not exist yet, create it.

Search first so we do not open a duplicate. If one already exists, use that.

Write enough that someone else could pick it up:

- what is wrong, or what you want
- how you noticed it (steps, a link, a screenshot)
- what “done” looks like

Then take it:

1. Check that nobody else is already assigned, and that nobody said they are working on it.
2. Assign yourself, or comment that you are taking it.
3. If it is assigned to someone else, talk to them first.

One person owns an issue at a time unless you agreed to work on it together.

If you stop, say so on the issue and unassign yourself.

## Branches and pull requests

Create a branch from the latest `main`. Name it after the work, for example `fix/otp-window` or `feat/registration-term`.

Open a pull request from that branch into `main`. You can open it as a draft while you are still working. Mark it ready when you want a review.

A pull request should say:

- what changed
- why
- how to check it
- the issue it closes (`Closes #12`)

Keep pull requests small enough to review in one sitting. If the work is large, split it.

Wait for checks to finish. Do not merge while they are red, unless the failure is clearly unrelated and you have said so on the pull request.

Delete the branch after the pull request is merged.

## Update before you push

Before you start, before you push, and before you ask for review:

1. Fetch the latest from GitHub.
2. Update `main`.
3. Update your branch with that `main`.

```bash
git fetch origin
git checkout main
git pull origin main
git checkout your-branch
git rebase origin/main
git push --force-with-lease
```

`--force-with-lease` is only for your own branch after a rebase. Do not force-push someone else’s branch unless they asked you to.

If you hit conflicts you are unsure about, ask.

## Review and merge

You need one approval before merging, except:

- documentation-only fixes
- small CI fixes
- other changes that cannot break the product (typos, comments, formatting)

If the change can alter behavior, protocol, or data, it needs an approval even if it looks small.

The approval must come from someone who did not author the pull request.

Do not merge someone else’s pull request unless they asked, or you have informed them.

## Working on someone else’s branch

It is OK to push to a colleague’s branch if you agreed verbally (or in chat) first.

When you do:

- tell them once you have pushed, so they can pull
- do not force-push unless they asked
- do not change the point of the pull request without saying so

If they have not agreed, open your own branch and pull request into their branch, or leave a review comment.

## Reviews

If you are asked to review, look at the diff, and say what is blocking merge versus what is a suggestion.

Prefer not to block the pull request. Leave comments (or approve with comments) and trust the author to take the feedback into account.

Use **Request changes** only when the pull request should not merge until those points are handled. That also means you are available to re-review when they push again. Do not request changes and then disappear.

If you are the author, answer every comment. Either change the code, or say why you are not changing it.

If you are not addressing something now, do not leave it silent. Put a `TODO` in the code, or open a new issue and link it from the pull request.

## Secrets

Do not commit passwords, API keys, seed phrases, `.env` files, or wallet material.

If you committed a secret by mistake, tell someone. Deleting it in a later commit is not enough.
