### Indexación de Descriptores con Lire
-----------------
[LireBuilder.luceneIndexer(BufferedImage image, ...)](https://github.com/dalbelap/flipper-reverse-image-search/blob/master/src/main/java/gal/udc/fic/muei/tfm/dap/flipper/service/util/cbir/LireBuilder.java)
```java
IndexWriter indexWriter = new IndexWriter(dir, conf);

try {
    // Creates builder from Lire descriptor
    DocumentBuilder builder = DocumentBuilderFactory.
      getEdgeHistogramBuilder();

    // Creates a Lucene document
    Document document = builder.createDocument(bufferedImage,
      pictureUUID);

    // Store document in Lucene
    indexWriter.addDocument(document);

} catch (IOException e) {
    throw new LireIndexerException("Error reading image.");
}
```
