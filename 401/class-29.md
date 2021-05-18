# Room
- we can use Room to save data that user can enter to local Database.
- There are three major components in Room:
    1. database class
    2. Data entities
    3. Data access objects (DAOs)

    ![images](https://developer.android.com/images/training/data-storage/room_architecture.png)

- Sample implementation
    1. Data entity
    2. Data access object (DAO)
    3. Database

# Defining data using Room entities
- we can use @Entity to defined the table in DataBase.
- to defined  a primary key we will use @PrimaryKey above the field that we want to be primary Key
- Define a composite primary key we can use @Entity with properties  primaryKeys
-  we use  @Ignore to Ignore fields.
- we can Provide table search support with @Fts4 or @Fts3.
- Include AutoValue-based objects we use @AutoValue.


# Define relationships between objects
- Create embedded objects with @Embedded in the Entity we need to use it.

- Define one-to-one relationships be use  @Relation and we should provide the columns from the tables tht we need to create the relation between them.
- Define one-to-many relationships be use  @Relation and we should provide the columns from the tables tht we need to create the relation between them.
- Define many-to-many relationships

# Accessing data using Room DAOs
- Anatomy of a DAO ou must always annotate your DAOs with @Dao
- Convenience methods
    1. Insert we can use it be  @Insert
    2. Update we can use it be @Update
    3. Delete we can use it be @Delete
- Query methods we can use  @Query and write some sql statement in it.