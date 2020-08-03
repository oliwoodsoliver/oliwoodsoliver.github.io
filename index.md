<!doctype HTML>

<html>
<script src="https://aframe.io/releases/0.9.2/aframe.min.js"></script>
<script src="https://rawgit.com/donmccurdy/aframe-extras/master/dist/aframe-extras.loaders.min.js"></script>
<script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.5.0/aframe/build/aframe-ar.js"> </script>
  <body style='margin : 0px; overflow: hidden;'>
    <a-assets>
       <video id="ds" autoplay loop="true" muted="true" crossorigin="anonymous" src="https://archive.org/download/electricsheep-flock-244-37500-9/00244%3D37509%3D33572%3D32771_512kb.mp4"></video>
    </a-assets>

    <a-scene embedded arjs='trackingMethod: best;, sourceType: webcam; debugUIEnabled: false;'>
      <a-marker preset="kanji" vidhandler>
        <a-plane position='1 2 0' scale="2 2 2" width="2" rotation="-90 0 0" material='transparent:true; opacity: 1; src:#ds'></a-plane>
      </a-marker>
    </a-scene>

    <script>
      window.addEventListener('load', function () {
      var v = document.querySelector('#ds');
      v.play();
      });
    </script>

  </body>
</html>
