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


## Utilisation
Il est préférable de lancer le projet directement depuis netbeans, autrement, une fois le projet sur un serveur ad-hoc, ouvrir le fichier "test-resbeans.html".

L'interface ressemble fortement à ce que l'on retrouve lorsqu'on fait un WS en .NET, il fonctionne également de la même manière que Postman ou SoapUI.
Ce que je veux dire par là, c'est que pour faire un Put ou un Post etc, il est necessaire de donner le squelette XML ou Json complet ce que vous voulez créer ou modifier.
Comme vous nous l'avez montrer sur Postman.

## En cas de besoin
En cas de besoin n'hésitez pas à nous contacter par mail : 
Clément Rémond : clementremond@outlook.fr
Eric Sailly : esailly@free.fr

### Enfin
Merci pour vos enseignements et votre patience.
