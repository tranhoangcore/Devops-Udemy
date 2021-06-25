---

---

# Kubernetes for the Absolute Beginners - Hands-on

## 1. **Kubernetes Overview**

![Components of Kubernetes](https://d33wubrfki0l68.cloudfront.net/2475489eaf20163ec0f54ddc1d92aa8d4c87c96b/e7c81/images/docs/components-of-kubernetes.svg)

Container + Orchestration

### 1. Container Orchestration

> Container orchestration automates the deployment, management, scaling, and networking of containers. Enterprises that need to deploy and manage hundreds or thousands of Linux® containers and hosts can benefit from container orchestration.

<img src="https://miro.medium.com/max/2920/0*q2ezs3YFk6SvC9mr.png" alt="img" style="zoom:70%;" />

### 2. Kubernetes Architecture

#### Nodes (Minions)

#### Cluster

#### Master

#### Components

#### Master vs Worker Nodes

![Kubernetes architecture](https://startkubernetes.com/static/ed77ff8be09a6293d24b21f4dadc55d7/5a190/k8s-architecture.png)

## 2.  **Setup Kubernetes**

**Minikube**

![](https://images2.imgbox.com/f0/33/1R4LwO4f_o.png)

## 3. Kubernetes Concepts

### 1. POD

> In terms of Docker concepts, a Pod is similar to a group of Docker containers with shared namespaces and shared filesystem volumes.

### 2. Service

A Service enables network access to a set of Pods in Kubernetes.

### 3. Deployment

A deployment is responsible for keeping a set of pods running.

### 4.  **YAML Introduction**

> YAML is a human-readable data-serialization language. It is commonly used for configuration files and in applications where data is being stored or transmitted. YAML targets many of the same communications applications as Extensible Markup Language but has a minimal syntax which intentionally differs from SGML.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
      env:
        - name: POSTGRES_PASSWORD
          value: mysecretpassword
```

## 5. **Kubernetes Concepts - PODs, ReplicaSets,**
**Deployments**

### 1. PODS Deployments:

### 2. Replication Controllers and ReplicaSets

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
      - name: nginx
        image: nginx
  selector:
    matchLabels:
      app: myapp
```

### 3. Deployments

## 6. Networking in Kubernetes

## 7. **Services**

### 1. ClusterIP

A ClusterIP service is the default Kubernetes service. It gives you a service inside your cluster that other apps inside your cluster can access. There is no external access.

![img](https://miro.medium.com/max/765/1*I4j4xaaxsuchdvO66V3lAg.png)

### 2. NodePort

A NodePort service is the most primitive way to get external traffic directly to your service. NodePort, as the name implies, opens a specific port on all the Nodes (the VMs), and any traffic that is sent to this port is forwarded to the service.

![img](https://miro.medium.com/max/942/1*CdyUtG-8CfGu2oFC5s0KwA.png)

### 3. LoadBalancer

A LoadBalancer service is the standard way to expose a service to the internet. On GKE, this will spin up a Network Load Balancer that will give you a single IP address that will forward all traffic to your service.

![img](https://miro.medium.com/max/822/1*P-10bQg_1VheU9DRlvHBTQ.png)



### 4. Ingress

Unlike all the above examples, Ingress is actually NOT a type of service. Instead, it sits in front of multiple services and act as a “smart router” or entrypoint into your cluster.

You can do a lot of different things with an Ingress, and there are many types of Ingress controllers that have different capabilities.

The default GKE ingress controller will spin up a [HTTP(S) Load Balancer](https://cloud.google.com/compute/docs/load-balancing/http/) for you. This will let you do both path based and subdomain based routing to backend services. For example, you can send everything on foo.yourdomain.com to the foo service, and everything under the yourdomain.com/bar/ path to the bar service.


![img](https://miro.medium.com/max/1786/1*KIVa4hUVZxg-8Ncabo8pdg.png)





## 8. **Microservices Architecture**

### 1. Microservices Application

![img](https://microservices.io/i/Microservice_Architecture.png)8

## 2. Microservices Application on Kubernetes

## 9. **Kubernetes on Cloud**

### 1. Kubernetes on GCP (GKE)

### 2. Kubernetes on AWS (EKS)

### 3. Kubernetes on Azure (AKS)
