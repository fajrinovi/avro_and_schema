# Kafka: Schema Registry and Avro

## Prerequisites
1. Apache Kafka
2. Confluent: `pip3 install confluent-kafka`
3. Avro: `pip3 install avro-python3`
4. Docker

## Steps
1. Create Kafka stacks with Docker Compose.
   ```
   docker-compose up -d
   ```
2. Create an avro schema for key and values.
3. Develop producer and consumer.
4. Run the producer to stream the data into the Kafka topic (make sure to run in the directory that stored the file).
   ```
   python producer.py
   ```
   If the producer manages to produce the data, it will look like this in the terminal:
   <details>
   <summary>Open to see the image.</summary>
   <img width="1221" alt="Producer" src="https://user-images.githubusercontent.com/113230789/228303562-70815df4-1f81-4a25-9d92-4c53c470859a.png">
   </details>
5. Run a consumer to ingest data from Kafka topics and load it into BigQuery.
   ```
   python consumer.py
   ```
   If the consumer manages to poll the data, it will look like this in the terminal:
   <details>
   <summary>Open to see the image.</summary>
   <img width="1221" alt="Consumer" src="https://user-images.githubusercontent.com/113230789/228303881-23d78400-4941-4de5-8c91-5c2a37ae871c.png">
   </details>
5. Open Confluent Control Center to monitor topic, schema registry, and message.
   <details>
   <summary>Topic.</summary>
   <img width="1440" alt="Screenshot 2023-03-28 at 14 22 17" src="https://user-images.githubusercontent.com/113230789/228308343-58d9c462-a0d0-4cf8-8eba-4b5b8e30a211.png">
   </details>
   <details>
   <summary>Schema.</summary>
   <img width="1440" alt="Screenshot 2023-03-28 at 14 21 07" src="https://user-images.githubusercontent.com/113230789/228308399-aaefc663-e9e5-4d55-9976-ebd8beb94815.png">
   <img width="1440" alt="Screenshot 2023-03-28 at 14 24 04" src="https://user-images.githubusercontent.com/113230789/228308656-e61635cd-d33b-44b3-b564-bdaeb05846c1.png">
   </details>
   <details>
   <summary>Messages.</summary>
   <img width="1440" alt="Screenshot 2023-03-28 at 14 23 49" src="https://user-images.githubusercontent.com/113230789/228308445-45745cc1-5b3e-449a-bcff-9e0c885a50de.png">
   </details>
6. Check the data that has been loaded in BigQuery.
   - Ensure the number of data rows loaded equals the number of rows in the data source.
     <details>
     <summary>Open to see the image.</summary>
     <img width="1440" alt="Screenshot 2023-03-28 at 23 24 48" src="https://user-images.githubusercontent.com/113230789/228309875-ce7db8b2-b691-40e1-83c4-553ec445f99d.png">
     </details>
   - Make sure the contents of the data that has been loaded into BigQuery are correct.
     <details>
     <summary>Open to see the image.</summary>
     <img width="1377" alt="Data in Bigquery" src="https://user-images.githubusercontent.com/113230789/228307253-9fb1d993-9eb5-4009-82c3-dcf329e4d743.png">
     </details>
