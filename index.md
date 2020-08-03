<!doctype HTML>

<html>
<script src="https://aframe.io/releases/0.9.2/aframe.min.js"></script>
<script src="https://rawgit.com/donmccurdy/aframe-extras/master/dist/aframe-extras.loaders.min.js"></script>
<script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.5.0/aframe/build/aframe-ar.js"> </script>
    
  <body style='margin : 0px; overflow: hidden;'>
    <a-assets>
        <video id="vid" src="buckBunny.mp4" loop="true" crossorigin></video>
    </a-assets>
    <a-marker preset="hiro" vidhandler>
      <a-plane position='1 2 0' scale="2 2 2" width="2" rotation="-90 0 0" 
       material='transparent:true; opacity: 0.7; src:#vid'></a-plane>
    </a-marker>
      
    <script>
      AFRAME.registerComponent('vidhandler', {
          init: function () {
            this.toggle = false;
            this.vid = document.querySelector("#vid")
            this.vid.pause()
        },
        tick:function(){
           if(this.el.object3D.visible == true){
             if(!this.toggle){
               this.toggle = true;
               this.vid.play();
            }
          }else{
            this.toggle = false;
            this.vid.pause();
          }
         }
        });
      </script>
      
  </body>
</html>
