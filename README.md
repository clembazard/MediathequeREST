# MediathequeREST
Mediatheque RESTful en JEE


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
