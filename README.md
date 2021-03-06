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
## 04 Add the IHasExteriorDoor interface
* There are two exterior doors in the house, the front door and the back door. Every location that has one (the front yard, back yard, living room, and kitchen) should implement IHasExteriorDoor. The DoorDescription read-only property contains a description of  the door (the front door is “an oak door with a brass knob,” and the back door is “a screen door”). The DoorLocation property contains a
reference to the Location where the door leads (kitchen).

&nbsp;
## 05 Add the OutsideWithDoor class
* OutsideWithDoor inherits from Outside and implements IHasExteriorDoor.
* The base class’s Description property fills in whether or not the location is hot. And that relies on the original Location class’s Description property to add the main description and exits.

&nbsp;
## 06 Add the RoomWithDoor class
* The RoomWithDoor class inherits from Room and implements IHasExteriorDoor. It does everything
that the room does, but it adds a description of the exterior door to the constructor. It also adds
DoorLocation, a reference to the location that the door leads to. DoorDescription and DoorLocation
are required by IHasExteriorDoor.

&nbsp;
## 07 Add the form controls
* Add a big multiline text box called description to show the description of the current room. A ComboBox called exits lists all of  the exits in the current room. It’s got two buttons: goHere moves to the room selected in the ComboBox, and goThroughTheDoor is only visible when there’s an exterior door.

&nbsp;
## 08 Add the house objects
* In the form code, add the CreateObjects method. It instantiates the classes and passes the right information to each one’s constructor. The door description is passed to the OutsideWithDoor constructors. The Exits[] array for each instance is populated. For the IHasExteriorDoor objects,
their door locations are being set.

&nbsp;
## 09 Add the MoveToANewLocation method
* The MoveToANewLocation() method displays a new location in the form. First we need to clear the combo box, and then we can add each of the locations’ names to it. Finally, we set its selected index (or which line is highlighted) to zero so it shows the first item in the list. The “Go through the door” button is set to invisible if the current location doesn’t implement IHasExteriorDoor.
* Use the method to move to the living room as a starting point.

&nbsp;
## 10 Use MoveToANewLocation with goHere button
* When the user clicks the “Go here:” button, it moves to the location selected in the combo box.

&nbsp;
## 11 Go through the outdoors
* When the user clicks the “goThroughTheDoor” button, moves to the appropriate location.
* We need to use the as keyword in order to downcast currentLocation to an IHasExteriorDoor so we can get access to the DoorLocation field.
