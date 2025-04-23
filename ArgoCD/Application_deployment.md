**Create an app from a Git repository**
```
argocd app create guestbook \
	--repo https://github.com/argoproj/argocd-example-apps.git \
	--path guestbook \
	--dest-namespace demo-guestbook \
	--dest-server https://kubernetes.default.svc \
	--directory-recurse
```
**List all the applications.**
```
  argocd app list
```
**Get the details of a application**
```
  argocd app get my-app
```

**Manually sync an application**
```
 argocd app sync <app_name>
argocd app sync app1 app2    #Multiple application at once
```


**List out all application**
```
argocd app list
```
