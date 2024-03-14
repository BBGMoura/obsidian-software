## Hibernate Caching
- Caching is a mechanism to enhance the performance of a system. 
- It is a buffer memory that lies between the application and the database.
- Instead of making the query to the database consistently, we ask hibernate to cache it.
- Cache memory stores recently used data items in order to reduce the number of database hits.

Hibernate utilises multilevel caching:
### Levels of Caching
**First-Level Caching**
The first-level cache is the Session cache and is mandatory cache though which all requests must pass. The Session object keeps an object under its own power before committing it to the database.

**Second-Level Caching**
Second-level cache is an optional cache. It is on the factory level. This cache can be configured on a per-class and per-collection basis and mainly responsible for caching objects across sections.

**Query-level Cache**
Hibernate also implements a cache for query result-sets that integrates closely with he second level cache.

This is an optional feature which requires two additional physical cache regions that hold the cached query results and timestamp of when a able was last updated. This is useful for queries which are ran frequently with the same parameters.

![[hibernate cache.png]]
