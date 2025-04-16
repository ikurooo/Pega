**Fields** are **reusable UI** components that consist of a name and a Field Type.  ^fields
	A **field group** is a cluster of individual fields that, together, present related data inside a [[#^views]]. Field groups help to organise related values together under a single header and provide methods to add instructions or temporarily hide fields in collapsible Sections within a View.

**Data Pages** retrieve data for the data object from a source and caches that information in memory. ^data-pages

**Data Object**  are reusable building blocks that collect and organise [[#^fields]], [[#^data-pages]], [[#^views]], and other elements. -> **part of UI** ^data-object

**Data Record** is a unique collection of [[#^fields]] and values that make up an instance of a [[#^data-object]]
 ![[Pasted image 20250416113849.png]]
The **System of record** is an internal or external system that sources the data.

**Integration Map** is a diagram of the data objects, Cases, and systems of record in the application and where they are sourced.
	![[Pasted image 20250416114201.png]]
	
In the **visual model** system fields **cannot** be edited
	![[Pasted image 20250416114052.png]]
	

![[Pasted image 20250416112540.png]]

![[Pasted image 20250416113343.png]]

**Calculated values** express a relationship between fields by setting the value of a calculated field based on one or more input fields. 
	**Functions** iterate over items in a list.
	**Expressions** calculate a field value by referencing any combination of simple fields, fancy fields, and data relationships.
	**Decision tables** use a set of conditions to test property values and return an appropriate response.
		For example, an online shopping cart application provides customers a total cost for each item ordered, based on unit price and quantity ordered, then calculates a total for all the items ordered.

A **Calculation Network**s identify the relationships between fields and allow Pega to update all relevant fields whenever a value changes.

**Views** are reusable configurations of UI elements that allow you to build modular and consistent spaces for completing Assignments with less effort. ^views

**View vs Forms**
[Views | Pega Academy](https://academy.pega.com/topic/views/v5/in/72681/66426/66556#p-c64025f9-3b80-4104-a948-e3ef90dad9c4)

## Best practices

**Whenever possible**, use **standard, commonly-used data objects that Pega Platform provides**, such as Address-Postal and Address-Email. You can also add relevant data objects to your application.

If a **data object** only **partially** meets your needs, you can **extend** that data object. For example, if you want to create the Employee data object, you can extend the existing Person data object to create the Person-Employee data object.

If a **suitable data object does not exist** yet, **create** a new one. For example, if you want to add the Airport Codes data object, but you cannot use or extend an existing data object, create a new one in Pega Platform.

| Data relationship  | Data source<br>                                                                                                                                     | **Use case**                                                                                                                       |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| **Embedded Data**  | Use this field when information is collected from user input into a Case.                                                                           | Capture information about the emergency contact for a patient, and then store the details about the contact in the patient record. |
| **Data reference** | Use this field when you need to reuse another data object from outside the Case.                                                                    | Use this field in a Case Type for booking medical appointments, to reference the facility where the appointment is made.           |
| **Case reference** | Use this field when you want to reuse data from another Case.                                                                                       | A user selects from a list of service Cases from the Service Case Type.                                                            |
| **Query**          | Use this field for read-only access to information that is external to the Case. The Query Field Type allows parameters to query for specific data. | Return the next appointment for a medical professional or the list of all appointments they have in a given time frame.            |
