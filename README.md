# Satel Badges Generation



```yml 
  badges-generation:
    needs: [poetry-redoc]
    timeout-minutes: 15
    runs-on: ubuntu-latest #${{ contains(needs.self-hosted-status.outputs.runner-status, 'online') && 'self-hosted' || 'ubuntu-latest' }}
    environment: ${{ inputs.environment }}
    steps:
      - name: Check out repository
        uses: actions/checkout@v4.1.1

      - name: Badges
        uses: SatelCreative/satel-badges-generation@1.0.0
        with:       
          app-name: ${{ inputs.app-name }}
          environment: ${{ inputs.environment }}
          work-dir: ${{ inputs.work-dir }}    
```
