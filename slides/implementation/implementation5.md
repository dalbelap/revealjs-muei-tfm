### *Infinite scroll*
-----------------
[pictures.html](https://github.com/dalbelap/flipper-reverse-image-search/blob/master/src/main/webapp/scripts/app/entities/picture/pictures.html)
```html
<div class="row" infinite-scroll="loadPage(page + 1)"
  infinite-scroll-disabled="links['last'] == page">
    <div ng-repeat="picture in pictures">
        <div ng-if="$index % 4 == 0" class="clearfix"></div>
        <div class="col-xs-4 col-sm-3 col-md-3 portfolio-item">
          ...
        </div>
    </div>
</div>
```
