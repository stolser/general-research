![general-dt-context-diagram](https://github.com/user-attachments/assets/aac59e22-3268-4e0a-82e9-a03d73241635)

```
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml

System_Boundary(cps, "Cyber-Physical System") {
  System(digitalTwin, "Digital Twin", "A digital representation of a real-world physical entity that simulates its different aspects (state, behavior, configuration, operations)")
  System(physicalTwin, "Physical Twin", "A real-world physical entity (object, process, system)")
}

System_Boundary(aus, "Avatar-User System") {
  Person(enhancedUser, "Enhanced User", "Generates data, information, and knowledge and provides them to the other modules")
  System(avatar, "Avatar", "A digital replica of the enhanced user that can perform simulations, acquire data, perform data analysis")
}

SystemDb_Ext(extData, "External Data Sources", "Raw/prepared, files/DB/DWH")
System_Ext(extAPI, "External/3-rd party APIs")

Rel(digitalTwin, avatar, "Models/Data")
Rel(avatar, digitalTwin, "Commands")
Rel(digitalTwin, physicalTwin, "Commands/Config", "IoT actuators")
Rel(physicalTwin, digitalTwin, "Periodic batch data uploads from local storage", "IoT gateways")
Rel(physicalTwin, digitalTwin, "Real-time data streams", "IoT sensors")
BiRel(enhancedUser, avatar, "Virtual/Augmented Reality")
Rel(enhancedUser, physicalTwin, "Updating config/operations")
Rel(extData, digitalTwin, "Data ingestion", "Batch/Streaming data pipelines")
Rel(extAPI, digitalTwin, "Data ingestion", "SOAP, REST, RPC, GraphQL, WebSockets, Web hooks")

@enduml
```
