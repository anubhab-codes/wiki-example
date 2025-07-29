You're absolutely right — the best CONTRIBUTING.md files are written in a task-oriented, "How do I..." style to help contributors quickly find and follow practical steps.

Let me now rewrite your CONTRIBUTING.md using a "How to" format, tailored to your SailPoint IIQ project:


---

✅ CONTRIBUTING.md (How-To Style)

# Contributing to the SailPoint IIQ Project

Welcome! This guide helps you contribute safely and consistently to this repository. Please follow the instructions below for creating branches, writing commits, raising pull requests, and handling hotfixes.

---

## How do I start working on a new feature or bug?

1. Make sure you're on the latest `dev` branch:

```bash
git checkout dev
git pull origin dev

2. Create a new feature or bugfix branch:



git checkout -b feature/SSB-123-add-xyz-app
# or
git checkout -b bugfix/SSB-456-fix-account-correlation

Branch naming format:

<type>/<story-id>-<short-description>

Types: feature, bugfix, hotfix

Use lowercase and hyphens. Avoid long or vague branch names.


---

How should I write commit messages?

Each commit must start with the story ID and describe the change clearly.

Format:

<story-id>: <what the commit does, in imperative mood>

Examples:

SSB-123: Add provisioning plan for XYZ app

SSB-456: Fix null pointer in account aggregation


Avoid commits like misc fixes, final changes, or wip.


---

How do I keep my branch updated?

Before pushing or creating a PR, always rebase onto the latest dev:

git fetch origin
git rebase origin/dev

If conflicts occur:

git add <resolved-file>
git rebase --continue

Abort rebase if needed:

git rebase --abort


---

How do I raise a pull request?

1. Push your feature branch:



git push -u origin feature/SSB-123-add-xyz-app

2. Create a pull request (PR) from your branch to dev.


3. Use a descriptive title:



SSB-123: Add connector for XYZ application

4. Select "Squash and merge" during PR merge.


5. Delete the branch after merging.




---

What if I need to fix an issue in production?

Use a hotfix branch.

1. Create a branch from prod:



git checkout prod
git pull origin prod
git checkout -b hotfix/SSB-999-fix-login-bug

2. Make the fix and raise a PR to prod.


3. After merging, merge the hotfix into:

uat

sit

dev




This prevents code drift between environments.


---

What if I’m contributing during a release cycle?

Only leads or release managers can raise PRs to:

sit

uat

prod


Your responsibility ends with a clean merge into dev.


---

What checks should I complete before requesting a review?

[ ] Did I use the correct branch name format?

[ ] Is my commit message clear and valid?

[ ] Did I rebase on top of dev?

[ ] Did I test the changes locally?

[ ] Did I request a reviewer?

[ ] Did I use squash and merge?



---

Where can I read the full process?

Check the GitHub Wiki for detailed documentation:

Git Branching Strategy

Developer Guidelines



---

Who do I contact for help?

Please reach out to the IIQ DevOps team at iiq-dev@example.com.

---

Let me know if you want a downloadable `.md` version or want to include GitHub Actions or CI checks later.


