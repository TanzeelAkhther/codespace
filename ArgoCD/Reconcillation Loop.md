*Reconcillation function* tries to match the actual state of a k8s cluster to the desire state defined in Git.
A *Reconcillation loop* is how often your ArgoCD application will synchronize from the Git Repository.
The default *timeout_period* is set to three minutes. This value is configurabke and is used within the ArgoCD repo server.
**ArgoCD_repo_server** - is responsible to retrieve the desired straight from Gitrepo server and it has a timeout option called as the *application_reconcillation_timeout*.
