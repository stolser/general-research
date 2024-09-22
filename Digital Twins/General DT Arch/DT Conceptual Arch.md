[PlantUML online editor](https://www.plantuml.com/plantuml/uml)

[C4-PlantUML System context docs](https://github.com/plantuml-stdlib/C4-PlantUML/blob/master/README.md#system-context--system-landscape-diagrams)

![dt-conceptual-arch](https://github.com/user-attachments/assets/4cf41ad9-cd8e-45a7-bd88-fa7b7716c40e)


```
@startuml
!theme vibrant
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml

System_Boundary(phTwin, "Physical Twin") {
  System(embedded, "Embedded", "Software on the physical system (edge computing, RTOS, firmware, TinyML)")
  System(iotSensors, "IoT sensors, smart devices", "Get telemetry data from the physical system")
  System(iotActuators, "IoT actuators", "Accept commands to update the physical system")
}

System_Boundary(digitalTwin, "Digital Twin") {
System_Boundary(edge, "Digital Twin (Edge)") {
  System(lDataIngestion, "Data Ingestion", "Collecting data (telemetry, config) from IoT sensors and embedded software", "", "", "", "IoT gateways, smart devices, message broker")
  System(lDataPreprocess, "Local data preprocessing", "Data cleansing, formatting, filtering, and aggregation")
  System(lDataStorage, "Local Data Storage", "Database, files")
  System(lModelStorage, "Local Model Storage", "Previously downloaded models (3D, ML) stored in a DB or files")
  System(lDecisionMaking, "Local Decision-Making", "A component responsible for generating commands and actions")
}

System_Boundary(cloud, "Digital Twin (Cloud, Data center)") {
  System(cRawDataStorage, "Raw Data Storage", "Stores semi- and unstructured data. Destination of EL data pipelines", "", "", "", "Data Lake")
  System(cDataPipelines, "Data Pipelines", "Batch/streaming data processing/transformation. Part of ETL/ELT and MLOps data pipelines", "", "", "", "ETL/ELT, MLOps")
  System(cProcessedDataStorage, "Processed Data Storage", "Stores semi- and structured data", "", "", "", "OLTP/OLAP DB, DWH")
  System(cModelStorage, "Model Storage", "Stores DT models (3D, ML)")
  System(cAnalysisSimulation, "Analysis, Simulation, Predictions", "DT's component that simulate and predict its state and behavior")
  System(cInfoBase, "Information Base", "Generates, stores, and exposes information about DT", "", "", "", "Knowledge Graph")
  System(cAPI, "APIs", "Exposes APIs", "", "", "", "SOAP, REST, RPC, GraphQL, WebSockets, Web hooks")
  System(cVisual, "Visualization", "Web/mobile UI, 3D")
}
}

System_Boundary(uas, "User-Avatar System") {
  Person(uasEnhancedUser, "Enhanced User", "Generates data/information/insights and provides them to other modules")
  System(uasAvatar, "Avatar", "A digital replica of the enhanced user that can perform simulations, acquire data, perform data analysis")
}

SystemDb_Ext(extData, "External Data Sources", "Raw/structured, files/DB/DWH")
System_Ext(extAPI, "External/3-rd party APIs")


Rel(embedded, iotSensors, "Config")
Rel(embedded, iotActuators, "Commands")
Rel(embedded, lDataIngestion, "Data, config")
Rel(iotSensors, lDataIngestion, "Real-time telemetry data, config")
Rel(lDecisionMaking, iotActuators, "Commands", "M2M interface")
Rel(lDataIngestion, lDataStorage, "Raw (unprocessed) data")
Rel(lDataIngestion, lDataPreprocess, "Raw data")
Rel(lDataPreprocess, lDataStorage, "Processed data")
Rel(lDataIngestion, cRawDataStorage, "Raw data")
Rel(lDataStorage, cRawDataStorage, "Raw data")
Rel(lDataStorage, lDecisionMaking, "Raw/preprocessed data")
Rel(lDataStorage, cDataPipelines, "Raw/preprocessed data")
Rel(cModelStorage, lModelStorage, "DT models (3D, ML) generated in the cloud")
Rel(lModelStorage, lDecisionMaking, "Models")

Rel(extData, cRawDataStorage, "Data ingestion", "Batch/Streaming EL data pipelines")
Rel(extData, cDataPipelines, "Data ingestion", "Batch/Streaming ETL data pipelines")
Rel(extAPI, cDataPipelines, "Data ingestion", "API access to external data sources")

Rel(cRawDataStorage, cDataPipelines, "Raw data")
Rel(cDataPipelines, cModelStorage, "Models (behavioral, conceptual, 3D, ML)")
Rel(cDataPipelines, cProcessedDataStorage, "Processed data")
Rel(cDataPipelines, cInfoBase, "Knowledge about DT (entities, components, relationships)")
Rel(cModelStorage, cAnalysisSimulation, "Models")
Rel(cProcessedDataStorage, cAnalysisSimulation, "Processed data")
Rel(cAnalysisSimulation, cVisual, "Data, reports, analytics")
Rel(cAnalysisSimulation, cAPI, "Data, reports, analytics")
Rel(cProcessedDataStorage, cVisual, "Processed data")
Rel(cProcessedDataStorage, cAPI, "Processed data")
Rel(cInfoBase, cVisual, "DT information/knowledge")
Rel(cInfoBase, cAPI, "DT information/knowledge")
Rel(cVisual, uasAvatar, "Models, data")
Rel(cAPI, uasAvatar, "Data")
BiRel(uasEnhancedUser, uasAvatar, "Virtual/Augmented Reality")
BiRel(uasAvatar, lDecisionMaking, "Commands, signals, data")
Rel(uasEnhancedUser, lDecisionMaking, "Human-Machine Interface")

@enduml
```
