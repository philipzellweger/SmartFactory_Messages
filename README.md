# SmartFactory_Messages

The core of the SmartFactory project is communicating between the participants, i.e. receiving and sending messages. By using the MQTT technology, it must be possible to dynamically decide in the callback function which message type is involved in order to correctly interpret the message and store it in the correct memory. For this requirement a library was created which can serialize messages through the design pattern factory. The purpose of this concept is to define all message types and their handling in one place in order to ensure a simple communication process. 

The used desing pattern is the factory. The principle is based on the polymorphism in which virtual functions of the base class are overwritten in the child class. A createfunction refers the message type to the correct specific class to serialize the received message. This principle ensures an easy handling of the different message types and standardizes the handling of messages throughout the SmartFactory project. 

## Table of contents
- Tools and technologies
   - Visual Studio Code
   - Doxygen
   - Shared pointer
- Software
   - Factory
   - UML
   - Dependency Graph
   - Collaboration Diagram
- ToDo's
- Contributors
- Changelog
- License
- Links to SmartFactory

## Tools and technologies

The source code is implemented in the programming language C++. In the following, the tools for editing the project are listed.

#### Visual Studio Code
The development environment used is [Visual Studio Code](https://code.visualstudio.com/) with the [PlatformIO extension](https://docs.platformio.org/en/latest/ide/vscode.html). The development environment can be downloaded open sourced. For an installation guide look here.  

#### Doxygen
Doxygen was used for documenting the source code. For using Doxygen in Visual Studio code, the [Doxygen Documentation Generator](https://marketplace.visualstudio.com/items?itemName=cschlosser.doxdocgen) extension is available.

#### Shared pointer

Shared pointers are used to transfer dynamically created objects. The advantage of shared pointers is that you do not need direct control over deleting dynamically created objects. As soon as no pointer points to the created object, the object is automatically deleted. This tool makes the factory design pattern very powerful. An explanation of shared pointer can be found [here](https://de.cppreference.com/w/cpp/memory/shared_ptr).

## Software

#### Factory
The structure of the factory design pattern is simple. It consists of a parent class which has a creatfunction and at least one purely virtual function. In addition, it has several child classes, which overwrite and thus define the purely virtual function of the element class. In the createfunction an object of the child class is dynamically created under condition of a criterion (in our case by the message type), the necessary overwritten functions are executed and finally a pointer with type of the parent class, which points to the dynamically created object, is returned. One of the advantages of the design pattern is its modularity. If a new message type is created in the project, it can easily be defined as a child class and added in the createfunction. This principle makes handling the different message types easy and modular.
[Here](https://sourcemaking.com/design_patterns/factory_method) is a detailed explanation of the design pattern factory.

![factory](https://developer-blog.net/wp-content/uploads/2018/01/factory-design-pattern.jpg)
[Image: [Developer-Blog FACTORY DESIGN PATTERN](https://developer-blog.net/factory-design-pattern-in-c/)]

#### UML
The figure below shows the data model in UML notation. In the factory implemented in SmartFactory, the function "translateJsonToStruct" is the creat function and "parseJSONToStruct" is the virtual function which is overwritten.

================== IMAGE ===============================

#### Dependency Graph
The figure below shows the dependency tree of the Message interface.


 ==================== IMAGE ==================================
 
 
 
#### Collaboration Diagram
The figure below shows the collaboration tree of the Message interface. The arrow simbolizes an instanced object.

=================== IMAGE ==========================================

## ToDo's
- [ ]
- [ ]

# Contributors
- [Philip Zellweger](https://github.com/philipzellweger)

# Changelog

V 1.0   -	Release SA HS20 -	[Philip Zellweger](https://github.com/philipzellweger)

# License

MIT License

# Links to SmartFactory
- [SmartFactory-Sortic](https://github.com/LMazzole/SmartFactory-Sortic)
- [SmartFactory_Box-Sortic](https://github.com/LMazzole/SmartFactory_Box-Sortic)
- [SmartFactory_Vehicle-Sortic](https://github.com/LMazzole/SmartFactory_Vehicle-Sortic)
- [SmartFactory_Vehicle-Basis](https://github.com/LMazzole/SmartFactory_Vehicle-Basis)
- [SmartFactory_SorticRoboter](https://github.com/philipzellweger/SmartFactory_SorticRoboter)
- [SmartFactory_SorticRoboter_CommunicationHub](https://github.com/philipzellweger/SmartFactory_SorticRoboter_CommunicationHub)
- [SmartFactory_MQTTCommunication](https://github.com/LMazzole/SmartFactory_MQTTCommunication) for Adafruit Feather M0 Wifi
- [SmartFactory_MQTTCommunication](https://github.com/philipzellweger/SmartFactory_MQTTCommunication) for Esp32 DevKitC
- [SmartFactory_I2cCommunication](https://github.com/philipzellweger/SmartFactory_I2cCommunication)
- [SmartFactory_Messages](https://github.com/philipzellweger/SmartFactory_Messages)
