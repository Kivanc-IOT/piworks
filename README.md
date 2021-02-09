# Introduction

## Purpose

The main purpose of this document is to clarify and visualize the software design and architecture of the project using different viewpoints. It also describes how the use cases will be implement using this design. In a nutshell, this document explains the internal structure of the project to readers.

## Scope

This application aims to check and list user authorizations. Application can be used by two
different users that are “admin” and “super admin”.

# Description

## Product Functions
![](/Users/kivancersoy/Desktop/funcs1.png)

* Users will be able to do sort and hide disabled users operations.
* Admin can add new user that has a role "Guest" or "Admin".
* SuperAdmin can add new user that has a role "Guest" or "Admin" or "SuperAdmin".

## Assumptions

The correctness of the inputs such as username, e-mail etc. is the responsibility of the user.

# Body

## Design Views and Corresponding Viewpoints

### UML Class Diagram Description 

There are 4 different packages in this project. This approach was made so that different classes with different tasks did not interfere. In the application package, there is only one class that initiates the application.
In the pages package, there are ListUsersPage and AddUserPage classes. In the operation package, there is one class where user operations are performed. In the dataAccess package, there is User class. All of the methods’ getters and setters are not shown in the UML Class Diagram.
![](/Users/kivancersoy/Desktop/uml2.png)

### Interface Viewpoint
This viewpoint’s corresponding design view is to explain each methods used in UML, so that it provides interface to ones that want to use those methods. Also reveals how our system will work.

#### Design Concerns
Designers, programmers, and testers often use design entities that they did not develop. The interface description establishes an agreement among designers, programmers, and testers about how cooperating entities will interact. Each entity interface description should contain everything another designer or programmer needs to know to develop software that interacts with that entity.

#### Classes and Method Definitions
##### Pages:
###### ListUsersPage
*  handleNewUser(): 
This method handles the event user clicking the "New User" button.
*  handleSort(): This method handles the event user clicking one of the sort buttons.
*  handleHideDisabledUser(): This method handles the event user clicking Hide Disabled User button.

###### AddUserPage
* handleSaveUser(): This method handles the event user clicking the "Save User" button.


##### Operations:
###### UserOperations:
* fillUserRoles(currentUserType: UserType): 
This method fills the combobox according to the role of the user using the application.
* saveUser(username: String, displayName: String, e-mail: string, userType: UserType, isEnabled: boolean): This method adds the user to the ListUserPage.

### Interaction ViewPoint

This viewpoint’s corresponding design view is to explain, interaction of the users with the system and the events that occur in this interaction, the functions and classes are indicated.
Sequence diagram is used to describe interaction viewpoint. The whole process is shown from the beginning to the user so that the user can more fully understand the structure of the viewpoint and see which classes and functions he/she uses.

#### Design Concern
This shows relationships between application and classes. It helps the developers to determine the route. Sequence diagram is used to show interaction between classes.

#### Sequence Diagram

##### Add User Interaction
![](/Users/kivancersoy/Desktop/add.png)
##### Sort Interaction
![](/Users/kivancersoy/Desktop/sort.png)
##### Hide Disabled User Interaction
![](/Users/kivancersoy/Desktop/hide.png)
