```
oc create secret generic git-credentials \
  --from-literal=username=<username> \
  --from-literal=token=<token>
```
`<username>`と`<token>`をあなたのGitHubアカウントの情報に置き換えてください。