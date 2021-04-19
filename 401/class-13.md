# Entity Relationships

- Generally the relations are more effective between tables in the database.
- we have four type of relations
    1. ManyToOne Relation
    2. OneToMany Relation
    3. OneToOne Relation
    4. ManyToMany Relation

## ManyToOne Relation

![images](https://www.tutorialspoint.com/jpa/images/many_to_one_relation.png)

- Many-To-One relation between entities: Where one entity (column or set of columns) is/are referenced with another entity (column or set of columns) which contain unique values. In relational databases these relations are applicable by using foreign key/primary key between table

## OneToMany Relation

![images](https://grokonez.com/wp-content/uploads/2017/09/kotlin-springjpa-one-to-many-relationship-uml.png)

- In this relationship each row of one entity is referenced to many child records in other entity. The important thing is that child records cannot have multiple parents. In a one-to-many relationship between Table A and Table B, each row in Table A is linked to 0, 1 or many rows in Table B.

## OneToOne Relation

![images](https://allaroundjava.com/wp-content/uploads/2019/02/one_to_one_entity_relation.png)

- In One-To-One relationship, one item can belong to only one other item. It means each row of one entity is referred to one and only one row of another entity.

## ManyToMany Relation

![images](https://www.tutorialspoint.com/jpa/images/many_to_many_relation.png)

- Many-To-Many relationship is where one or more rows from one entity are associated with more than one row in other entity.

# Integration Testing in Spring

![images](https://www.programmersought.com/images/330/1f28c5178da2bfee00e666f3a739b0a2.JPEG)

- Spring Boot provides an easy way to write a Unit Test for Rest Controller file. With the help of SpringJUnit4ClassRunner and MockMvc, we can create a web application context to write Unit Test for Rest Controller file.
