# **Ericsson PNSI Challenge**

## Administered May 27 2022

### Completed by Ian Holmes

__

## ***Running the Project***

### ***Prerquisites***

- Have a running Kubernetes cluster
- Clone this repo and navigate to the root folder
- For option 2: have helm installed

### **Option 1: yaml**

Step 1: run the following command

```shell
kubectl apply -f .\yaml\hello-app.yml
```

Step 2: run the following command

```shell
kubectl apply -f .\yaml\hello-app-svc.yml
```

Step 3: View your new deployment and service with the following command

```shell
kubectl get all
```

### **Option 2: helm**

Step 1: run the following command

```shell
helm install test .\helm\hello-app-helm-0.1.0.tgz
```

Step 2: View your new deployment and service with the following command

```shell
kubectl get all
```

### ***Testing With Curl***

To verify the service has been successfully exposed, run the following command, where `<EXTERNAL-IP>` is the External IP value for the hello-app service

```shell
curl http://<EXTERNAL-IP>
```

This should return a result similar to the following (there may be additional info such as status code etc.)

```shell
Hello, world!
Version: 2.0.0
Hostname: hello-app-deployment-helm-85fdc74868-s8rmp
```

*The service can also be verified by opening a new browser tab navigating to `http://<EXTERNAL-IP>`*
