There are different ways of writing queries with Spring Data JPA.

### findByFieldName
``` java
@Repository
public interface SurveryRepository extends JpaRepository<Survey, Long> {

	Optional<Survey> findById(Long surverId);
	
	Long countByCreatedBy(Long userId);
}
```

More details in [[Custom Queries]]

### @Query
``` java
@Repository
public interface VoteRepository extends JpaRepository<Vote, Long> {

	@Query("SELECT v FROM Vote v WHERE v.user.id = :userId AND v.surver.id in :surverIds")
	List<Vote> findByUserIdAndSurverIdIn(@Param("userId) Long userId, @Param("surverIds") List<Long> surveyIds)

}
```
