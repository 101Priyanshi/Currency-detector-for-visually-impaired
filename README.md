
### NOTE: The mdj files were created in StarUML
## PROBLEM STATEMENT
To build a currency detector app for visually impaired people
## CLASS DIAGRAM
A class diagram in the Unified Modeling Language is a type of static structure diagram that describes the structure of a system by showing the system's classes, their attributes, operations, and the relationships among objects.
In our Problem, we have two classes named ‘User’ and ‘Currency’ whose multiplicity is many -to-many, and an Association Class named ‘Predict’ as shown in the class diagram..
### USER CLASS
#### Attributes : 
email
username
password

#### Operations :
getLoginDetails() : retrieves the login details of the user
### CURRENCY CLASS
#### Attributes :
Value : value of the currency

#### Operations :
getValue() : retrieves the value of the currency from database.  

### PREDICT CLASS (ASSOCIATION CLASS)
#### Attributes :
valuePredicted : value of the currency detected by the app using the image uploaded



#### Operations :
scanPhoto() : User scans the Currency
predctCurrency() : App detects the currency and predict the value of the currency
displayOutput() : Voice is generated and played which says the value of the currency whose image is taken. 

## OBJECT DIAGRAM
Object Diagrams represent an instance of Class Diagram.
Here, we have two objects, one of User class and other of Currency class connected via link.
Object Diagram uses notation that is similar to that used in class diagrams. 



## STATE CHART DIAGRAM
State chart diagram is used to describe the states of different objects in its lifetime.
The first step is to start the app and capture the image.
Then the app will try to identify the currency.
If there is no ambiguity  then the app notifies the user in the form of audio.
If ambiguity exists then the user is notified to capture the image one more time.

## USE CASE DIAGRAM
A use case diagram iis a representation of a user's interaction with the system that shows the relationship between the user and the different use cases in which the user is involved.


### ACTORS
Actors represent the external entities that interact with the system. Actors include roles the system needs to deal with. 
User is the primary actor.
Currency dataset and audio dataset are the secondary actors.
The currency detector app provides common  services to blind people which include: Capture Image, Currency Identification, Audio Generation and Audio Output  services. 


### ROLES
User captures image of the currency and uploads the same.
Image is processed by the app in the back-end
Value of the currency is predicted
The label given to the currency is then sent as an audio output to the user from the audio dataset

### EXCEPTION SCENARIO
The currency scanned might be  fake.
Non- currency image scanned (the model will still give some label to the image even if it is not a currency image)
The currency may be torn (i.e. it may be in a bad condition)  


