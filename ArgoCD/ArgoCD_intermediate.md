*Reconcillation function* tries to match the actual state of a k8s cluster to the desire state defined in Git.

A *Reconcillation loop* is how often your ArgoCD application will synchronize from the Git Repository.

The default *timeout_period* is set to three minutes. This value is configurabke and is used within the ArgoCD repo server.

**ArgoCD_repo_server** - is responsible to retrieve the desired straight from Gitrepo server and it has a timeout option called as the *application_reconcillation_timeout*.

The *API_Server* can be set up to receive webhook events in order to remove the polling delay.

Within our Git Provider, we can create the *webhook* by defining the ArgoCD server instance endpoint append with */api/webhook.*

Once the webhook is created, for every push event to to Git repository, the *webhook is going to send the events to the ArgoCD server*, and ArgoCD repo server will in turn pull the committed changes.
*By using webhook we can remove the polling delay*

ArgoCD continuously pulls Git repositories for any new changes an at the same time it will continuously check the status of kubernetes resources.

**Various Resource Health Checks**
1. Healthy status - used when all the resources are 100% healthy.
2. Progressing status - used if a resource is unhealthy but could still be healthy if given time
3. Degraded status - used if a resource status indicates a failure or an inability to reach a healthy state in a timely manner.
4. Missing status - used if resource is not present in the cluster.
5. Suspended status - used if a resources is suspended or paused, typical example is a paused deployment.
6. Unknown status - Health assessment failed and actual health status is unknown.

For *Kubernetes_secrets* it will determine whether the service is of type load balancer, and verifies that the *loadbalancer.ingress_list* is not empty and that the *hostname* or *IP* has at least one value.



