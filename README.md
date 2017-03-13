# MediathequeREST
Mediatheque RESTful en JEE


# Scripts de création des tables

# Book
CREATE TABLE IF NOT EXISTS Book (
    Id INT NOT NULL Auto_Increment, 
    Name TEXT NOT NULL, 
    Category VARCHAR(50) NOT NULL, 
    PRIMARY KEY (ID)
)


# Member
CREATE TABLE IF NOT EXISTS Member (
    Id INT NOT NULL Auto_Increment, 
    IdBook INT NOT NULL, 
    Name TEXT NOT NULL, 
    PRIMARY KEY (ID), 
    FOREIGN KEY (IdBook) REFERENCES Book(Id)
)
