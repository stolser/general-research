https://mermaid.js.org/syntax/mindmap.html

```mermaid
%%{
  init: {
    'theme':'forest'
  }
}%%

mindmap
  root((Digital Twin))
    id)"`**Purpose/Goals**`"(
        What? Discover problems/issues
        Why? Understand why they appear
        What-if? Analyze what may happen
        What-will? Predict future problems/issues
        How? Find solutions/prescriptions for existing/future problems/issues
    id)"`**Technologies**`"(
        IoT
            Sensors
            Real-time data collection
            Actuators
            Sending commands to the physical system
            Edge Computing, Embedded
            MicroK8s, K3s, KubeEdge
            Google Anthos
            Edge AI, TinyML
            Connectivity
            Physical/Data Link layer: 5G, Ethernet, Wi-Fi, Bluetooth, ZigBee
            Application layer: MQTT, CoAP, ZigBee
        Robotics, Other hardware
            Drones
            3D Scanning/Printing
        Virtual/Augmented Reality
        AI/ML
            Edge AI/TinyML
            Inference/Predictions without Internet connection
            Federated Learning
            Data privacy
        Blockchain
            Security
            Data privacy and availability
            Hardware integrity
        Big Data
            Batch/Streaming data pipelines
            Ingestion, processing, and storing historical/real-time data
            Analytics on large data sets
            DWH/Data Lake/Data Vault 2.0
        Cloud
            Infinite scalability
            Effective Ops
            Simplified hardware management and operations
        Knowledge Graphs
            Fast, convenient, and contextual access to all existing information
    id)"`**Architectural Considerations and Docs**`"(
        Architecturally significant functional requirements
        DDD for core/non-core domain analysis/modeling and logical components identification
        EventStorming to identify domain events
        Identifying/prioritizing NFRs/Arch Characteristics
        Identifying Fitness Functions to track and measure NFRs
        Physical architecture, software/hardware components, services, APIs, storages/DBs, protocols
        ADRs to document architecturally significant decisions
    id)"`**General Considerations**`"(
        Observability
            Software observability
                Logging
                Monitoring
                Tracing
                Performance profiling
            Physical system observability
        Software/Data Security
            Zero Trust Architecture
        Regulatory/Legal Compliance
            PCI DSS, GDPR, SOX, HIPAA
    id)"`**Portfolio/Project/Product Management**`"(
	    Enterprise Architecture
            Digital Transformation
            TOGAF, ITIL
            Identifying business drivers, objectives, and requirements
            Identifying core values and high-level principles/policies, and ensuring they are followed
            Providing a high-level architecture governance
            Capabilities analysis and prioritization business/cultural/process/technical/measurement
	    Lean Portfolio/Product Management
            Value Stream analysis
            Systems Thinking for analysis of the physical twin as a CAS
	        Design Thinking for problem identification/discovery/research
            Hypothesis-Driven Development
            SAFe
    id)"`**Types of DT**`"(
        Digital Model
        Digital Shadow
        Network DT
        Cognitive DT
```
