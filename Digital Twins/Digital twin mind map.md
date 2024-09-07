https://mermaid.js.org/syntax/mindmap.html

```mermaid

mindmap
  root((Digital Twin))
    id)"*Purpose/Goals*"(
      What? Discover problems/issues
      Why? Understand why they appear
      What-if? Analyze what may happen
      What-will? Predict future problems/issues
      How? Find solutions/prescriptions for existing/future problems/issues
    id)"*Technologies*"(
      Digital Transformation
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
      Back-end, Front-end, UI/UX Development
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
	  id)"*Portfolio/Project/Product Management*"(
	    Enterprise Architecture
	      TOGAF, ITIL
	      Providing a high-level architecture governance
	      Identifying required business, technical, organizational, and measurement capabilities
	      Identifying core values and high-level principles/policies, and ensuring they are followed
	    Lean Portfolio/Product Management
	      Value Streams
	      Systems Thinking
	        Provides a complex approach to problem identification and solution development
	      Design Thinking
	        Identifying the right problems and appropriate solutions
	      The SAFe Framework
	      Hypothesis-Driven Development
    id)"*Architecture considerations/docs*"(
      Architecturally significant Functional requirements
      Logical Components
        DDD, Core Domains, EventStorming
      NFRs/Arch Characteristics
      Arch style/Physical architecture
      Arch Decisions
        ADRs
    id)"*Types of DT*"(
      Digital Model
      Digital Shadow
      Network DT
      Cognitive DT
        Self-learning
        Self-improving

```
