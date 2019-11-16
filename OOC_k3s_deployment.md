#  Open Open City k3s Deployment

You may find useful information here when preparing your deployment of your 
application to Open Open City's k3s cluster.

You need the following files:

* ```<project>_service.yml```
* ```<project>_deployment.yml```

<project> is the name of your __Junction 2019__ project that you have submitted.

__IMPORTANT__

Please come and talk to us when your app is ready. We will help you with the 
deployment, if needed. :)

## ```<project>_service.yml```

__IMPORTANT__

Please pick a Nodeport from the range: __32100-32200__

Currently assigned Nodeports in our cluster are: 

 * flowify 32100

```
---
apiVersion: v1
kind: Service
metadata:
  labels:
    app: <project>
    component: <project>
  name: <project>
  namespace: <project>
spec:
  type: NodePort
  ports:
    - port: xxxx          THE PORT YOUR CONTAINER EXPOSES e.g. 8080
      protocol: TCP
      targetPort: xxxx    THE PORT YOUR CONTAINER EXPOSES e.g. 8080
      nodePort: xxxxx     PICK ONE FROM THIS RANGE <32100-32200>
  selector:
    app: <project>
```

## ```<project>_deployment.yml```

Your applications can be deployed on either a RPi 4B+ node, or RPi 3B+ nodes.
The RPi 4B+ runs a 32 bit OS, while the 3B+ nodes run 64bit OpenSUSE Tumbleweed.

Please keep that info in mind and prepare your container image accordingly. 
Also state the correct __nodeSelector__ value in the deployment file.

We currently have support for the following nodeSelector values:

* RPi 4B+: kubernetes.io/arch: arm

* RPi 3B+: kubernetes.io/arch: arm64

Tip: 

to ease your work we recommend to pick a suitable base container image 
from a well know container registry and modify it to suit your needs.

```
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: project>i
  labels:
    app: <project>
  namespace: <project>
spec:
  replicas: 1
  selector:
    matchLabels:
      app: <project>
  template:
    metadata:
      labels:
        app: <project>
    spec:
      hostNetwork: true
      containers:
      - name: <project>
        image: <your image>
        ports:
        - containerPort: xxxxx      THE PORT YOUR CONTAINER EXPOSES e.g. 8080
        securityContext:
          privileged: true
          #hostNetwork: true
      nodeSelector:
        kubernetes.io/arch: arm
```


