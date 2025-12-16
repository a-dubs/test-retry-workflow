# Test Retry Workflow

This repository tests the GitHub Actions retry mechanism for flaky build errors.

## What This Tests

The workflow randomly (50/50 chance) outputs either:
- **Flaky error**: The specific error pattern we're looking for → triggers retry → should succeed
- **Different error**: A non-matching error → no retry → should fail

Run the workflow multiple times to see both scenarios in action!

## How to Use

1. Create a GitHub repository (see instructions below)
2. Push this code to GitHub
3. Go to Actions tab → Run workflow manually
4. Run it multiple times to see both success and failure scenarios

## Expected Behavior

| Scenario | Result |
|----------|--------|
| Flaky error detected → Retry succeeds | ✅ Job passes |
| Different error → No retry | ❌ Job fails (expected) |

