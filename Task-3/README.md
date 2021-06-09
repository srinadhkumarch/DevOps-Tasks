Below are the commands to install BotKube controller in Kubernets cluster.
BotKube is existing controller to communite Kubernets with Slack.

kubectl create ns botkube
helm repo add infracloudio https://infracloudio.github.io/charts
helm install --version v0.12.1 botkube --namespace botkube \
  --set communications.slack.enabled=true \
  --set communications.slack.channel=kube-slack \
  --set communications.slack.token=xoxb-901855467383-2176534487632-DPrbmga1QIStmglmHKRqjFNu \
  --set config.settings.clustername=EKS-Prod-Cluster \
  --set config.settings.kubectl.enabled=true \
  --set image.repository=infracloudio/botkube \
  --set image.tag=v0.12.1 \
  -f config.yaml \
  infracloudio/botkube

----

manifest.yaml is sample deployment to verity BotKube is notification to Slack