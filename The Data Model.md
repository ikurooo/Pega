**Fields** are **reusable UI** components that consist of a name and a Field Type.  ^fields
	A **field group** is a cluster of individual fields that, together, present related data inside a [[#^views]]. Field groups help to organise related values together under a single header and provide methods to add instructions or temporarily hide fields in collapsible Sections within a View.

**Data Pages** retrieve data for the data object from a source and caches that information in memory. ^data-pages
	Pega Platform automatically prepends the characters D_ to the name of a Data Page to differentiate the page from other pages in memory. 
	1. The **structure** of the page contents.
	2. The **Object Type** represented by the contents of the Data Page.
	3. The **edit mode** supported by the page.
	4. The **scope** of the Data Page.
		![[Pasted image 20250416134659.png]]

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
# Data Manipulation

**Data Transforms** are used to initialise, manipulate, map and transform data associated with a Case.
	Data Transforms can also be used to set default values when a new case is created

**Superclasses** can make Data Transforms more modular.
	Consider a Claim class with a Home subclass. The Home subclass, in turn, has a Rental subclass with Data Transforms at each level that sets the default values. You set your Data Transforms so that common default values are set in the Claim class, and specific values are set in the subclasses.

# Data Validation
**Validate Rules** ensure that the data that your users provide meets the Conditions that a Case requires in order to go forward.
	Business logic might require that an application validates data differently based on certain conditions, such as user input, Case Status or Stage, or a user action. This can be accomplished with a _Validate_ Rule.

**Edit Validate** Rules are typically applied to properties, and consist of Java code that compares the value of a property to a defined pattern. These rules are used for client-side validation. 
	For example, an edit Validate Rule can check whether a property value consists of seven numbers, with a space separating the third and fourth numbers. If the pattern match succeeds, the input is considered valid. Otherwise, the system flags the input with an error.  ^77afac
# Data Sources

If you must **combine data** from multiple sources to populate a Data Page, select the **Aggregate** sources option. 

 If a Data Page contains **more than one source**, configure a **logical Condition** for each source to test whether to query the data source.

# Refresh strategies

In a Data Page record, the Load management tab provides developers with three options for configuring a refresh strategy for a read-only Data Page. 

### Reload once per interaction

The Reload once per interaction option updates the contents of the Data Page each time a user accesses the page in memory. 
### Do not reload when

The Do not reload when option uses a When Condition to test whether the Data Page is considered stale. If the Condition returns a result of true, the contents of the Data Page are considered current and Pega Platform does not attempt to update the Data Page.

### Reload if older than

The Reload if older than option uses a fixed interval of time to determine whether a Data Page is stale. After the interval ends, the Data Page contents are considered stale, and the next attempt to access the Data Page causes Pega Platform to update the Data Page. So, if a Data Page with a **Reload if older than interval of 10 minutes** is first accessed at 1200 (12:00 PM), the page is considered stale at 1210 (12:10 PM). Pega Platform then updates the contents of the page **when a user accesses the stale page**, which may not occur until 1300 (1:00 PM).