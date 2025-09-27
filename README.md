# akpsi_kelompok_5_2025SB
## Use Case Diagram
### user management
```
@startuml
left to right direction
actor "Admin" as a
actor "Sales Rep." as s
package "User Access & Management" {
 usecase "Register users" as UC1
 usecase "Admin login" as UC2
 usecase "User login" as UC3
 usecase "Verify User" as UC4
}

a -- UC2
a -- UC1
s -- UC3
UC2 .-> UC4 : <<include>>
UC3 .-> UC4 : <<include>>

@enduml
```
### generating leads
```
@startuml
left to right direction
actor "Sales Rep." as sr
rectangle "Potential Client" as pc
rectangle "External Data" as ed
package "Lead Generation" {
 usecase "Predictive Market Intelligence" as UC1
 usecase "Client Segmentation" as UC2
 usecase "Generate Leads" as UC3
 usecase "Lead Scoring" as UC4
 usecase "Send Cold Email" as UC5
}
sr -- UC4
sr -- UC2
UC1 -- ed
UC1 .-> UC2 : <<include>>
UC3 .-> UC5 : <<include>>
UC5 -- pc

@enduml
```
### tracking leads status
```
@startuml
left to right direction
actor "Sales Rep." as sr
actor "Sales Manager" as sm

package "Leads Tracking" {
 usecase "Update Leads Status" as UC1
 usecase "Leads Status Report" as UC2
}

sr -- UC1
UC2 -- sm

@enduml
```
