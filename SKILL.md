---
name: splitwise
description: Create and manage expenses on Splitwise. Use this skill when the user wants to log a new expense, split a bill, or check their Splitwise balance.
---

# Splitwise Skill

This skill allows an agent to interact with the Splitwise API to automate shared expenses.

## Requirements

- `SPLITWISE_API_KEY`: A Long-lived User Token obtained from the [Splitwise Developer Console](https://secure.splitwise.com/apps).

## Usage

### Logging an Expense
The primary script handles creating a 50/50 split between two users.

```bash
python3 {baseDir}/scripts/add_expense.py \
  --cost "10.00" \
  --desc "Lunch" \
  --payer_id "12345" \
  --other_id "67890" \
  --via "agent-name"
```

### Parameters
- `--cost`: Total amount (e.g., "45.00")
- `--desc`: Brief description of the expense.
- `--payer_id`: The Splitwise User ID of the person who paid.
- `--other_id`: The Splitwise User ID of the person being split with.
- `--group_id`: (Optional) The ID of a specific Splitwise group.
- `--via`: (Optional) Appends "(via name)" to the description.

## Setup for Agents
1. Create a Splitwise App at `https://secure.splitwise.com/apps`.
2. Generate a "Long-lived User Token".
3. Store it as `SPLITWISE_API_KEY`.
4. Use the API to find your User IDs and Group IDs.
