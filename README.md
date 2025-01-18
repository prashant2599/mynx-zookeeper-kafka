<h1>Zookeeper-kafak-Task-Deployment</h1>

<h2>Deployment-Instruction</h2>

### Step 1: Package the Helm Chart

```bash
helm package .
```

### steP 2: Install the helm Chart 

```bash
helm install zookeeper-kafka zookeeper-kafka.tgz
```

## Verify the kafka Cluster is functional

### step 3: Access the kafka

```bash
kubectl exec -it kafka-0 -n kafka -- /bin/bash
```
