# Explore The House
[Head First C#](http://www.headfirstlabs.com/books//hfcsharp/)

&nbsp;
## 00 Start the project
* In VS, create a Windows Forms Application project.

&nbsp;
## 01 Add the abstract class Location
* Add the abstract class Location.
* The constructor sets the name field, which is the read-only Name property.
* The public Exits field is an array of Location references that keeps track of all of the other places that this location connects to.
* The base Description property returns a string that describes the room, including the name and a list of all of the locations it connects to (which it finds in the Exits[] field). Its subclasses will need to change the description slightly, so they’ll override it.

&nbsp;
## 02 Add the Room class
* The Room class inherits from Location and adds a private field for the decoration. Its constructor sets the field.
* The Room class will override and extend Description to add the decoration.

&nbsp;
## 03 Add the Outside class
* Outside is a lot like Room — it inherits from Location, and adds a private field for the Hot property, which is used in the Description() method extended from the base class.
* The Outside class will override and extend Description to add a comment if hot.

&nbsp;
## 04 Add the OutsideWithDoor class
