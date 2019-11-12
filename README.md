

<h1>Datos Personales</h1>

<p><img src="https://scontent.fpty1-1.fna.fbcdn.net/v/t1.0-9/s960x960/72962947_2495280033895835_5137077994673668096_o.jpg?_nc_cat=100&_nc_oc=AQm0bRQSjXrjEGjZeO0VIJeHbWFt-V-7LgNIh0THXUTuvtx89DnC1sj2e9jQH2H-0XE&_nc_ht=scontent.fpty1-1.fna&oh=c93f8fc460e7012cadf9d7843053a7b0&oe=5E5C5230">
<h2><p><strong><a href="https://arantxa-torres.github.io/Formulario-de-datos/">Formulario de datos</a></strong>
<p><strong>Nombre Completo:</strong> Arantxa Ailyn Torres Caicedo 
<p><strong>Fecha Nacimiento:</strong> 5 de Abril de 2001
<p><strong>Edad:</strong> 18 años
<p><strong>Nacionalidad:</strong> Panameña 

<h1>Datos Educativos</h1>
<p><strong>Escuelas:</strong><p>
<p><em>- Primaria: YMCA </em>
<p><em>- Premedia y media: Centro Educativo Bilingüe Visión del Saber. </em>
<p><strong>Universidad:</strong>
<P><em>- Universidad Nacional de Panamá</em>
<h1>Redes Sociales</h1>
<p><strong>Facebook:</strong> <a href="https://www.facebook.com/arantxa.torres.980">Arantxa Torres</a>
<p><strong>Instagram:</strong> <a href="https://www.instagram.com/arantxaa_xx/">arantxaa_xx</a>



<!DOCTYPE html>
<html>
  <head>
    <title>Geolocation</title>
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no">
    <meta charset="utf-8">
    <style>
      html, body, #map-canvas {
        height: 100%;
        margin: 0px;
        padding: 0px
      }
    </style>
    <!--
    Include the maps javascript with sensor=true because this code is using a
    sensor (a GPS locator) to determine the user's location.
    See: https://developers.google.com/maps/documentation/javascript/tutorial#Loading_the_Maps_API
    -->
    <script src="https://maps.googleapis.com/maps/api/js?v=3.exp&sensor=true"></script>

    <script>
// Note: This example requires that you consent to location sharing when
// prompted by your browser. If you see a blank space instead of the map, this
// is probably because you have denied permission for location sharing.

var map;

function initialize() {
  var mapOptions = {
    zoom: 6
  };
  map = new google.maps.Map(document.getElementById('map-canvas'),
      mapOptions);

  // Try HTML5 geolocation
  if(navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(function(position) {
      var pos = new google.maps.LatLng(position.coords.latitude,
                                       position.coords.longitude);

      var infowindow = new google.maps.InfoWindow({
        map: map,
        position: pos,
        content: 'Location found using HTML5.'
      });

      map.setCenter(pos);
    }, function() {
      handleNoGeolocation(true);
    });
  } else {
    // Browser doesn't support Geolocation
    handleNoGeolocation(false);
  }
}

function handleNoGeolocation(errorFlag) {
  if (errorFlag) {
    var content = 'Error: The Geolocation service failed.';
  } else {
    var content = 'Error: Your browser doesn\'t support geolocation.';
  }

  var options = {
    map: map,
    position: new google.maps.LatLng(60, 105),
    content: content
  };

  var infowindow = new google.maps.InfoWindow(options);
  map.setCenter(options.position);
}

google.maps.event.addDomListener(window, 'load', initialize);

    </script>
  </head>
  <body>
    <div id="map-canvas"></div>
  </body>
</html>
