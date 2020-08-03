# Security-system-using-face-recognition-and-qr-code-scanning

### This github repository hosts the code required for a security system / entry log system using face recognition and qr code scanning.

#### Make a folder named "images" to house the image database for facial recognition.
#### This only takes one picture per person and the picture is named the name of the person.

#### Another Folder named "entry logs" should be made alongside it which is empty for the time being.
#### This folder stores automatically generated entry logs for each day with the information about the person and time.

##### Mysql database structure:
![Mysql database structure](https://res.cloudinary.com/gautzz/image/upload/v1596104257/Annotation_2020-07-30_154031_oucrd7.png)

The database being used is students database.

The code can also be easily modified to work for employee database for example or anything else.

## Working:

### Set up

##### The program encodes faces from the images folder using the face_recognition and dlib libraries.
##### it then connects to a mysql database for checking peoples details.

### While Running

##### While running the program looks for faces in realtime and tries to match it with the encodings of the faces in the image folder.
##### If the face matches, It now looks for a QR code of the person.

##### The QR code contains the registration number(in this case because its unique) of the person.
##### The program decodes the QR code (using pyzbar library) and checks if the person is showing their won QR code with their face or not.
##### If they satisfy all conditions, the program displays the message --> "Access Granted, Welcome {Name of the person}"
##### The details of the person are collected from the database and stored in an excel file with the persons name, all their details and the time of entry.

##### This file is saved in the entry logs folder automatically.
