
# Hibernate Many to Many

![images](https://fmhelp.filemaker.com/help/18/fmp/en/FMP_Help/images/relational.07.06.1.png)

- A many-to-many relationship occurs when multiple records in a table are associated with multiple records in another table. Relational database systems usually don't allow you to implement a direct many-to-many relationship between two tables. If there were many invoices with the same invoice number and one of your customers inquired about that invoice number, you wouldn't know which number they were referring to. This is one reason for assigning a unique value to each invoice.

- To avoid this problem, you can break the many-to-many relationship into two one-to-many relationships by using a third table, called a join table. A typical example of a many-to many relationship is one between students and classes.

## An Example
- Let’s say we are creating a database for a university (which is an example I’ve used often). We capture details about students who attend classes, among other things. The rules are:

    - A student can be enrolled in multiple classes at a time (for example, they may have three or four classes per semester).
    - A class can have many students (for example, there may be 20 students in one class).
-   This means a student has many classes, and a class has many students.

- We can’t add the primary key of one table into the other, or both, because this only stores a single relationship, and we need many.

- So how do we capture this?

- We use a concept called a joining table or a bridging table.

- A joining table is a table that sits between the two other tables of a many-to-many relationship. Its purpose is to store a record for each of the combinations of these other two tables. It might seem like a bit of work to create, but it’s simple to do and provides a much better data structure.
-  we can create a new table called class_enrolment.
- class_enrollment. It stores two columns: one for each of the primary keys from the other table.

#### class_enrollment
| Student ID      | Class ID |
| ----------- | ----------- |
| 1      | 3       |
| 1   | 5        |
| 1      | 9      |
| 2   | 1        |
| 2      | 4       |
| 2  | 5        |
| 2     | 9       |

#### Student:

| Student ID	| Student name |
|---------------|--------------| 
| 1    | John       |
| 2    | Debbie       |

#### Class:

| Class ID	| Class name |
|-----------|------------|
|1 | English |
|2 | Maths |
|3 | Spanish |
|4 | Biology |
|5 | Science |
|6 | Programming |
|7 | Law |

- Having our data structure in this way makes it easier to add more relationships between tables and to update our students and classes without impacting the relationships between them.
