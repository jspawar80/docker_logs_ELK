# docker_logs_ELK


1. **Clone this repository**

2. Change the ownership of the `filebeat.yml` file to root:

   ```bash
   sudo chown root:root filebeat.yml
   ```

3. Adjust the file permissions so that only the owner (root in this case) can write to it:

   ```bash
   sudo chmod go-w filebeat.yml
   ```

This will change the permissions of the file to `-rw-r--r--`.

4. **Start Services with Docker Compose**

    If you're using Docker Compose, you can start Elasticsearch, Kibana, and optionally Logstash by running:

    ```bash
    docker-compose up -d
    ```
5. Random Log generator

```
docker run -d --name log-generator chentex/random-logger:latest
```
6. **Access Kibana**

    Open your web browser and navigate to `http://localhost:5601` to access Kibana.

Here are the steps to set up an index pattern for `logstash-*` in Kibana:

### Step 1: Access Kibana

Open your web browser and navigate to your Kibana instance. The URL is usually `http://localhost:5601` if you're running it locally.

### Step 2: Navigate to "Stack Management"

Once Kibana is open, look for the "Stack Management" option in the left-hand sidebar and click on it.

### Step 3: Define Index Pattern

In the "Index pattern name" field, type `logstash-*` to match all indices that have names starting with `logstash-`.

### Step 4: Configure Settings

- **Time Filter**: If your Logstash indices contain time-based events, you'll want to choose a time field for your index pattern. This is often `@timestamp`, which is a commonly used field for time-based logs.
  
Click "Next Step" after configuring these settings.



