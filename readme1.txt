The **Pega PDC (Pega Diagnostic Cloud)** and the **Prometheus Exporter** are two distinct tools that serve different purposes in terms of monitoring, performance metrics, and system diagnostics. Here's a comparison to help clarify their differences:

### 1. **Pega PDC (Pega Diagnostic Cloud)**

* **Purpose**: Pega PDC is a cloud-based monitoring and diagnostics tool built specifically for Pega applications. It's used to collect, analyze, and visualize performance data related to the Pega Platform. PDC is designed to offer detailed insights into the health of Pega applications, troubleshoot issues, and improve overall system performance.

* **Metrics**: It provides out-of-the-box monitoring for various aspects of the Pega application, such as rule execution, case processing, database performance, memory utilization, JVM metrics, and much more.

* **Integration**: The Pega Diagnostic Cloud is primarily used within the Pega ecosystem. It connects to Pega environments and provides aggregated views of performance data, alerts, and diagnostics.

* **Features**:

  * Real-time monitoring of Pega applications.
  * Advanced troubleshooting, including root cause analysis for performance issues.
  * Customizable dashboards tailored to Pega-specific metrics.
  * Historical data storage and trend analysis for long-term performance tracking.

* **Audience**: Primarily for Pega administrators, developers, and operations teams working with Pega systems.

### 2. **Prometheus Exporter**

* **Purpose**: Prometheus is an open-source monitoring and alerting toolkit designed for cloud-native environments. It is widely used to monitor applications, infrastructure, and services in Kubernetes, microservices, and cloud environments. Prometheus uses a time-series database to store metrics and provides robust querying capabilities via the PromQL language.

* **Metrics**: Prometheus does not focus on Pega-specific metrics by default but can collect a wide range of system and application-level metrics such as CPU usage, memory, disk I/O, network traffic, and application-specific metrics via exporters.

* **Exporter**: Prometheus relies on **exporters**, which are specialized programs or scripts that expose metrics from various sources (e.g., databases, web servers, JVMs, etc.) in a format that Prometheus can scrape. Common exporters include:

  * **Node Exporter**: For system-level metrics (CPU, memory, disk, etc.).
  * **JVM Exporter**: For JVM-based applications like Pega.
  * **Database Exporters**: For PostgreSQL, MySQL, etc.
  * **Custom Exporters**: For specific application metrics like Pega, custom exporters can be written to expose relevant data.

* **Integration**: Prometheus is a more general-purpose monitoring system that can integrate with any application or infrastructure, including Pega, via custom exporters.

* **Features**:

  * Highly flexible and can be customized for a variety of use cases.
  * Open-source and widely adopted in cloud-native environments.
  * Can be extended with custom exporters for Pega or other enterprise applications.
  * Querying via PromQL and advanced alerting with Alertmanager.

* **Audience**: Typically used by DevOps, Site Reliability Engineers (SREs), and teams managing cloud-native, containerized, or hybrid environments.

### **Comparison Summary**

| Feature             | Pega PDC                                          | Prometheus Exporter                                                 |
| ------------------- | ------------------------------------------------- | ------------------------------------------------------------------- |
| **Purpose**         | Pega-specific monitoring and diagnostics          | General-purpose monitoring for apps & infrastructure                |
| **Focus**           | Pega application performance & diagnostics        | System and application metrics (wide variety)                       |
| **Integration**     | Native to Pega Platform                           | Integrates with any app/infrastructure, custom exporters for Pega   |
| **Metrics**         | Pega-centric (JVM, case processing, rules)        | System-level (CPU, memory), application-level (JVM, databases)      |
| **Ease of Use**     | Tailored for Pega users, user-friendly dashboards | Requires setup of exporters, flexible but more manual configuration |
| **Customizability** | Limited to Pega application metrics               | Highly customizable with Prometheus exporters                       |
| **Deployment**      | Cloud-based, specific to Pega                     | Self-hosted, often on Kubernetes or servers                         |
| **Target Audience** | Pega admins, developers, ops teams                | DevOps, SREs, infrastructure teams                                  |

### **When to Use Each**:

* **Use Pega PDC** if you're primarily monitoring and troubleshooting Pega applications. It’s the easiest and most integrated tool for Pega environments, offering out-of-the-box insights and diagnostics specifically designed for Pega systems.

* **Use Prometheus Exporter** if you need a more general-purpose monitoring tool that works across a wide range of systems, applications, and services. You can configure Prometheus with custom exporters to monitor Pega alongside your other infrastructure and applications. It’s particularly useful in cloud-native or microservice environments where you need a centralized monitoring solution for everything.

---

Would you like more details on how to integrate Prometheus with Pega, or specific examples of metrics each tool monitors?



Here’s a grouped and categorized version of the questions from the image, organized for clarity and easier reference:

---

### 🔐 **Security, Compliance & Data Handling**

* How were the internal control concerns sorted such as PCI/PII data handling?
* How did you handle data residency, backup and DR?
* Did auditors/regulators raise any issues with moving to the Pega Cloud?
* Was there any challenge on data/case archival (if there were existing measures in place)?
* Co-ordination required during VISA compliance release?
* Security - PII / PCI (already covered by Balaji)?

---

### 🔄 **Migration Strategy & Execution**

* Was it a Lift/Shift or phased approach or greenfield build?
* What was the biggest challenge during migration (data, integration, performance, security/pen testing)?
* How long did the entire migration process take from planning to go live?
* What was the Migration strategy they adapted for Data Migration, Archival?
* What was the preferred Migration Approach? Parallel Run vs Big Bang?

---

### ☁️ **Pega Cloud vs Internal Hosting**

* How complex was the integration from Pegacloud to internal Lloyds APIs for fetching data?
* How has the Pegacloud performed in terms of latency, throughput and uptime? Do you have any noisy neighbour issues?
* How responsive is the Pega cloud support compared to internal teams?
* Do you still maintain some infra ops skills inhouse or is everything managed by Pega?
* What are the trade-offs you have taken as a result of this move?
* Was there a comment made that Lloyds initially went with a single VPC but then pivoted to multi, why?

---

### 🧪 **Testing & Environments**

* What is your experience on incidents and downtime?
* What is the number of test environments and production environments for each application?
* How are the test environments and production environments handled in Pega Cloud or internal system?
* Lloyds had multiple instance of PEGA if I see it - what was the Migration strategy?

---

### ⚙️ **Technical Implementation & Operations**

* What was Pega’s involvement and did you use 3rd party SI?
* How did you customize it (your environment)?
* How easy is patching, upgrades and scaling now? Inhouse or is everything managed by Pega?
* Were you able to reduce headcount on infra management costs after this move?
* How has this impacted time to market for new workflows?

---

### 💸 **Cost & Pricing**

* How are the costs comparing now - initial setup vs ongoing operational?
* Any surprises in consumption-based pricing?

---

### 🧠 **Best Practices, Learnings & Strategy**

* What are the best practices they follow for minor and major Pega version upgrades?
* What is the design principle they have taken to avoid the Swivel Chair issue?
* What is the experience of internal Pega connect with PEGA in Cloud for end-to-end scenarios?

---

### 🤖 **AI and Innovation**

* Leveraging Pega Gen AI (ease vs benefits vs use cases)?

---

### 📊 **Metrics & Business Impact**

* What is the number of resources/applications in PEGA Engineering vs Integration/API/platform team to connect PEGA on cloud with On-prem or other interfacing applications?

---

Let me know if you want this converted into a document, spreadsheet, or formatted slide content.
