
   <div class="music">

            <img src="img/pla.png" id="icon">
         </div>

         <audio id="mysong">
            <source src="img/song.mp3" type="audio/mp3">
         </audio>

         <script>
            var mySong = document.getElementById("mysong");
            var icon = document.getElementById("icon");

            icon.onclick = function () {
               if (mySong.paused) {
                  mySong.play();
                  icon.src = "img/pau.png";
               } else {
                  mySong.pause();
                  icon.src = "img/pla.png";

               }

            }

         </script>








         /*---------- ScrollMagic----------*/


.animation{
    height: 100vh;
   
    background-repeat: no-repeat;
    background-position: center;
    position: relative;
    overflow: hidden;
}
.bool{
    height: 70px;
    position: absolute;
    top: 50%;
    left: 0;
}


<!--ScrollMagic-->

<section class="animation">
   <img class="bool" src="img/arrow.png" alt="img" />
</section>


<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/ScrollMagic.min.js" integrity="sha512-8E3KZoPoZCD+1dgfqhPbejQBnQfBXe8FuwL4z/c8sTrgeDMFEnoyTlH3obB4/fV+6Sg0a0XF+L/6xS4Xx1fUEg==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/plugins/debug.addIndicators.js" integrity="sha512-mq6TSOBEH8eoYFBvyDQOQf63xgTeAk7ps+MHGLWZ6Byz0BqQzrP+3GIgYL+KvLaWgpL8XgDVbIRYQeLa3Vqu6A==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/plugins/animation.gsap.min.js" integrity="sha512-5/OHwmQzDSBS0Ous4/hlYoWLHd06/d2r7LdKZQVBXOA6PvOqWVXtdboiLTU7lQTGyVoKVTNkwi0ol4gHGlw5ww==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/latest/TweenLite.min.js" integrity="sha512-/8phkpsAzxsbuX18zNkQ2gCq4Q5JsWoPo1jHLDeZorPUHRtx9YJxpdk+os05oDhPJVCNzA2/NMl4rmJyQ+6Fvg==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/latest/TimelineLite.min.js" integrity="sha512-I0VFyPo7hdM7YrEbQ0pvX4bX2904k0+B19u/xBrPrQoMprfcSnIDfGFD8kP52GbAhwtDjkEVhXlQvj8+vkJyew==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/latest/plugins/CSSPlugin.min.js" integrity="sha512-ht40uOoiTef4nKq0THVzjIGh3VS108J577LVVgNXnQLXza3doXjoM3owin2vd+Hm6w88k12RIrePIVY2WNzz6Q==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/latest/plugins/BezierPlugin.min.js" integrity="sha512-oOy5+mtZRcqjn6b9k4oj+tk2/hVIetzOAM9Y5cndEHgLxiIGavAz1agbHf6JjGzxXZ2SMbu08Uy1DDF0UwA0qQ==" crossorigin="anonymous"></script>
<script >
   const flightPath = {
    curviness: 0.2,
    autoRotate: true,
    values: [
        { x: 100, y: -30 },
        { x: 300, y: 90 },
        { x: 500, y: -30 },
        { x: 700, y: 90 },
        { x: 900, y: -30 },
        { x: 1100, y: 90 },
        { x: window.innerWidth, y: -30 }
    ]
}

const tween = new TimelineLite();

tween.add(
    TweenLite.to(".bool", 1, {
        bezier: flightPath,
        ease: Power1.easeInOut
    })
);

const Controller = new ScrollMagic.Controller();

const scene = new ScrollMagic.Scene({
    triggerElement: ".animation",
    duration: 1000,
    triggerHook: 0
})
    .setTween(tween)
    .addIndicators()
    .setPin('.animation')
    .addTo(Controller);
</script>

