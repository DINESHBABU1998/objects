# objects
Topic: Kubernetes Object Model

The Kubernetes Platform contains control over the resources related to Storage and Compute

There are five types of Object model:
1] Namespace
2] POD
3] Replicaset
4] Deployment
5] Service

NameSpace:
   1]  Namespace is like a package name, Logical partionaning of the kubernities cluster is said to be Namespace.
2] Namespaces are a way to organize clusters into virtual sub-clusters
3] Any resource that exists within Kubernetes exists either in the default namespace or a namespace that is created by the cluster operator
4] Namespaces provide a scope for names. Names of resources need to be unique within a namespace, but not across namespaces.
5] Namespaces cannot be nested inside one another and each Kubernetes resource can only be in one namespace.
6] To create namespace ,  my-namespace.yaml
7] To Run namespace - kubectl create -f ./my-namespace.yaml

8] To list the namespace in Cluster we should use below command 
         kubectl get namespaces
9] To delete Namespace - kubectl delete namespaces <insert-some-namespace-name>

10] Attaching the link for my reference - https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/

PODS
1] Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.
2] A Pod is a group of one or more containers, with shared storage and network resources, and a specification for how to run the containers.
3] A Pod is similar to a set of containers with shared namespaces and shared filesystem volumes
4] To Create a POD , kubectl apply -f https://k8s.io/examples/pods/simple-pod.yaml

5] Link for reference - https://kubernetes.io/docs/concepts/workloads/pods/



Replica Set
1] A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time.
2] Commands which are listed to operate on Replica set
https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/

Deployment
1] A Deployment provides declarative updates for Pods and ReplicaSets.
2] We can create a deployment by using following command , kubectl apply -f https://k8s.io/examples/controllers/nginx-deployment.yaml
3] To check if the deployed or not , use the below command kubectl get deployments
4] To get deployment roll out status- kubectl rollout status deployment/nginx-deployment
5] Attaching the link which includes all the command and also the commands if we get any error,
https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
   
   
Services:
Services provide a way to expose applications running in pods. Their purpose is to represent a set of pods that perform the same function and set the policy for accessing those pods.
Although pod failure is an expected event in a cluster, Kubernetes replaces the failed pod with a replica with a different IP address. This creates problems in communication between pods that depend on each other.
Using the kube-proxy process that runs on each cluster node, Kubernetes maps the service's virtual IP address to pod IP addresses. This process allows for easier internal networking but also enables exposing of the deployment to external networks via techniques such as load balancing.
