# update-submodules-action

GitHub action for updating references to submodules in parent repo

## Workflow

```yml
on:
  push:
    branches:    
      - dev
      - staging
      - release

jobs:
  update-parent:
    runs-on: ubuntu-latest
    steps:
      - name: Update parent
        uses: eco-trip/update-submodules-action@v1.0
        with:
          parent: eco-trip/Ecotrip
          submodules: App, Api, CP
          token: ${{ secrets.MEBBOT }}
          commit_message: "chore: Update Api [skip ci]"
```
