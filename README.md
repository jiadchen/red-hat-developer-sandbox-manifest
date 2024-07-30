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

sandboxの制約としてpodを50個に達していると、podの作成ができなくなるので、podの削除が必要です。  
Completedの状態のPodを全部削除するコマンド  
`oc get pods -n jiadchen-dev --field-selector=status.phase=Succeeded -o jsonpath='{.items[*].metadata.name}' | xargs -r oc delete pod -n jiadchen-dev`

すべてのpipelinerunを削除するコマンド  
`oc delete pipelinerun --all -n jiadchen-dev`