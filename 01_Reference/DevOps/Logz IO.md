---
tags:
  - devops
  - logging
  - monitoring
  - cloud
  - elk
  - logz-io
---
# Logz IO

> [!INFO]
> **Logz.io** is a scalable, cloud-native observability platform based on the **ELK Stack** (Elasticsearch, Logstash, Kibana) and Grafana. It provides log management, infrastructure monitoring, and security analytics as a service.

**Related Notes:**
- [[Kubernetes]] – integrating Logz.io agent (DaemonSet) for cluster monitoring.
- [[Docker]] – shipping container logs to Logz.io.
- [[AWS]] – monitoring AWS infrastructure and services (e.g., S3, CloudWatch).

---

## 🚀 Getting Started

To start using Logz.io, you typically need to retrieve your **Listener Host** and **Account Token** from the settings page.

1. **Sign up/Login** to the Logz.io console.
2. Navigate to **Settings > Manage > General** to find your *Token*.
3. Identify the correct **Listener URL** for your region (e.g., `listener.logz.io` or `listener-eu.logz.io`).

## 📦 Shipping Logs

You can ship logs using various methods. The most common for servers is **Filebeat**.

### Filebeat Configuration (`filebeat.yml`)
```yaml
filebeat.inputs:
- type: log
  paths:
    - /var/log/*.log
  fields:
    logzio_codec: json
    token: "<YOUR_LOGZ_IO_TOKEN>"
    type: "syslog"
  fields_under_root: true
  encoding: utf-8
  ignore_older: 3h

output.logstash:
  hosts: ["listener.logz.io:5015"]
  ssl.certificate_authorities: ["/etc/pki/tls/certs/COMODORSADomainValidationSecureServerCA.crt"]
```

## 🔍 Kibana Querying

Logz.io uses **Kibana** for visualization and querying.

- **Basic Search**: Enter plain text to search all fields (e.g., `error`).
- **Field Search**: `log_level:ERROR` or `status:500`.
- **Boolean Logic**: `env:production AND (status:404 OR status:500)`.
- **Wildcards**: `service_name:auth*`.

### Common Filters
- `type`: filter by log type (e.g., `nginx`, `syslog`).
- `kubernetes.namespace_name`: filter by K8s namespace.
- `tags`: filter by specific tags added during shipping.
