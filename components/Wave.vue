<template>
<div class='box'>
  <div class='wave -one'></div>
  <div class='wave -two'></div>
</div>

</template>

<script>
</script>

<style>
.box {
	position: fixed;
	top: 30%;
	transform: rotate(80deg);
	left: 0;
<<<<<<< HEAD
    bottom: 0;
    z-index: -1;
=======
    	bottom: 0;
	z-index: 1;
>>>>>>> 83158eec96a16a5656697738c7ad653232d0a09d
}

.wave {
	position: fixed;
	top: 0;
	left: 0;
  opacity: .4;
  position: absolute;
  top: 3%;
  left: 10%;
  background: #09b48980;
  width: 1500px;
  height: 1300px;
  margin-left: -150px;
  margin-top: -250px;
  transform-origin: 50% 48%;
  border-radius: 43%;
  animation: drift 7000ms infinite linear;
}


.wave.-two {
  animation: drift 3000ms infinite linear;
  opacity: .1;
  background: black;
	position: fixed;
}

.box:after {
  content: '';
  display: block;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 11;
  transform: translate3d(0, 0, 0);
}

@keyframes drift {
  from { transform: rotate(0deg); }
  from { transform: rotate(360deg); }
}

/*LOADING SPACE*/

.contain {
	animation-delay: 4s;
	z-index: 1000;
	position: fixed;
	top: 0;
	left: 0;
	bottom: 0;
	right: 0;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-flow: row nowrap;
  flex-flow: row nowrap;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;

  background: #09b489e7;
  background: -webkit-linear-gradient(#09b48980, #40e0b8cb);
  background: linear-gradient(#ffffff, #ffffff);
}

.icon {
  width: 100px;
  height: 100px;
  margin: 0 5px;
}

/*Animation*/
.icon:nth-child(2) img {-webkit-animation-delay: 0.2s;animation-delay: 0.2s}
.icon:nth-child(3) img {-webkit-animation-delay: 0.3s;animation-delay: 0.3s}
.icon:nth-child(4) img {-webkit-animation-delay: 0.4s;animation-delay: 0.4s}

.icon img {
  -webkit-animation: anim 2s ease infinite;
  animation: anim 2s ease infinite;
  -webkit-transform: scale(0,0) rotateZ(180deg);
  transform: scale(0,0) rotateZ(180deg);
}

@-webkit-keyframes anim{
  0% {
    -webkit-transform: scale(0,0) rotateZ(-90deg);
    transform: scale(0,0) rotateZ(-90deg);opacity:0
  }
  30% {
    -webkit-transform: scale(1,1) rotateZ(0deg);
    transform: scale(1,1) rotateZ(0deg);opacity:1
  }
  50% {
    -webkit-transform: scale(1,1) rotateZ(0deg);
    transform: scale(1,1) rotateZ(0deg);opacity:1
  }
  80% {
    -webkit-transform: scale(0,0) rotateZ(90deg);
    transform: scale(0,0) rotateZ(90deg);opacity:0
  }
}

@keyframes anim{
  0% {
    -webkit-transform: scale(0,0) rotateZ(-90deg);
    transform: scale(0,0) rotateZ(-90deg);opacity:0
  }
  30% {
    -webkit-transform: scale(1,1) rotateZ(0deg);transform: scale(1,1) rotateZ(0deg);opacity:1
  }
  50% {
    -webkit-transform: scale(1,1) rotateZ(0deg);
    transform: scale(1,1) rotateZ(0deg);opacity:1
  }
  80% {
    -webkit-transform: scale(0,0) rotateZ(90deg);
    transform: scale(0,0) rotateZ(90deg);opacity:0
  }
}
</style>
