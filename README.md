
# Kubernetes Projects

# What we need

    1. Docker desktop for macOS M2
    2. Enable Kubernetes engine inside docker desktop
    3. Minicube for all other OS to manage VMs
    4. Kubectl is used to manage contianers inside VMs

[1. Running single Frontend Application Container in Pod](#single-container)


# single-container

To run single container inside Pod and expose it to outside world using kubernetes we need to create two types of objects (Pod and Service)/(Deployment and Service)

    1. Pod 
        - It's the smallest possible unit in kubernetes that we can deploy.
        - After creating pod object type we can only change image nothing else.
           - For example: in client-pod.yaml file we can only update the name of the image but
             if we try to change the port from 3000 to anything else it will throw an error. 
             To address this issue we need new object type that is deployment
    2. Service
        - Nodeport
            To expose the container to outside world.(Usually used for development purposes)
    3. Deployment
        - Deployment is used to maintain the set of identicle pods and it makes sure that 
          the configuration is correct and pods are always in runnable state and right number 
          of pods exists. so basically itmonitors the state of each pod and updates it when 
          necessary.


### Commands

To apply client-pod.yaml 

```cmd
kubectl apply -f <file-path>

kubectl apply -f client-pod.yaml
```

To apply client-node-port.yaml

```cmd
kubectl apply -f client-node-port.yaml
```
To apply client-deployment.yaml

```cmd
kubectl apply -f client-deployment.yaml
```

To get the information about the running objects. In this command we can also use service or any other object type.

```cmd
kubectl get Pods
```
To get detailed information about objects

```cmd
kubectl describe <object-type> <object-name>

kubectl describe pod client-pod
```

To delete the running object type
```cmd
kubectl delete -f <file-path>

kubectl delete -f client-pod.yaml
```

## Authors
- [@Dixit Patel](https://github.com/Dixit-Patel-1990/Docker)