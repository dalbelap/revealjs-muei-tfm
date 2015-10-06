### *Infinite scroll*
-----------------
[picture.controller.js](https://github.com/dalbelap/flipper-reverse-image-search/blob/master/src/main/webapp/scripts/app/entities/picture/picture.controller.js)
```javascript
$scope.loadAll = function() {
Picture.query({page: $scope.page, size: 20}, function(result, headers)
{
      $scope.links = ParseLinks.parse(headers('link'));
      for (var i = 0; i < result.length; i++) {
         $scope.pictures.push(result[i]);
      }
});
```
