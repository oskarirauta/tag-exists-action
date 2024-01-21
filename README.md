# tag-exists-action
Action for checking if tag exists in repository

### usage

```
name: test if tag exists

on:
  workflow_dispatch:
    inputs:
      tagname:
        description: "tag name"
        required: true

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Check out code
        uses: actions/checkout@v3
      - name: test if tag exists
        uses: ./
        with:
          tag: ${{ inputs.tagname }}
      - name: show result
        shell: bash
        run: |
          echo "tag ${{ inputs.tagname }} exists: ${{ env.tag_exists }}"
```
