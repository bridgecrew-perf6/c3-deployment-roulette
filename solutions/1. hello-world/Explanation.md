### Step to reproduce the error and fix.
1. Deployed the app using the below command
```./initialize_k8s.sh
2. Described the pod using the below command and found out that It was in restarting state.
```kubectl describe pod hello-world-d696c5567-x5fdx
3. Checked the logs of pod and It was failing due to wrong health check URL.
```kubectl logs hello-world-d696c5567-x5fdx  
4. Fixed the url in the hello-world deployment
5. Redeployed the deployment
```kubectl apply -f starter/apps/hello-world/hello.yml
6. Boom, got fixed.