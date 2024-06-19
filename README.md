## ELK Stack Configuration for Cloudlab

This repository contains the Docker Compose and configuration files used to set up an Elastic Stack (ELK) on a Google Cloud instance for log analysis. It is specifically tailored to handle and analyze logs from network devices and servers, making it ideal for monitoring and security analysis in large-scale deployments.

### Components

- **Elasticsearch**: Acts as the heart of the stack, providing powerful search capabilities.
- **Logstash**: Processes incoming logs and feeds them into Elasticsearch.
- **Kibana**: Provides visualization capabilities for data stored in Elasticsearch.

### Additional Components on premise
- **Filebeat**: Lightweight shipper for forwarding and centralizing log data from local systems to the ELK stack on the cloud.
- **Suricata**: Network security monitoring tool configured to forward logs to the ELK stack on the cloud.

### Directory Structure

```
elk/
│
├── docker-compose.yml        # Defines services, networks, and volumes for the ELK stack
├── logstash.conf             # Configuration for Logstash processing
├── instances.yml             # Instance configuration for Elasticsearch
├── filebeat.yml              # Filebeat configuration for log forwarding (located on prem)
└── suricata.yaml             # Suricata configuration for network monitoring (located on prem)
```

### Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/cultimedia/elkstack.git
   cd elkstack
   ```

2. **Set up environment variables:**
   - Rename `.env.example` to `.env`.
   - Update the `.env` file with your specific settings.

3. **Start the services:**
   ```bash
   docker-compose up -d
   ```

4. **Access Kibana:**
   - Open your web browser and navigate to `http://[your-cloud-ip]:5601`.

### Security

For security reasons, sensitive files like `ca.crt` and `.env` containing credentials and private keys are not included in this repository. Ensure these files are securely managed and not exposed publicly.

### Contribution

Contributions to this project are welcome. Please fork the repository and submit a pull request.

---

**Notes:**
- Adjust the paths and specifics to match your actual deployment and environmental setup.
- Include additional instructions or configurations relevant to your setup if necessary.
