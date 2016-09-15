# Developer Guide

* [Setting Up](#setting-up)
* [Design](#design)
* [Testing](#testing)
* [Appendix A: User Stories](#appendix-a--user-stories)
* [Appendix B: Use Cases](#appendix-b--use-cases)
* [Appendix C: Non Functional Requirements](#appendix-c--non-functional-requirements)
* [Appendix D: Gloassary](#appendix-d--glossary)

## Setting up

#### Prerequisites

1. **JDK 8** or later
2. **Eclipse** IDE
3. **e(fx)clipse** plugin for Eclipse (Do the steps 2 onwards given in
   [this page](http://www.eclipse.org/efxclipse/install.html#for-the-ambitious))


#### Importing the project into Eclipse

0. Fork this repo, and clone the fork to your computer
1. Open Eclipse (Note: Ensure you have installed the **e(fx)clipse plugin** as given in the prerequisites above)
2. Click `File` > `Import`
3. Click `General` > `Existing Projects into Workspace` > `Next`
4. Click `Browse`, then locate the project's directory
5. Click `Finish`

## Design
<img src="images/mainClassDiagram.png"/>

## Testing

* In Eclipse, right-click on the `test/java` folder and choose `Run as` > `JUnit Test`

## Appendix A : User Stories

Priorities: High (must have) - `* * *`, Medium (nice to have)  - `* *`,  Low (unlikely to have) - `*`


Priority | As a ... | I want to ... | So that I can...
-------- | :-------- | :--------- | :-----------
`* * *` | new user | see usage instructions | refer to instructions when I forget how to use the App
`* * *` | user | add a new person |
`* * *` | user | delete a person | remove entries that I no longer need
`* * *` | user | find a person by name | locate details of persons without having to go through the entire list
`* *` | user | hide [private contact details](#private-contact-detail) by default | minimize chance of someone else seeing them by accident
`*` | user with many persons in the address book | sort persons by name | locate a person easily

As a new user, I want to be able to see usage instructions so that I can refer to instructions when I forget how to use the App.

As a user, I want to be able to add a person to AddressBook so that I can find that person's details when I want to at a later time.

As a user, I want to delete a person from AddressBook so that I can remove entries of people that I no longer need.

As a user, I want to be able to find a person by name so that I can locate the details of persons without having to go through the entire list.

As a user, I want to be able to edit a person's details from AddressBook So that I don't have to delete and add back the same person from AddressBook.

As a user, I want to be able to add people who may have same details for certain fields like name or email and still be able to find both of them when I try to locate them.

As a user, I want to be hide the private contacts of other people so as to minimise the chances of someone else seeling them by accident.


## Appendix B : Use Cases

(For all use cases below, the **System** is the `AddressBook` and the **Actor** is the `user`, unless specified otherwise)

#### Use case: Delete person

**MSS**

1. User requests to list persons
2. AddressBook shows a list of persons
3. User requests to delete a specific person in the list
4. AddressBook deletes the person <br>
Use case ends.

**Extensions**

2a. The list is empty

> Use case ends

3a. The given index is invalid

> 3a1. AddressBook shows an error message <br>
  Use case resumes at step 2

#### Use case: Rename tag

**MSS**

1.The user finds all persons who have the certain tag
2.AddressBook shows a list of persons
3.User requests to change the name of the certain tag 
4.User inputs the new tag
5.AddressBook confirms this with the user
6.User re-confirms with AddressBook
5.AddressBook renames all of those tags with a new tag

**Extensions**
2a. The list is empty

>AddressBook informs the user that the list is empty
 Use case resumes at step 1

4a. The user inputs a tag that already exists

>4a1. AddressBook informs the user that the tag already exists
 Use case resumes at step 4
 
## Appendix C : Non Functional Requirements

1. Should work on any [mainstream OS](#mainstream-os) as long as it has Java 8 or higher installed.
2. Should be able to hold up to 1000 persons.
3. Should come with automated unit tests and open source code.
4. Should favor DOS style commands over Unix-style commands.
5. Should be able to launch within 8 seconds
7. Should be able to run smoothly and fast
8. Should be able to hold up to 1000 tags
9. Should be able be user-friendly
## Appendix D : Glossary

##### Mainstream OS

> Windows, Linux, Unix, OS-X

##### Private contact detail

> A contact detail that is not meant to be shared with others
