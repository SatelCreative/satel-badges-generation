# Satel Badges Generation

This centralized GitHub action created code coverage badges from xml reports

```yml 
  badges-generation:
    needs: [poetry-redoc]
    timeout-minutes: 15
    # Code coverage action doesn't run on self-hosted runner
    runs-on: ubuntu-latest
    environment: ${{ inputs.environment }}
    outputs:
      BADGES: ${{ steps.badges.outputs.BADGES }}
    steps:
      - name: Check out repository
        uses: actions/checkout@v4.1.1

      - name: Badges
        uses: SatelCreative/satel-badges-generation@1.0.0
        with:       
          app-name: ${{ inputs.app-name }}
          environment: ${{ inputs.environment }}  
```
