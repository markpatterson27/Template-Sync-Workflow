# Template Sync Workflow

Reusable workflow to sync changes from a template source repository.

## Usage

```yml
name: Sync from template source

on:
  push:
    branches:
    - '*'
    - '!source-template-updates'

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

jobs:
  sync:
    uses: markpatterson27/Template-Sync-Workflow/.github/workflows/template-sync.yml@main
    with:
      template-repo: <owner>/<tempate-repo>
      create-pr: true
      update-branch-name: source-template-updates
      update-strategy: merge
    secrets:
      workflowPAT: ${{ secrets.SYNC_TOKEN }}
      templatePAT: ${{ secrets.SYNC_TOKEN }}

```
