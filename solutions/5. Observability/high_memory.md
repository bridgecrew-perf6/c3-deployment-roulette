## Steps:
1. Installed the Observability Matrix
`kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/download/v0.4.2/components.yaml`
2. Checked the hight CPU using the below command and found out that **hello-world** pod is using the max memory.
`kubectl top pod`
3. Deleted the hello-world deployment