# docker_logs_ELK

1. Change the ownership of the `filebeat.yml` file to root:

   ```bash
   sudo chown root:root filebeat.yml
   ```

2. Adjust the file permissions so that only the owner (root in this case) can write to it:

   ```bash
   sudo chmod go-w filebeat.yml
   ```

This will change the permissions of the file to `-rw-r--r--`.

3. Restart the Filebeat container:

   ```bash
   docker-compose restart filebeat
   ```
4. Random Log generator

```
docker run -d chentex/random-logger:latest
```
