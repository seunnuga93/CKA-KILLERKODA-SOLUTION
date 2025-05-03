# Set the context (already given)
kubectl config use-context kubernetes-admin@kubernetes

# Step 1: Create the ServiceAccount
kubectl create sa app-account -n default

# Step 2: Create a Role (not ClusterRole) that allows get on pods
kubectl create role app-role-cka \
  --verb=get \
  --resource=pods \
  -n default

# Step 3: Create a RoleBinding (not ClusterRoleBinding)
kubectl create rolebinding app-role-binding-cka \
  --role=app-role-cka \
  --serviceaccount=default:app-account \
  -n default
