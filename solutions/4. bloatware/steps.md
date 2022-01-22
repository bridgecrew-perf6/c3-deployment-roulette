## Steps:
1. Deployed the bloatware service
`kubectl apply -f bloatware.yml `
2. Checked the pods status and found out that pods are in pending status due to un-sufficient nodes available to schedule all the pods
`kubectl get pods`
3. Added the OIDC provider
```
eksctl utils associate-iam-oidc-provider \
--cluster udacity-cluster \
--approve \
--region=us-east-2
```
4. created cluster service account with IAM permissions
```
eksctl utils associate-iam-oidc-provider \
--cluster udacity-cluster \
--approve \
--region=us-east-2 --profile=udacity
```
5. Added the cluster-autoscaler.yaml file and applied it to the kube-system namespace.
`kubectl apply -f cluster-autoscaler.yaml -n kube-system`
6. Redeployed the bloatware 
`kubectl apply -f bloatware.yml `
7. New nodes came up and the all pods got scheduled.