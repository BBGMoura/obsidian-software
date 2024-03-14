JPA offers 4 different ways to generate primary key values with the annotation **@Id**.

1. AUTO: Hibernate selects the generation strategy based on used dialect
2. IDENTITY: Hibernate relies on an auto-incremented database column to generate the primary key
3. SEQUENCE: Hibernate requests the primary key value from a database sequence
4. TABLE: Hibernate uses a database table to simulate a sequence