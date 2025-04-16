**SOR** - System of record i.e. a database [[The Data Model#^0faafe]]

**x Type** is like the blueprint for a specific instance of **x** ex.: **Rule** vs **Rule Type**. See: [[Rules]]

A **Case Type** is an abstract model of a business transaction. [[Pega Case management#^7683cc]]

A **Case** is a specific transaction instance. [[Pega Case management#^ae4572]]

**Stages** ->  represent the Case transfer from one caseworker to another or a significant change in the status of the Case. [[Pega Case management#^a63d22]]

**Processes** -> contain a series of Tasks, or Steps, that users complete as they work on the case. [[Pega Case management#^a63d22]]

**Steps** ->  within a Process is either a user Action or an automated Action. [[Pega Case management#^a63d22]]

**Persona** -> determines who interacts with the application [[Pega Case management#^6c0ba8]]

**Channel** -> determine how a persona acts with an application [[Pega Case management#^6c0ba8]]

**Data Objects** -> are reusable building blocks that collect and organise fields, data-pages, views, and other elements. -> **part of UI** [[Pega Case management#^bad95b]] [[The Data Model#^data-object]]

**Data Pages** retrieve data for the data object from a source and caches that information in memory.
[[The Data Model#^4ecbbe]]

**Data Record** is a unique collection of fields and values that make up an instance of a data object [[The Data Model#^425e13]]

**Integration Map** is a diagram of the data objects, Cases, and systems of record in the application and where they are sourced. [[The Data Model#^aabc14]]

**Rules** -> Pega applications compormiuse of instructions called **Rules** that govern the apllication behaviour, these rules are organised into **Layers** that can be reused between applicatiions. These layers are referred to as **Rulesets**. [[Rules]]

A **widget** is a complex component focused on a specific business goal. The component is fully operational in any context. [[Pega Constellation Design System#^4207f6]]
  
A **design token** is a tool used to convey key design and UX principles across multiple channels and technologies. [[Pega Constellation Design System#^cc7a35]]
  
A **prescribed design** is a set of informed default designs and templates with preset configurations to reduce designing time. [[Pega Constellation Design System#^fb5170]]
  
A **pattern** is a repeatable and scalable combination of components and user flows to create a consistent experience. [[Pega Constellation Design System#^a3c70e]]
  
A **theme** is a set of simple settings used to style an application according to brand standards.
[[Pega Constellation Design System#^81c82c]]

A **Worklist** is a list of all open Assignments, in order of importance, for a **specific user**. [[Routing Assignments#^d78c5f]]

A **Work Queue** is a list of all open Assignments, in order of importance, for a group of users. [[Routing Assignments#^d75d66]]

A **Work Group** identifies a cross-functional team that uses a **Work Queue** to distribute work. [[Routing Assignments#^0b8bb0]]

