### oc commandのインストール

### oc login
https://oauth-openshift.apps.sandbox-m2.ll9k.p1.openshiftapps.com/oauth/token/display  
Log in with this token の下に表示されているコマンドを実行してください。

```
oc create secret generic git-credentials \
  --from-literal=username=<username> \
  --from-literal=token=<token>
```
`<username>`と`<token>`をあなたのGitHubアカウントの情報に置き換えてください。