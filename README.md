# Hibernate Tutorial
HIBERNATE – object relational mapping tool

Hibernate is a Java framework that maps an object-oriented model to a database.

In Hibernate.cfg.xml is specified the database connection driver, url, username and password.
In pom.xml are specified the dependencies. 

Configuration represents a configuration or properties file for Hibernate. The Configuration object is usually created once during application initialization. The Configuration object reads and establishes the properties Hibernate uses to get connected to a database and configure itself for work. A Configuration object is used to create a SessionFactory and then typically is discarded.

SessionFactory  is created from a Configuration object, and it is a factory for Session objects. It, is usually created during application start up. It should be created once and kept for later use.
The SessionFactory object is used by all the threads of an application. It is a thread safe object. One SessionFactory object is created per database. Multiple SessionFactory objects (each requiring a separate configuration) are created when connecting to multiple databases. 
Session objects provide the main interface to accomplish work with the database. A Session object does the work of getting a physical connection to the database. 
Transaction it represents unit of works.

Query and Criteria
These objects are used to retrieve (and recreate) persistent objects.

Annotations:
@Entity - Specifies that the class is an entity. This annotation is applied to the entity class. Maps the object to the spring container
@Table – Specifies the primary table. Map the object to the DB
@secondaryTable – Specifie secondary tables
@Id - Specifies the primary key of an entity. 
The @GeneratedValue annotation is used when you want Hibernate to assign the entity identifier automatically using either:
•	IDENTITY column
•	a SEQUENCE
•	or a TABLE generator
If you don’t use the @GeneratedValue annotation, then the identifier must be manually assign.
The IDENTITY generator allows an integer/bigint column to be auto-incremented on demand. The increment process happens outside of the current running transaction, so a roll-back may end-up discarding already assigned values (value gaps may happen).
A SEQUENCE is a database object that generates incremental integers on each successive request. 
The TABLE generator allows JDBC batching but it resorts to SELECT FOR UPDATE queries. The row level locking is definitely less efficient than using a native IDENTITY or SEQUENCE.
@Column - Specifies the mapped column for a persistent property or field. If no Column annotation is specified, the default values apply.
@PrimaryKeyJoinColumn - Specifies a primary key column that is used as a foreign key to join to another table.
@Embedable - Specifies a class whose instances are stored as an part of an owning entity . exp: Address in the address class before declaration.
@Embedded - Specifies a field of an entity whose value is an instance of an embeddable class. Exp: Addres in the Employee class
@OneToOne – Specifie an one to one relation
@ManyToMany – Specifie an many to many relation
@NotNull is valid as long as it’s not null, but it can be empty
@NotEmpty is valid as long as it’s not null and its size/length is greater than zero
@NotBlank  is valid as long as it’s not null and the trimmed length is greater than zero
@UniqueConstraint = { } Specifies that a unique constraint is to be included for a primary or secondary table.
@NaturalId - ????
@JoinTable annotation joins the associating table with the help of third table.
