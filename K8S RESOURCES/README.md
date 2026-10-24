# Namespaces

<h1>Namespaces Defination</h1> An isolated envornment for resources which can be seen only at that namespaces 
isolated and separated from other namespaces. File and Directories are nogt affected by this it can be seen 
in cluster only resources get isolates which can only seen by specifyimg the particular namespaces.

<h1>namesapces Creation</h1>

    kubectl create ns (namespaces name)
    or
    kubectl create ns (namespaces name)
    
<h1>To check Created Namespaces</h1>

     kubectl get namespaces
     or 
     kubectl get ns

<h1>Imperitive 
<br>
<h1>Creating Resource In Namespace</h1>

    kubectl apply -f (name of yaml file) -n (name of namespace) 

-n (name of namespace) : can be used everywhere 
<br>

  Example:

         kubectl get pods -n (name of namespace)
         kubectl run (name of pod) --image=(image name nginx) -n (name of namespace
         kubectl logs (Resource) -n (name of namespace)
<h1>Declarative
<br>
<h1>Strecutre of YAML</h1>

    apiversion:
    kind:
    metadata:
      name:
      namespace:

In yaml apiversion, kind, metadata is default to create any resource in namespace put the namespace in metadata section 

<h1>To Set Any Namespace As Default Namespace & Switch Namespace Quickly</h1>

    kubectl config set-context --current --namespace=(name of namespace)

<h1>To See Current Working Namespace</h1>

    kubectl config view --minify | grep namespace 
    or
    kubectl config current-context
    
<h1>To See All Resources In Different Namespaces</h1>

    kubectl get all --all -namespace 

<h1>Delete Namespace</h1>

    kubectl delete ns (name of namespace)

<h1>Watch Resources Live</h1>

    kubectl get pods -n dev -w

<h1>List Resources Supported in Namespace</h1>

    kubectl api-resources --namespaced=true

  Cluster-wide resources:

    kubectl api-resources --namespaced=false

      
              
