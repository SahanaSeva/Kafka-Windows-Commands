# Kafka-Windows-Commands

1. Run Kafka in Kraft mode

   ```$env:KAFKA_CLUSTER_ID = (& .\bin\windows\kafka-storage.bat random-uuid)```
 
   ```.\bin\windows\kafka-storage.bat format -t $env:KAFKA_CLUSTER_ID -c .\config\kraft\server.properties```
 
2. Start Kafka Server / Broker

    ```.\bin\windows\kafka-server-start.bat .\config\kraft\server.properties```

3. Create topic

    ```.\bin\windows\kafka-topics.bat --create --topic kafka-topic --bootstrap-server localhost:9092```

4. list out all topic names

    ```.\bin\windows\kafka-topics.bat --bootstrap-server localhost:9092 --list```

5. Describe topics
  
    ```.\bin\windows\kafka-topics.bat --bootstrap-server localhost:9092 --describe --topic kafka-topic```

6. Produce message

    ```.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic kafka-topic```


7. Consume message

    ```.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic kafka-topic --from-beginning```



