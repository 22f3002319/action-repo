# Action Repository

This is a dummy GitHub repository used solely for triggering GitHub webhook events (push, pull request, merge) to test the webhook receiver system.

## Purpose

This repository exists to:
- Trigger **PUSH** events by making commits and pushes
- Trigger **PULL_REQUEST** events by creating pull requests
- Trigger **MERGE** events by merging pull requests

## Repository Structure

```
action-repo/
├── README.md
├── sample-file.txt
└── .gitignore
```

## Usage

### 1. Clone and Setup

```bash
git clone <your-action-repo-url>
cd action-repo
```

### 2. Trigger PUSH Events

Make changes and push to any branch:

```bash
# Make a change
echo "New content" >> sample-file.txt

# Commit and push
git add .
git commit -m "Test push event"
git push origin main
```

### 3. Trigger PULL_REQUEST Events

Create a new branch and open a pull request:

```bash
# Create a new branch
git checkout -b feature/test-pr

# Make changes
echo "PR changes" >> sample-file.txt
git add .
git commit -m "Test PR event"

# Push the branch
git push origin feature/test-pr
```

Then go to GitHub and create a pull request from `feature/test-pr` to `main`.

### 4. Trigger MERGE Events

After creating a pull request, merge it through GitHub's web interface. This will trigger a MERGE event.

## Testing Checklist

- [ ] Push to main branch
- [ ] Push to feature branch
- [ ] Create pull request
- [ ] Merge pull request
- [ ] Verify events appear in webhook-repo UI

## Notes

- This repository can be minimal - it only needs to exist to trigger webhooks
- You can add any files you want for testing
- The repository doesn't need to have any actual functionality
