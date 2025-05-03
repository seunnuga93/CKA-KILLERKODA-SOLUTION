## Run the below command

CREATE SERVICE ACCOUNT
```
kubectl create sa app-account

```

CREATE CLUSTERROLE
```
kubectl create clusterrole app-role-cka --verb=get --resource=pods

```

CREATE CLUSTERROLEBINDING
```
kubectl create clusterrolebinding app-role-binding-cka \
  --clusterrole=app-role-cka \
  --serviceaccount=default:app-account
```
