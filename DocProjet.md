# MediathequeREST
Mediatheque RESTful en JEE

# Clément Remond (confirmé) / Eric Sailly (débutant)

Netbeans 8.2
Glassfish 4.1 (NOT 4.1.1 !)
Java 1.8.0_91
Serveur MySQL 5.5.54 et serveur de l'ULCO

#le projet est disponible sur GitHub à l'adresse :
	https://github.com/clembazard/MediathequeREST

#Paramétrage :
	editer le fichier : « ./web/WEB-INF/glassfish-resources.xml »
	changer les informations suivantes :

	<property name="serverName" value="ADRESSE de votre serveur mysql"/>
	<property name="portNumber" value="PORT de votre serveur mysql"/>
	<property name="databaseName" value="Nom de votre base"/>
	<property name="User" value="USER mysql"/>
	<property name="Password" value="password mysql"/>
	<property name="URL" value="jdbc:mysql://ADRESSE:PORT/NomDeLaBase?zeroDateTimeBehavior=convertToNull"/>
        

## Scripts de création des tables

### Book
    CREATE TABLE IF NOT EXISTS Book (
        Id INT NOT NULL Auto_Increment, 
        Name TEXT NOT NULL, 
        Category VARCHAR(50) NOT NULL, 
        PRIMARY KEY (ID)
    );
        
    INSERT INTO Book (`Name`, Category) VALUES 
    ("Harry Potter 1", "Fantasy"),
    ("Harry Potter 2", "Fantasy"),
    ("Harry Potter 3", "Fantasy"),
    ("Harry Potter 4", "Fantasy"),
    ("Jurassic Park", "Sci-fi");


### Member
    CREATE TABLE IF NOT EXISTS Member (
        Id INT NOT NULL Auto_Increment, 
        IdBook INT NOT NULL, 
        Name TEXT NOT NULL, 
        PRIMARY KEY (ID), 
        FOREIGN KEY (IdBook) REFERENCES Book(Id)
    );

    INSERT INTO Member (IdBook, `Name`)
    VALUES
    (5, "Clément Rémond"),
    (1, "Eric Sailly");
