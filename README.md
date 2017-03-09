# interactive-map
Maps are a great way to leverage your website to drive traffic to your doors. A majority of maps simply show the locations of a given entity as well as an address without any further context or interactivity. In our example, we've designed a map that displays locations you can learn more about by clicking on the location. Clicking on the location triggers a popup with further information related to that specific location. You can add any information you'd like to these popups that make the most sense for your business. 

## Tutorials

For detailed instructions, view Solodev's [Designing an Interactive Map using JavaScript](https://www.solodev.com/blog/web-design/designing-an-interactive-map-using-javascript.stml) article.

## Demo

Try out a working example on [JSFiddle](https://jsfiddle.net/solodev/ero96q7n/).

## HTML

The interactive map contains the following basic HTML markup.

```
<div class="container" >
   <div class="row ct-u-padding-bottom-40" >
      <div class="col-lg-6 col-lg-push-6 col-md-7 col-md-push-5" >
         <div class="ct-map" >
            <img alt="Map" class="ct-map__image" src="https://www.solodev.com/assets/map/map-revised.jpg" >
            <div class="ct-city stone" >
               <button class="ct-city__button" type="button" tabindex="0" ><img alt="Map Open Icon" class="ct-plus" src="https://www.solodev.com/assets/map/map-plus.png"  data-pin-nopin="true"><img alt="Map Close Icon" class="ct-close" src="https://www.solodev.com/assets/map/map-close.png" data-pin-nopin="true" ><span class="ct-city__name" >Headquarters</span></button>
               <div class="ct-popup" >
                  <div class="inner" >
                     <span class="ct-popup__name" >HQ</span>
                     <p class="ct-popup__content" >
                        Corporate Headquarters<br />at 1400 N. Magnolia.
                     </p>
                  </div>
               </div>
            </div>
            <div class="ct-city orlando">
               <button class="ct-city__button" type="button" tabindex="0" ><img alt="Map Open Icon" class="ct-plus" src="https://www.solodev.com/assets/map/map-plus.png"  data-pin-nopin="true"><img alt="Map Close Icon" class="ct-close" src="https://www.solodev.com/assets/map/map-close.png"  data-pin-nopin="true"><span class="ct-city__name" >Local Office</span></button>
               <div class="ct-popup" >
                  <div class="inner" >
                     <span class="ct-popup__name" >Local</span>
                     <p class="ct-popup__content" >
                        Your local WebCorpCo office.
                     </p>
                  </div>
               </div>
            </div>
            <div class="ct-city orlando2" >
               <button class="ct-city__button" type="button" tabindex="0" ><img alt="Map Open Icon" class="ct-plus" src="https://www.solodev.com/assets/map/map-plus.png"  data-pin-nopin="true"><img alt="Map Close Icon" class="ct-close" src="https://www.solodev.com/assets/map/map-close.png" ><span class="ct-city__name" >Regional Office</span></button>
               <div class="ct-popup" >
                  <div class="inner" >
                     <span class="ct-popup__name" >Regional</span>
                     <p class="ct-popup__content" >
                        Regional Headquarters<br />at 435 Curson Ave.
                     </p>
                  </div>
               </div>
            </div>
         </div>
      </div>
      <div class="col-lg-6 col-lg-pull-6 col-md-5 col-md-pull-7" >
         <div class="ct-content" >
            <h2 class="ct-section-header text-left" >
               Our Locations<small >Just Around the Corner</small>
            </h2>
            <br >
            <br >
            <ul class="list-unstyled" >
               <li >Meet with a WebCorpCo Specialist anywhere, anytime
               </li>
               <li >Local, regional, and national data centers
               </li>
               <li >Compute storage ranging from $5k-$25k
               </li>
               <li >Amazing customer service from WebCorpCo Success Team
               </li>
               <li >Free Parking and Snacks
               </li>
               <li >Pool, Gym, and Jacuzzi at all locations
               </li>
            </ul>
            <a class="btn btn-motive" href="#" tabindex="0" >Learn More</a>
         </div>
      </div>
   </div>
</div>
```

## CSS

All required CSS is included in interactive-map.css

## JavaScript

The interactive map utilizes the following JavaScript.

```
$(document).ready(function() {
      var city, map;
      map = $('.ct-map');
      city = map.find('.ct-city');
      city.each(function() {
        var button, that;
        that = $(this);
        button = that.find('.ct-city__button');
        return button.on('click', function() {
          city.not(that).removeClass('active');
          if (that.hasClass('active')) {
            that.removeClass('active');
            return map.removeClass('popup-open');
          } else {
            that.addClass('active');
            return map.addClass('popup-open');
          }
        });
      });
});
```
## External Includes

This tutorial includes the following third party resources.

```
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet">
<link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">
<link href="interactive-map.css" rel="stylesheet">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
```

