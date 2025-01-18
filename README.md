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
### step 4: Now, Produca a message to a kafka-topic

```bash
kafka-console-producer.sh --broker-list kafka-0:9092 --topic mynx-test-topic
```
### Step 5: Once a prompt open and type the message
```bash
> Hello Mynx-Test
> This is the Zookeeper-kafka-Task
```
### step 6: Now, Consume the message from kafka-topic
```bash
kafka-console-consumer.sh --bootstrap-server kafka-0.kafka.kafka.svc.cluster.local:9092 --topic mynx-test-topic --from-beginning
```

### Now, Helm Commands for upgradinng, Installing and uninstalling the chart,

'''bash
# upgrading the helm chart
helm upgrade --install <chart_name> <chart_name>.tgz 

# uninstalling the helm chart
helm uninstall <chart_name>
```