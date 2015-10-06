### Interfaces Accessor
----------------
[PictureAccessor.java](https://github.com/dalbelap/flipper-reverse-image-search/blob/master/src/main/java/gal/udc/fic/muei/tfm/dap/flipper/repository/PictureAccessor.java)
```java
@Accessor
public interface PictureAccessor {

  @Query("SELECT * FROM picture " +
      "WHERE solr_query = :query LIMIT :total")
  Result<Picture> findSolrQueryOrdered(@Param("query") String query,
    @Param("total") int total);

}
```

[GeneralCounterAccessor.java](https://github.com/dalbelap/flipper-reverse-image-search/blob/master/src/main/java/gal/udc/fic/muei/tfm/dap/flipper/repository/GeneralCounterAccessor.java)
```java
    @Query("SELECT picture_counter FROM " +
        "user_counter WHERE user = :user")
    ResultSet getPictureCounter(@Param("user") String user);

```
