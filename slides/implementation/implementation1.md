### Patrón [**Repository**](http://www.martinfowler.com/eaaCatalog/repository.html)
----------------
[PictureRepository.java](https://github.com/dalbelap/flipper-reverse-image-search/blob/master/src/main/java/gal/udc/fic/muei/tfm/dap/flipper/repository/PictureRepository.java)
```java
public Page<Picture> findByOwnerOrdered(String owner, Pageable pageable) {

  String query = String.format("{\"q\":\"owner:%s\", " +
                  "\"start\": %d, " +
                  "\"sort\":\"created DESC\"}",
              owner, pageable.getOffset());

  List<Picture> pictures = pictureAccesor.
    findAllOrdered(query, pageable.getPageSize()).all();

  long total = userCounterAccessor.
    getPictureCounter(owner).one().getLong("picture_counter");

  return new PageImpl<>(pictures, pageable, total);
}
```
