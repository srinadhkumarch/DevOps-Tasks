https://github.com/srinadh-lanistar/golang-repo

operator-sdk new slack-operator --type go --repo github.com/srinadh-lanistar/golang-repo

1. Let’s first install the operator sdk
go get -d github.com/operator-framework/operator-sdk
cd $GOPATH/src/github.com/operator-framework/operator-sdk
git checkout master
make dep
make install

operator-sdk create slack-operator --api-version=v1alpha1 --kind=Slack --type=helm \ --helm-chart=slack --helm-chart-repo=https://akash-gautam.github.io/helmcharts/

operator-sdk create api slack-controller

xoxb-901855467383-2176534487632-DPrbmga1QIStmglmHKRqjFNu

-----------------

operator-sdk create slack-operator --type=helm --helm-chart stable/slack


https://lanistar.slack.com/archives/D024VB6PW0H
@BotKube
helm upgrade --version v0.12.1 botkube --namespace botkube \
  --set communications.slack.enabled=true \
  --set communications.slack.channel=kube-slack \
  --set communications.slack.token=xoxb-901855467383-2176534487632-DPrbmga1QIStmglmHKRqjFNu \
  --set config.settings.clustername=EKS-Prod-Cluster \
  --set config.settings.kubectl.enabled=true \
  --set image.repository=infracloudio/botkube \
  --set image.tag=v0.12.1 \
  -f sample-res-config.yaml \
  infracloudio/botkube



  ------------------------
  helm repo add slack-helm 
  helm create slack-helm
  helm install slack-helm slack-helm/ --namespace kube-system
  helm install my-cherry-chart buildachart/ --values buildachart/values.yaml