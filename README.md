# akpsi_kelompok_5_2025SB
## Use Case Diagram
### Big Picture
```
@startuml
left to right direction
rectangle "[Potential Client]" as pc
rectangle "[External Data]" as ed
actor "Admin" as a
actor "Sales Rep." as s
actor "Sales Manager" as sm

package "Lead Generation" {
 usecase "Predictive Market Intelligence" as UC1
 usecase "Client Segmentation" as UC2
 usecase "Generate Leads" as UC3
 usecase "Lead Scoring" as UC4
 usecase "Send Cold Email" as UC5
 usecase "Update Leads Status" as UC6
 usecase "Leads Status Report" as UC7

 usecase "Register users" as UC8
 usecase "Admin login" as UC9
 usecase "User login" as UC10
 usecase "Verify User" as UC11
}
s -- UC4
s -- UC2
UC1 -- ed
UC1 .-> UC2 : <<include>>
UC3 .-> UC5 : <<include>>
UC5 -- pc

s -- UC6
sm -- UC7

a -- UC9
a -- UC8
s -- UC10
sm -- UC10
UC8 .-> UC11 : <<include>>
UC10 .-> UC11 : <<include>>

@enduml
```
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
