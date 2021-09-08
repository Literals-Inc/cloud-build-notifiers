SOPS usage instructions
===

Encryption:

```
cd cloud-build-notifiers
export LITERAL_ENV=development ; lt-secrets encrypt -f "--encrypted-regex '^(value)$'" "slack/slack.${LITERAL_ENV}.yaml" -s
export LITERAL_ENV=staging     ; lt-secrets encrypt -f "--encrypted-regex '^(value)$'" "slack/slack.${LITERAL_ENV}.yaml" -s
export LITERAL_ENV=production  ; lt-secrets encrypt -f "--encrypted-regex '^(value)$'" "slack/slack.${LITERAL_ENV}.yaml" -s
```

Decryption:

```
export LITERAL_ENV=development ; lt-secrets decrypt "slack/slack.${LITERAL_ENV}.yaml.enc"
export LITERAL_ENV=staging     ; lt-secrets decrypt "slack/slack.${LITERAL_ENV}.yaml.enc"
export LITERAL_ENV=production  ; lt-secrets decrypt "slack/slack.${LITERAL_ENV}.yaml.enc"
```
