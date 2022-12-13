# Notes for Google Cloud Certificated Cloud Architect

Following are the 7 operation services:
```
1. Monitoring - Monitoring agent collect CPU, Network and Process metrics. This creates alerts as well. We can also configure monitoring
agents for third party apps.
2. Debugger - Troubleshoot production application code issues.
3. Logging - Logs from Services, has query capability. Use router sink to send logs to GCS, Pub/Sub or BigQuery
5. Profiler - monitor production for memory leak, reduce cost and code performance.
6. Trace - Troubleshoot latency issues
7. Error reporting - Send notification when error occurs from log files.
```

> - Stackdriver /GoogldCloud Logging provides you with the ability to filter, search, and view logs from your cloud and open source application services. Allows you to define metrics based on log contents that are incorporated into dashboards and alerts. Enables you to export logs to BigQuery, Google Cloud Storage, and Pub/Sub.
> - [Reference](https://cloud.google.com/stackdriver/)


### About health Check ###
For a health check on http (port 80) you don't need to configure nothing in the server.
If the resource you are checking isn't publicly available, you must configure the resource's firewall to permit incoming traffic from the uptime-check servers. See Getting IP addresses to download a list of the IP addresses. If the resource you are checking doesn't have an external IP address, uptime checks are unable to reach it.

### NoSQL
NoSQL is well for:
✑ Developers are working with applications that create massive volumes of new, rapidly changing data types ג€" structured, semi-structured, unstructured and polymorphic data.

### Cloud Dataflow
Cloud Dataflow is a fully-managed service for transforming and enriching data in stream (real time) and batch (historical) modes with equal reliability and expressiveness -- no more complex workarounds or compromises needed.

### BigQuery
BigQuery is designed for large-scale processing of tabular data, for OLAP.
Tables can be time-partitioned and set to be expired at n days
JobUser can only grant in Project level while DataView can run query job.


### Cloud SQL:
- To reduce no. of queries, set the memcache service level to dedicated. Create a key from the hash of the query, and return database values from memcache before issuing a query to Cloud SQL.

### Google Cloud Bigtable
Google Cloud Bigtable is a scalable, fully-managed NoSQL wide-column database that is suitable for both real-time access and analytics
workloads.
Good for:
✑ Low-latency read/write access
✑ High-throughput analytics
✑ Native time series support
Google Cloud Bigtable is a scalable, fully-managed NoSQL wide-column database that is suitable for both real-time access and analytics
workloads.
Good for:
✑ Low-latency read/write access
✑ High-throughput analytics
✑ Native time series support
Reference: https://cloud.google.com/storage-options/

### Type of Database in google:
- OLTP - Cloud Spanner & Cloud SQL
- OLAP - Big Query
- NoSQL - Filestore and Big Table

### DataLab 
DataLab is used more for data science scenarios like interactive data analysis and build ML models. However, it does not provide anomaly detection OOTB.

### Deployment Manager
Deployment Manager is used to automate the process of provisioning infrastructure

### Datastore
Each entity in a Datastore mode database has a key that uniquely identifies it. The key consists of the following components:
• The namespace of the entity, which allows for multitenancy
• The kind of the entity, which categorizes it for the purpose of queries
• An identifier for the individual entity, which can be either
• a key name string
• an integer numeric ID
• An optional ancestor path locating the entity within the database hierarchy
An application can fetch an individual entity from the database using the entity's key, or it can retrieve one or more entities by issuing a query
based on the entities' keys or property values.
Reference: https://cloud.google.com/datastore/docs/concepts/entities#datastore-datastore-named-key-python, 
https://cloud.google.com/datastore/docs/concepts/entities#datastore-datastore-named-key-python

### Dataproc
- Google Cloud Dataproc is a fast, easy-to-use, low-cost and fully managed service that lets you run the Apache Spark and Apache Hadoop
- Cloud Dataproc provisions big or small clusters rapidly, supports many popular job types, and is integrated with other Google Cloud Platform services, such as Google Cloud Storage and Stackdriver Logging, thus helping you reduce TCO.
Dataproc runs Hadoop, so many kinds of jobs are supported automatically. When you create a cluster with Dataproc, the following technologies are configured by default:
* Hadoop
* Spark
* Hive
* Pig
🚨 Only use preemptible nodes for jobs that are fault-tolerant or that are low enough priority that occasional job failure won't disrupt your business.


### Identity-Aware Proxy 
=> application level authentication (https://cloud.google.com/iap/docs/concepts-overview)
If you want to start using Google Cloud resources but want to retain their on-premises Active Directory domain controller for identity
management, use Google Cloud Directory Sync to synchronise Active Directory usernames with cloud identities and configure SAML SSO.

Sequence of creating MIG from custom image:
1. Create a custom image from the existing disk.
2. Create an instance template from the custom image.
3. Create an autoscaled managed instance group from the instance template

Cloud VPN gateways and tunnels are regional objects, not global

Cloud Filestore is a scalable and highly available shared file service fully managed by Google. Cloud Filestore provides
persistent storage ideal for shared workloads. It is best suited for enterprise applications requiring persistent, durable, shared storage
which is accessed by NFS or requires a POSIX compliant file system.
reference: https://cloud.google.com/terms/services-20180724

Google Kubernetes Engine
To enable the GKE cluster to automatically add/remove nodes based on CPU load => Configure a HorizontalPodAutoscaler with a target CPU usage. Enable the Cluster Autoscaler from the GCP Console.
Deploy each microservice as a Deployment (not POD). Expose the Deployment in the cluster using a Service, and use the Service DNS name to
address it from other microservices within the cluster.

resilience testing can be done by Schedule a disaster simulation exercise during which you can shut off all VMs in a zone to see how your application behaves

SSD - Local SSD cannot be used for boot volume (because its Non-persistent ) and always used for temporary data storage. However, pd-ssd ( Performance (SSD) persistent disks) is persistent and can be used as boot disk.
Reference: https://cloud.google.com/compute/docs/disks#localssds


http response: Implement retry logic using a truncated exponential backoff strategy when response code is 5xx and 429.


Using the Cron service provided by App Engine, publish messages to a Cloud Pub/Sub topic. Subscribe to that topic using a messageprocessing utility service running on Compute Engine instances.


Instance Template
* When doing rolling update, can choose between Proactive and Opportunistic ( The MIG applies an opportunistic update only when you manually initiate the update on selected instances or when new instances are created. New instances can be created when you or another service, such as an autoscaler, resizes the MIG)

* Regional persistent disk is a storage option that provides synchronous replication of data between two zones in a region



====
GitHub cheat sheet reference: https://github.com/blqthien/Google-Certified-Architect-exam-resources/blob/master/GCP-Products-Cheat-Sheet.md

