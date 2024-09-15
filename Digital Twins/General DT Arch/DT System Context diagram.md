[PlantUML online editor](https://www.plantuml.com/plantuml/uml)

![general-dt-context-diagram](https://github.com/user-attachments/assets/b4e6f24f-5fcb-485d-b764-1bc587749006)

```
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml

System_Boundary(cps, "Cyber-Physical System") {
  System(digitalTwin, "Digital Twin", "A digital representation of a real-world physical entity that simulates its different aspects (state, behavior, configuration, operations)")
  System(physicalTwin, "Physical Twin", "A real-world physical entity (object, asset, process, system)")
}

System_Boundary(aus, "Avatar-User System") {
  Person(enhancedUser, "Enhanced User", "Generates data, information, and knowledge and provides them to the other modules")
  System(avatar, "Avatar", "A digital replica of the enhanced user that can perform simulations, acquire data, perform data analysis")
}

SystemDb_Ext(extData, "External Data Sources", "Raw/prepared, files/DB/DWH")
System_Ext(extAPI, "External/3-rd party APIs")

Rel(digitalTwin, avatar, "Models/Data")
Rel(avatar, digitalTwin, "Commands")
Rel(digitalTwin, physicalTwin, "Feedback/Commands", "M2M interface; IoT actuators")
Rel(physicalTwin, digitalTwin, "Periodic batch data uploads from local storage", "IoT gateways; Smart devices")
Rel(physicalTwin, digitalTwin, "Real-time data streams", "IoT sensors")
BiRel(enhancedUser, avatar, "Virtual/Augmented Reality")
Rel(enhancedUser, physicalTwin, "Human-Machine Interface")
Rel(extData, digitalTwin, "Data ingestion", "Batch/Streaming data pipelines")
Rel(extAPI, digitalTwin, "Data ingestion", "SOAP, REST, RPC, GraphQL, WebSockets, Web hooks")

@enduml
```
