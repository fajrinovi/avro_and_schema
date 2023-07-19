# Kafka: Schema Registry and Avro

## Prerequisites
1. Apache Kafka
2. Confluent: `pip3 install confluent-kafka`
3. Avro: `pip3 install avro-python3`
4. Docker

## Steps
### 1. Avro
1. Create Kafka stacks with Docker Compose.
   ```
   docker-compose up -d
   ```
2. Run `pip install -r requirements.txt` in the terminal or CMD
3. Run `python playground.py` in the terminal or CMD

   This is the result:
   
   ![1](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/c6bdca1f-f996-43ea-98d0-29249f99603c)
   
5. There should be one file generated: `users.avro`
   
   ![2](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/6ed12b9a-e3b4-4f79-8cce-a7b4302cdf98)

### 2. Schema Registry
1. Create an avro schema for key and values.
2. Develop producer and consumer.
3. Run the producer to stream the data into the Kafka topic (make sure to run in the directory that stored the file).
   ```
   python producer.py
   ```
   If the producer manages to produce the data, it will look like this in the terminal:
   
   ![5](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/29d80fa9-d8ee-4e28-a73a-11431c4a6682)
   
9. Run a consumer to ingest data from Kafka topics and load it into BigQuery.
   ```
   python consumer.py
   ```
   If the consumer manages to poll the data, it will look like this in the terminal:

   ![6](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/d8ca5f0b-0035-4115-b980-f608bf3e5354)

5. Open Confluent Control Center to monitor topic, schema registry, and message.
   - Topic:
     
   ![7](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/529c96aa-0bc7-4807-89e0-1290907658df)

   - Schema:
     
   ![key](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/d3a7340f-b590-4e93-a875-92d4a88ad90b)

   ![value](https://github.com/fajrinovi/kafka_avro_and_schema/assets/57751463/1c67fa2c-ba23-4a4f-824b-3fd6ea885db4)


   
