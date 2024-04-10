# Introduction :-
In this guide we are going to discuss about

1) Entity creation

2) Repo creation

3) Service Creation

4) Controller Creation

5) Database configuration in application.properties

6) Adding data.sql with sql queries.

7) Reading Employee Data


### Adding employee package :- 
Let us create a package with name employee in src/main/java/com.learn.employeeservice.

![img.png](img.png)

![img_1.png](img_1.png)

## Employee Entity Creation :-

Let us create a new java class i.e Employee file inside employee folder.

![img_2.png](img_2.png)


![img_3.png](img_3.png)

### Adding Fields inside Employee :-
Let us add below fields

1) Id (Long/int type)

2) Name (String type)

3) Age (Integer type)

4) isActive (Boolean type)

5) Salary (Double type)

### Employee class with Fields information :-
```
package com.learn.employeeservice.employee;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;

@Getter
@Setter
@Entity
@Table(name="employee")
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private int age;
    private boolean isActive;
    private double salary;
}


```
### Adding Annotations in employee class

@Entity - The class annotated with @Entity informs spring boot this is
entity class and it can be mapped to a db table.

@Table - Using this annotation we can give database table name.

@Id - Marking specific field as primary key of entity. Eg:- id column.

@GeneratedValue - This annotation is used to specify the primary key generation strategy to use. i.e Instructs database to generate a value for this field automatically. If the strategy is not specified by default AUTO will be used.

@Getter - its shortcut annotation for creating all getter methods

@Setter- shortcut annotation for creating all setter methods.

Let us add all these annotations to the Employee Entity class.

## Final Version of Employee Entity

```
package com.learn.employeeservice.employee;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;

@Entity
@Table(name="employee")
@Getter
@Setter
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private int age;
    private boolean isActive;
    private double salary;
}
```
## EmployeeRepository creation :-

We need Repository to interact with database.
So Let us create EmployeeRepository interface in employee package.

![img_4.png](img_4.png)

**Note** :- EmployeeRepository is an **interface**. so please select
type as interface while creating file.

#### EmployeeRepository is going to extends JpaRepository.

JpaRepository ==> JPA(Java Persistence API) Repository is mainly used for managing the data in a Spring Boot Application.
it contains API for basic CRUD operations and also API for pagination and sorting.

```
public interface JpaRepository<T,ID>
Where:

    T: Domain type that repository manages (Generally the Entity/Model class name)
    ID: Type of the id of the entity that repository manages (Generally the wrapper class of your @Id that is created inside the Entity/Model class)

```

Final version of EmployeeRepository


```
package com.learn.employeeservice.employee;

import org.springframework.data.jpa.repository.JpaRepository;

public interface EmployeeRepository extends JpaRepository<Employee, Long> {
}

```











