
### NOTE: The mdj files were created in StarUML
## PROBLEM STATEMENT
To build a currency detector app for visually impaired people
## CLASS DIAGRAM
* A class diagram in the Unified Modeling Language is a type of static structure diagram that describes the structure of a system by showing the system's classes, their attributes, operations, and the relationships among objects.<br/>
* In our Problem, we have two classes named ‘User’ and ‘Currency’ whose multiplicity is many -to-many, and an Association Class named ‘Predict’ .<br/>
### USER CLASS
* #### Attributes : 
  * email<br/>
  * username<br/>
  * password<br/>

* #### Operations :
  * getLoginDetails() : retrieves the login details of the user
### CURRENCY CLASS
* #### Attributes :
  * Value : value of the currency

* #### Operations :
  * getValue() : retrieves the value of the currency from database.  

### PREDICT CLASS (ASSOCIATION CLASS)
 * #### Attributes :
   * valuePredicted : value of the currency detected by the app using the image uploaded



 * #### Operations :
   * scanPhoto() : User scans the Currency<br/>
   * predctCurrency() : App detects the currency and predict the value of the currency<br/>
   * displayOutput() : Voice is generated and played which says the value of the currency whose image is taken. <br/>

## OBJECT DIAGRAM
* Object Diagrams represent an instance of Class Diagram.<br/>
* Here, we have two objects, one of User class and other of Currency class connected via link.<br/>
* Object Diagram uses notation that is similar to that used in class diagrams. <br/>



## STATE CHART DIAGRAM
* State chart diagram is used to describe the states of different objects in its lifetime.<br/>
* The first step is to start the app and capture the image.<br/>
* Then the app will try to identify the currency.<br/>
If there is no ambiguity  then the app notifies the user in the form of audio.<br/>
If ambiguity exists then the user is notified to capture the image one more time.<br/>

## USE CASE DIAGRAM
A use case diagram iis a representation of a user's interaction with the system that shows the relationship between the user and the different use cases in which the user is involved.


### ACTORS
* Actors represent the external entities that interact with the system. Actors include roles the system needs to deal with. <br/>
* User is the primary actor.<br/>
* Currency dataset and audio dataset are the secondary actors.<br/>
* The currency detector app provides common  services to blind people which include: Capture Image, Currency Identification, Audio Generation and Audio Output  services.<br/> 


### ROLES
* User captures image of the currency and uploads the same.<br/>
* Image is processed by the app in the back-end<br/>
* Value of the currency is predicted<br/>
* The label given to the currency is then sent as an audio output to the user from the audio dataset<br/>

### EXCEPTION SCENARIO
* The currency scanned might be  fake.<br/>
* Non- currency image scanned (the model will still give some label to the image even if it is not a currency image)<br/>
* The currency may be torn (i.e. it may be in a bad condition)  <br/>

## USER STORY

| IDENTIFIER|                USER STORY                       | POINTS |
|:---------:|:-----------------------------------------------:|:------:|
|   Req 01  |          Identify currency note                 |   10   |
|   Req 02  |Generate audio output for the detected currency  |   10   |
|   Req 03  |          User gives login details               |   6    |
|   Req 04  |          Detect torn currency                   |   3    |
|   Req 05  |          Detect fake currency                   |   3    |




## NATURAL LANGUAGE

i. Once the user logs in, the system asks for the image of the currency or an already scanned one. <br/>
ii. Once the user uploads, image is sent for processing where the system has a trained Machine Learning model which processes the image and gives the value of the currency as its output<br/>
iii. Based on this value,  voice is generated from the audio dataset and given as the output to the user.<br/>
iv. Taken image or scanned copy is again added to the dataset along with the label i.e value of currency for further usage.
 ## STRUCTURED SPECIFICATION
 * Function: Detect currency.

* Description: Detection of currency for blind people.

* Inputs: Scanned image of the currency , Currency Dataset .

* Source : Image of the Currency from the user, Images of all types of Currencies in a Dataset

* Output : Value of the currency in audio format.

* Destination: Value of the currency.

* Action : Using the Image taken as Input from the user and processing it using a Machine Learning   
 Algorithm, its value is predicted. Based on the value predicted, voice is generated and given as Output

* Requirements : Image Dataset which contains a large set of images of all types of currencies along with their labels to train the Machine Learning Algorithm and to compare while testing. Voice Dataset to give voice output.

* Precondition:     Image scanned by the user should be a currency and should be identifiable.
		Image scanned by the user should be clear.
		Image scanned by the user should be not more than 1.5 MB.

* PostCondition: Taken image is added to the Image Dataset along with the labels so that can be used later

* Side Effects: None

## TABULAR FORMAT
|               Condition                |                  Action              |
|:-------------------------------------: |:------------------------------------:|
|       Captured Image pixel > 2 MP      |Image accepted for further processing |
|       Captured Image pixel < 2 MP      |Image rejected and asked to scan again|
|Captured Image (Real and good condition)|Sent for processing                   |
|        No Exception (Fake Notes)       |Audio Output of scanned currency      |



