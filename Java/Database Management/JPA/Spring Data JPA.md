
JPA is just a specification. It is showing how the code can be implemented but has not in itself implemented anything. In other words, JPA is just an interface but Hibernate (which is a ORM) is actually the implementation framework.

ORM is object-relational mapping. Java code is written and Hibernate, following the JPA specification, takes care of creating tables and etc. based on the mappings of the Java class.

Spring Data JPA is an abstraction layer built on top of [[Hibernate]]. It makes it easy to implement JPA based repositories. This module deals with enhanced support for JPA based data access layers.

## General
- [[Data with JPA]]

## JPA Entities
- [[JPA Entities]]
-  [[Generating Primary Keys]]
- [[Entity]]

## Queries
- [[Queries]]
- [[Custom Queries]]

## Repository
- [[JPA Repositories]]
- [[CRUD Repository]]
- [[Connecting Repository to Controller]]

## Testing
- [[Testing JPA Repository]]

## Properties
- [[JPA & Hibernate Properties]]

